# 스케줄링 정책과 현대 OS

## 한 줄 정의
[[용어 모음집/CPU|CPU]] [[용어 모음집/스케줄링|스케줄링]] 정책은 **준비 큐에 있는 [[용어 모음집/프로세스|프로세스]]나 [[용어 모음집/스레드|스레드]] 중 누구에게 CPU를 줄지 결정하는 기준**이다.

예전 교과서에서는 FCFS, SJF, RR, Priority를 먼저 배우지만, 실제 현대 운영체제는 이 알고리즘을 그대로 하나만 쓰기보다 **공정성, 우선순위, 선점, 실시간 보장, CPU 그룹 제한**을 섞어서 사용한다.

---

## 교과서 기본 정책

| 정책                     | 선택 기준               | 선점 여부   | 장점                     | 주의점                                 |
| ---------------------- | ------------------- | ------- | ---------------------- | ----------------------------------- |
| [[용어 모음집/FCFS]]        | 먼저 도착한 작업           | 보통 비선점형 | 구현이 단순함                | 긴 작업이 앞을 막는 convoy effect           |
| [[용어 모음집/SJF]]         | 예상 실행 시간이 짧은 작업     | 보통 비선점형 | 평균 [[용어 모음집/대기 시간]] 감소 | 실행 시간 예측 어려움, [[용어 모음집/Starvation]] |
| SRTF                   | 남은 실행 시간이 짧은 작업     | 선점형     | SJF보다 응답성 개선           | 남은 시간 예측 필요                         |
| [[용어 모음집/Round Robin]] | 일정 time quantum 순환  | 선점형     | 응답성, 공정성 좋음            | quantum이 너무 작으면 [[용어 모음집/문맥 교환]] 증가 |
| [[용어 모음집/우선순위 스케줄링]]   | 우선순위 높은 작업          | 둘 다 가능  | 중요한 작업 우선 처리           | 낮은 우선순위 작업 starvation               |
| [[용어 모음집/MLFQ]]        | 여러 우선순위 큐와 동적 승격/강등 | 선점형     | 대화형 작업에 유리             | 규칙이 복잡함                             |

---

## FCFS
[[용어 모음집/FCFS|FCFS]](First-Come, First-Served)는 먼저 온 작업을 먼저 실행한다.

### 예시
```text
작업 A: 10ms
작업 B: 1ms
작업 C: 1ms

도착 순서가 A -> B -> C이면:
A가 10ms를 다 쓴 뒤에야 B, C가 실행된다.
```

### 바로 이해하기
- 은행 창구에서 먼저 온 사람부터 처리하는 방식이다.
- 단순하지만, 앞사람 일이 너무 길면 뒤의 짧은 일도 같이 밀린다.

### 자주 하는 실수
- FCFS를 무조건 공정하다고 생각함
  - 바로잡기: 도착 순서는 공정해 보이지만, 짧은 작업 입장에서는 긴 작업 때문에 오래 기다릴 수 있다.

---

## SJF와 SRTF
[[용어 모음집/SJF|SJF]](Shortest Job First)는 실행 시간이 가장 짧을 것으로 예상되는 작업을 먼저 실행한다. SRTF(Shortest Remaining Time First)는 SJF의 선점형 버전으로, 새로 온 작업의 남은 시간이 더 짧으면 현재 작업을 빼앗을 수 있다.

### 예시
```text
작업 A: 8ms
작업 B: 2ms
작업 C: 1ms

SJF는 C -> B -> A 순서가 평균 대기 시간을 줄이는 데 유리하다.
```

### 사용 조건
- 각 작업의 CPU burst를 어느 정도 예측할 수 있어야 한다.
- 실제 OS에서는 미래 실행 시간을 정확히 알 수 없으므로 과거 CPU 사용 패턴으로 추정한다.

### 자주 하는 실수
- SJF가 항상 현실적으로 최선이라고 생각함
  - 바로잡기: 평균 대기 시간 관점에서는 좋지만, 실행 시간 예측이 어렵고 긴 작업이 계속 밀릴 수 있다.

---

## Round Robin
[[용어 모음집/Round Robin|Round Robin]]은 각 작업에 time quantum을 주고, 시간이 끝나면 다음 작업으로 넘긴다.

