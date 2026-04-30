# 영묘 - Opus 코덱(프레임) 설계

## 문제 1: Raw PCM 전송 비용
- PCM은 무압축이라 대역폭이 커지고, 실시간 전송에서는 병목이 된다.

## 해결 1: libopus 기반 인코딩
- Opus Encoder 설정(VoIP):
  - bitrate: 24kbps
  - FEC(inband): on, packet loss 10% 가정
  - DTX: on(무음이면 전송 억제)
  - complexity: 5(인코딩 CPU 절약)

## 문제 2: UE 기본 Voice encoder/decoder의 UDP 부적합
- UE의 IVoiceEncoder/IVoiceDecoder는 “stream 기반”이라 UDP에서 프레임 단위로 잘라 보내면 상태가 깨질 수 있다.

## 해결 2: “Stateless 프레임 단위” 코덱 + Ring buffer
- 16kHz 기준 20ms 프레임(320 samples) 단위로 인코딩.
- Ring buffer에 PCM을 누적하고, 오래된 데이터는 버린다(최대 60ms 수준만 유지).
- Opus payload는 프레임별로 `[2바이트 길이][N바이트 opus]`를 반복해서 패킹한다.

## 문제 3: 디코딩 동시성 이슈
- 동일 화자의 코덱을 여러 스레드에서 동시에 디코드하면 상태가 꼬일 수 있다.
- 해결: 수신 순서대로 GameThread에서 단일 디코드/재생(실패 프레임은 드롭).

