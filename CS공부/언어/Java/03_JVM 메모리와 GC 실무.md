# JVM 메모리와 GC 실무

## 메모리 영역
- Heap: 객체 저장
- Stack: 메서드 호출/지역 변수
- Metaspace: 클래스 메타데이터

## GC 핵심
- Young/Old 영역 특성에 맞춘 수집 전략이 필요
- GC pause는 평균보다 p95/p99 지연에 영향이 크다.

## 실무 지표
- GC pause time
- allocation rate
- old gen usage
- full GC 빈도

## 운영 팁
- 힙 크기 증설 전에 객체 수명/할당 패턴을 먼저 본다.
- GC 로그를 상시 수집해 배포 전후 변화량을 비교한다.
