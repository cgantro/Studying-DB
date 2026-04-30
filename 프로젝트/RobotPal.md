# RobotPal

## 한 줄 정의
C++ 기반 로봇 시뮬레이터를 Web/Desktop으로 확장하고, 실시간 제어/영상 파이프라인 병목을 구조적으로 개선한 프로젝트.

## 내 역할
- C++/Python 네트워크 아키텍처
- TCP/WebSocket 전송 계층 설계
- 성능 병목 분석 및 병렬화

## 핵심 구조
- Python asyncio Receiver/Processor 분리
- Queue 기반 Producer-Consumer
- C++ NetworkTransport 추상화(TCP/WebSocket 교체 가능)
- Emscripten 기반 WASM 포팅

## 기술 선정 이유
- C++17: 성능/자원 제어
- asyncio + Queue: I/O 비동기 처리와 병목 분리
- WebAssembly: 설치 없이 브라우저 실행
- ECS(flecs): 모듈 결합도 감소, 확장성

## 개선 경험
### JPEG 인코딩 병목
- 원인: 단일 스레드 + 무거운 인코딩 단계
- 해결: libjpeg-turbo + 멀티스레드 인코딩 파이프라인
- 결과: 처리량 2배 이상, 멀티코어 활용 개선

### 패킷 파싱 안정화
- 원인: TCP stickiness
- 해결: 길이 헤더 + 링버퍼 기반 커스텀 프로토콜

## CS 연결
- 운영체제: 스레드/큐/경합
- 네트워크: 스트림 파싱, 지연/처리량 균형
- 컴퓨터구조: SIMD 최적화 체감
