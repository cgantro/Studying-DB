# CFS

## 정의
CFS(Completely Fair Scheduler)는 Linux에서 일반 작업을 공정하게 실행하기 위해 사용된 CPU 스케줄러다. 각 작업이 CPU를 얼마나 받았는지를 virtual runtime으로 추적하고, 상대적으로 CPU를 덜 받은 작업을 우선 실행한다.

## 사용 환경
일반 사용자 프로세스와 서버 프로세스처럼 특별한 실시간 보장이 필요 없는 작업을 스케줄링할 때 사용된다.

## 사용 조건
작업별 실행 시간, nice 값, run queue, virtual runtime 같은 정보가 필요하다. 우선순위가 높은 실시간 정책이 runnable 상태이면 일반 CFS 작업보다 먼저 실행될 수 있다.

## 예시
동일한 우선순위의 작업 A와 B가 있으면 둘이 CPU 시간을 비슷하게 나눠 갖도록 조정한다. A가 CPU를 많이 썼다면 A의 virtual runtime이 커지고, B가 다음에 선택될 가능성이 높아진다.

## 주의점
- CFS는 단순 Round Robin이 아니다.
- 같은 시간 조각을 기계적으로 돌리는 것이 아니라, CPU 사용량의 공정성을 기준으로 선택한다.
- 최근 Linux 일반 작업 스케줄링은 [[용어 모음집/EEVDF|EEVDF]] 방향으로 발전하고 있다.

## 관련 용어
[[용어 모음집/스케줄링|스케줄링]], [[용어 모음집/EEVDF|EEVDF]], [[용어 모음집/SCHED_OTHER|SCHED_OTHER]], [[용어 모음집/cgroup|cgroup]], [[용어 모음집/CPU|CPU]]
