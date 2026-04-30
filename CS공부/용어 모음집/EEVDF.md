# EEVDF

## 정의
EEVDF(Earliest Eligible Virtual Deadline First)는 CPU를 받을 자격이 있는 작업 중 virtual deadline이 가장 빠른 작업을 선택하는 스케줄링 방식이다.

## 사용 환경
Linux의 일반 작업 스케줄링에서 공정성을 유지하면서 지연 시간에 민감한 작업을 더 잘 다루기 위해 사용된다.

## 사용 조건
작업별 virtual runtime, lag, virtual deadline 같은 값을 계산할 수 있어야 한다. CPU를 받을 자격이 있는 작업만 후보가 된다.

## 예시
작업 A와 B가 둘 다 실행 가능하더라도, A가 공정한 몫보다 CPU를 더 많이 받았다면 당장 선택 대상에서 밀릴 수 있다. 반대로 CPU를 받을 자격이 있고 deadline이 더 빠른 작업은 먼저 실행될 수 있다.

## 주의점
- EEVDF는 실시간 deadline을 무조건 보장하는 [[용어 모음집/SCHED_DEADLINE|SCHED_DEADLINE]]과 다르다.
- 여기서 deadline은 일반 작업의 공정성과 지연 시간 조절을 위한 virtual deadline이다.
- CFS의 공정성 아이디어와 연결해서 이해하면 좋다.

## 관련 용어
[[용어 모음집/CFS|CFS]], [[용어 모음집/스케줄링|스케줄링]], [[용어 모음집/SCHED_OTHER|SCHED_OTHER]], [[용어 모음집/응답 시간|응답 시간]]