### 예시
```text
time quantum = 4ms

A 4ms 실행 -> B 4ms 실행 -> C 4ms 실행 -> A 다시 실행
```

### quantum 크기
| quantum | 결과 |
|---|---|
| 너무 작음 | 문맥 교환이 너무 자주 일어나 CPU 시간이 낭비된다. |
| 적당함 | 응답성과 오버헤드 사이의 균형을 잡는다. |
| 너무 큼 | FCFS처럼 한 작업이 오래 CPU를 잡는다. |

### 자주 하는 실수
- quantum을 작게 할수록 무조건 좋다고 생각함
  - 바로잡기: 응답 시간은 좋아질 수 있지만 문맥 교환 비용 때문에 전체 처리량이 떨어질 수 있다.

---

## Priority Scheduling
[[용어 모음집/우선순위 스케줄링|Priority Scheduling]]은 우선순위가 높은 작업을 먼저 실행한다.

### 예시
```text
긴급 알림 처리 스레드: 높은 우선순위
동영상 인코딩 스레드: 낮은 우선순위

긴급 알림이 들어오면 인코딩보다 먼저 CPU를 받는다.
```

### 보완책
- [[용어 모음집/Starvation|starvation]]을 막기 위해 오래 기다린 작업의 우선순위를 올리는 aging을 쓴다.
- 높은 우선순위 스레드가 낮은 우선순위 스레드가 가진 락을 기다릴 때는 priority inversion 문제가 생길 수 있다.

---

## MLFQ
[[용어 모음집/MLFQ|MLFQ]](Multi-Level Feedback Queue)는 여러 개의 우선순위 큐를 두고, 작업의 행동에 따라 큐를 옮긴다.

### 기본 아이디어
- 처음 들어온 작업은 높은 우선순위 큐에서 시작한다.
- CPU를 오래 쓰면 CPU-bound 작업으로 보고 낮은 큐로 내린다.
- 짧게 실행하고 I/O 대기를 자주 하면 interactive 작업으로 보고 높은 우선순위를 유지할 수 있다.
- 너무 오래 기다린 작업은 starvation 방지를 위해 다시 올릴 수 있다.

### 예시
```text
Q0: 높은 우선순위, 짧은 quantum
Q1: 중간 우선순위, 중간 quantum
Q2: 낮은 우선순위, 긴 quantum

사용자 입력 처리처럼 짧게 자주 깨어나는 작업은 Q0에 머물기 쉽고,
긴 계산 작업은 점점 Q2로 내려갈 수 있다.
```

---

## Linux에서 실제로 보는 정책

| Linux 정책 | 용도 | 핵심 |
|---|---|---|
| [[용어 모음집/SCHED_OTHER]] 또는 SCHED_NORMAL | 일반 프로세스 | 기본 시분할 정책 |
| SCHED_BATCH | 배치 작업 | 상호작용성보다 처리량 |
| SCHED_IDLE | 매우 낮은 중요도 작업 | CPU가 남을 때 실행 |
| [[용어 모음집/SCHED_FIFO]] | 실시간 작업 | 같은 우선순위에서는 스스로 양보하거나 막힐 때까지 실행 |
| [[용어 모음집/SCHED_RR]] | 실시간 작업 | 같은 우선순위 안에서 round-robin |
| [[용어 모음집/SCHED_DEADLINE]] | deadline 기반 실시간 작업 | runtime, deadline, period로 보장량을 표현 |

### CFS와 EEVDF
[[용어 모음집/CFS|CFS]](Completely Fair Scheduler)는 오래 실행을 덜 받은 작업을 고르는 방식으로 일반 작업 사이의 공정성을 맞춘다. Linux 6.6부터는 일반 작업 스케줄링이 [[용어 모음집/EEVDF|EEVDF]] 방향으로 전환되었고, EEVDF는 각 작업의 lag와 virtual deadline을 이용해 공정성과 지연 시간 개선을 함께 노린다.

```text
CFS 관점:
CPU를 덜 받은 작업을 먼저 실행해서 공정성을 맞춘다.

EEVDF 관점:
CPU를 받을 자격이 있는 작업 중 virtual deadline이 가장 빠른 작업을 고른다.
```

