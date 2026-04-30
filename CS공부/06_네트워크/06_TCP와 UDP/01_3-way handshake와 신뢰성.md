# 3-way handshake와 신뢰성

## 3-way handshake
- SYN -> SYN/ACK -> ACK
- 양쪽의 송수신 가능 상태와 초기 시퀀스 번호를 동기화

## TCP 신뢰성 메커니즘
- 순서 보장
- 재전송
- 흐름 제어
- 혼잡 제어

## 실무 이슈
- handshake 실패: 방화벽/포트/라우팅/백로그 포화
- 재전송 증가: 패킷 손실, RTT 증가, 혼잡 상태 의심
