# RobotPal - 수신 서버(Python) 설계: 최신성 우선(프레임 드롭)

## 목표
- “가장 최신 프레임”을 빠르게 반영한다.
- 디코딩/리사이즈가 밀려서 지연이 누적되는 상황을 끊는다.

## 문제
- 수신(네트워크)과 디코딩/리사이즈(CPU bound)가 한 코루틴에서 같이 돌면, 처리 지연이 누적된다.
- 결과적으로 “지금 화면/AI가 필요한 프레임”이 아니라 “과거 프레임”을 처리하게 된다.

## 해결
### 1) Receiver/Processor 분리
- Receiver:
  - WS: `async for message in websocket`에서 bytes만 받아 Queue에 넣는다.
  - TCP: `reader.read()`로 받은 조각을 buffer에 누적하고 길이 헤더(4B) 기반으로 프레임을 완성한다.
- Processor:
  - Queue에서 bytes를 꺼내 최신 프레임 기준으로 처리한다.

### 2) Queue size를 1로 고정
- Queue가 꽉 차면 기존 값을 버리고 최신 프레임으로 교체한다.
- “프레임 드롭”을 명시적으로 선택해서 지연 누적을 막는다.

### 3) JPEG pass-through + 디코딩은 thread pool
- 화면 표시용: `latest_jpeg`를 즉시 업데이트(디코딩 없음).
- AI용: 디코딩/리사이즈는 `ThreadPoolExecutor`로 넘겨 I/O 루프를 막지 않는다.
- 모드:
  - `ROBOTPAL_STREAM_MODE=single`: 디코딩을 메인 루프에서(단순)
  - 기본(`multi`): executor에서 병렬 디코딩

## 제어 명령 송신(요약)
- Python에서 JSON 직렬화 후 길이 헤더(4B)를 붙여 WS 또는 TCP로 전송한다.
- 인터페이스는 동일하지만, 채널(WS/TCP)은 연결 상태에 따라 달라진다.

## 대안과 트레이드오프(수신/처리 관점)
- 프레임을 모두 보존(Queue를 키움):
  - 장점: 손실 없음
  - 단점: 실시간 스트리밍에서는 “지연”이 더 큰 문제(사용자는 과거 화면을 봄)
- 디코딩을 GPU로 오프로딩:
  - 장점: CPU 여유 확보
  - 단점: 환경 의존성 증가, 개발 복잡도 증가

