# 영묘 - 보이스 UDP 릴레이 서버

## 문제
- TCP(WebSocket) 기반 보이스는 “신뢰성” 때문에 최신 프레임보다 순서/재전송이 우선될 수 있어, 지연이 누적되기 쉬웠다.

## 해결: UDP 릴레이 + 룸 단위 브로드캐스트
- 서버는 “디코딩/믹싱”을 하지 않고, 같은 roomCode 참가자에게 패킷을 그대로 전달하는 릴레이 역할을 한다.

## 구현 포인트(근거)
- payload 검증:
  - `payloadSize`와 실제 길이 불일치, 과대 payload는 드롭
  - voice payload 상한: `2048` bytes
- 워커 구조:
  - roomCode 해시로 shard를 고정해서 worker 2개로 분산
  - UDP 수신 콜백 → sharedData 확보(복사 최소화) → shard queue push → worker에서 파싱/라우팅
- stale cleanup:
  - 클라이언트 lastSeen 기반 타임아웃 정리(기본 300s), 주기 60s

## 대안
- WebRTC:
  - 장점: NAT traversal, 지터/손실 대응 내장
  - 단점: 시그널링/세션/브라우저 호환까지 포함하면 구현량이 커짐

