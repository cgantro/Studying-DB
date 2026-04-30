# RobotPal

## 현재 상태
- **진행중** (RobotPal 저장소 기준 마지막 커밋: `2026-04-09 +09:00`)

## 한 줄 정의
C++ 로봇 시뮬레이터에서 “제어 명령 송수신 + 카메라 스트리밍”을 Desktop(TCP) / Web(Emscripten WebSocket)로 확장하면서, 병목을 측정하고 파이프라인으로 쪼개서 해결한 프로젝트.

## 내 역할
- (내 담당) 카메라 스트리밍 파이프라인 병목 측정/개선
- (내 담당) Desktop(TCP) / Web(WebSocket) 전송 계층 추상화, 송신 비동기화
- (내 담당) Python 수신 서버에서 실시간성 중심 수신/처리 분리(프레임 드롭, 디코딩 오프로딩)
- (팀 공통) 시뮬레이터 기능 개발, 씬/에디터/UI 확장 (내 기여와 구분 필요 시 추가 정리)

## 핵심 구조
- C++(송신): `Texture::GetAsyncData(PBO ping-pong)` → `StreamingPipeline(queue)` → `EncodeWorker(N개)` → `len(4B)+JPEG` → `NetworkEngine(NetworkTransport)`
- Python(수신): Receiver(WS/TCP) → Buffering(길이 헤더 파싱) → `latest_jpeg` 즉시 갱신(디코딩 없음) + `latest_image`는 thread pool에서 디코딩/리사이즈
- 전송 계층: Native는 TCP + SendThread로 메인 스레드 블로킹 회피, Web은 Emscripten WebSocket

## 기술 선정 이유
- C++17: 렌더/시뮬레이션 루프에서 지연 제어가 필요
- 길이 헤더(4B) 기반 바이너리 프로토콜: TCP fragmentation/stickiness를 수신 측에서 안전하게 처리
- JPEG + libjpeg-turbo: 구현 난이도 대비 즉시 적용 가능한 CPU 경량화 포인트
- Producer-Consumer(Queue) + 멀티 워커: “렌더링/캡처/인코딩/전송”을 분리해서 병목 위치를 고정
- asyncio + ThreadPoolExecutor: Python에서 I/O와 CPU(디코딩/리사이즈) 경합을 분리

## 문제 -> 원인 -> 해결 (요약)
### 1) 카메라 스트리밍 FPS 하락
- 문제: 스트리밍을 켜면 앱 FPS/수신 FPS가 떨어짐
- 원인: `glReadPixels`(GPU→CPU readback) stall + JPEG 인코딩(CPU bound) + 잦은 할당/복사
- 해결:
  - Desktop: PBO 2개 ping-pong으로 readback 비동기화 (`Texture::GetAsyncData`)
  - 인코딩: 워커 스레드 분리 + 버퍼 재사용(reserve/clear) + RGBA→RGB 변환 최적화
  - JPEG: libjpeg-turbo 경로로 통일(CMake에서 Native/Web 분기 포함)

### 2) 실시간성이 중요한데 수신 측이 밀림
- 문제: 수신(네트워크)과 디코딩이 한 덩어리면 프레임 지연이 누적됨
- 원인: 디코딩/리사이즈는 CPU bound이고, 처리 지연이 곧 “최신 프레임” 손실로 이어짐
- 해결: Python에서 Receiver/Processor 분리 + Queue size=1로 최신 프레임만 유지(프레임 드롭)

## CS 연결
- 운영체제: 스레드/큐/경합
- 네트워크: 스트림 파싱, 지연/처리량 균형
- 컴퓨터구조: SIMD 최적화 체감

## 상세 문서
- [00-상태-요약](RobotPal/00-상태-요약.md)
- [01-구조-흐름](RobotPal/01-구조-흐름.md)
- [02-카메라-스트리밍-송신-병목-개선](RobotPal/02-카메라-스트리밍-송신-병목-개선.md)
- [03-수신-서버-Python-프레임-드롭-실시간](RobotPal/03-수신-서버-Python-프레임-드롭-실시간.md)
- [04-전송계층-추상화-대안](RobotPal/04-전송계층-추상화-대안.md)