### cgroup CPU 제한
컨테이너나 서버에서는 개별 프로세스만이 아니라 [[용어 모음집/cgroup|cgroup]] 단위로 CPU 몫을 제한한다. 예를 들어 어떤 컨테이너에 CPU quota를 50%로 걸면, 그 안의 스레드가 아무리 많아도 그룹 전체가 일정 기간 안에서 정해진 CPU 시간 이상을 쓰지 못한다.

---

## Windows에서 실제로 보는 방식
Windows는 스레드마다 우선순위를 두고, 높은 우선순위의 실행 가능한 스레드를 먼저 고른다. 같은 우선순위 안에서는 time slice를 나누어 round-robin처럼 실행한다.

### 핵심 구조
- 프로세스는 priority class를 가진다.
- 스레드는 thread priority를 가진다.
- 둘을 합쳐 스레드의 base priority가 정해진다.
- I/O 완료나 사용자 입력처럼 반응성이 중요한 상황에서는 동적 priority boost가 적용될 수 있다.

### 예시
```text
UI 입력 스레드: 상대적으로 높은 우선순위
백그라운드 압축 스레드: 낮은 우선순위

사용자가 마우스를 움직이거나 키를 누르면 UI 스레드가 먼저 CPU를 받아 반응성을 유지한다.
```

### 주의점
- REALTIME_PRIORITY_CLASS는 일반 앱에서 거의 쓰면 안 된다.
- 너무 높은 우선순위 스레드가 CPU를 계속 잡으면 입력, 디스크 flush, 시스템 스레드가 방해받을 수 있다.

---

## 정책 선택 기준

| 상황 | 더 중요한 목표 | 어울리는 방향 |
|---|---|---|
| 대화형 UI | 짧은 응답 시간 | RR, 동적 우선순위, MLFQ 계열 |
| 배치 처리 | 처리량, 평균 완료 시간 | SJF 추정, batch 정책 |
| 일반 서버 | 공정성, 처리량, 지연 시간 균형 | CFS/EEVDF, cgroup 제한 |
| 컨테이너 환경 | 그룹별 CPU 격리 | cgroup CPU quota/share |
| [[용어 모음집/실시간 시스템|실시간 제어]] | deadline, 예측 가능성 | SCHED_FIFO, SCHED_RR, SCHED_DEADLINE |

---

## 면접 포인트
- 교과서 알고리즘은 스케줄링의 기준을 이해하기 위한 모델이다.
- 실제 OS는 하나의 알고리즘만 쓰지 않고, 일반 작업/실시간 작업/배치 작업/컨테이너 그룹을 나누어 다룬다.
- Linux 일반 작업은 전통적으로 CFS를 배웠지만, 최근 커널은 EEVDF 기반으로 바뀌는 흐름을 알아두면 좋다.
- Windows는 우선순위 기반 선점 스케줄링이며, 같은 우선순위에서는 time slice를 나누어 실행한다.
- 스케줄링은 응답 시간, 처리량, 공정성, starvation, 문맥 교환 비용 사이의 트레이드오프다.

## 더 깊게 보기
- [[02_스케줄링]]
- [[03_실시간 시스템]]
- [[02_응답 시간 대기 시간 처리량]]
- [[용어 모음집/CFS|CFS]]
- [[용어 모음집/EEVDF|EEVDF]]
- [[용어 모음집/SCHED_DEADLINE|SCHED_DEADLINE]]

## 참고
- [Linux Kernel Documentation - CFS Scheduler](https://docs.kernel.org/scheduler/sched-design-CFS.html)
- [Linux Kernel Documentation - EEVDF Scheduler](https://docs.kernel.org/next/scheduler/sched-eevdf.html)
- [Linux Kernel Documentation - Deadline Task Scheduling](https://www.kernel.org/doc/html/latest/scheduler/sched-deadline.html)
- [Linux man-pages - sched(7)](https://www.man7.org/linux/man-pages/man7/sched.7.html)
- [Microsoft Learn - Scheduling Priorities](https://learn.microsoft.com/en-us/windows/win32/procthread/scheduling-priorities)
