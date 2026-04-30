# SCHED_DEADLINE

## 정의
SCHED_DEADLINE은 Linux의 deadline 기반 실시간 스케줄링 정책이다. 작업이 필요한 CPU 시간(runtime), 반복 주기(period), 마감 시간(deadline)을 선언하고, 커널은 그 조건을 기준으로 스케줄링한다.

## 사용 환경
주기적으로 실행되어야 하고 마감 시간을 지켜야 하는 오디오 처리, 제어 시스템, 로봇 제어 같은 실시간 작업에서 사용된다.

## 사용 조건
작업의 runtime, deadline, period를 알고 있어야 한다. 시스템 전체 CPU 용량을 초과하는 설정은 받아들여지지 않거나 불안정한 동작을 만들 수 있다.

## 예시
어떤 작업이 10ms마다 한 번 실행되어야 하고, 매 주기마다 2ms의 CPU 시간이 필요하다면 다음처럼 생각할 수 있다.

```text
runtime = 2ms
period = 10ms
deadline = 10ms
```

이 작업은 한 주기마다 2ms의 CPU 예산을 받고, 예산을 다 쓰면 다음 주기까지 제한될 수 있다.

## 주의점
- SCHED_DEADLINE은 일반 작업을 빠르게 만들기 위한 옵션이 아니다.
- 잘못 설정하면 시스템 전체의 예측 가능성과 안정성을 해칠 수 있다.
- EEVDF의 virtual deadline과 SCHED_DEADLINE의 실시간 deadline은 목적이 다르다.

## 관련 용어
[[용어 모음집/SCHED_FIFO|SCHED_FIFO]], [[용어 모음집/SCHED_RR|SCHED_RR]], [[용어 모음집/EEVDF|EEVDF]], [[용어 모음집/스케줄링|스케줄링]], [[용어 모음집/CPU|CPU]]
