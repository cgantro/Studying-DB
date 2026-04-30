# 실행 계획과 EXPLAIN

## EXPLAIN 목적
- 옵티마이저가 어떤 접근 경로를 선택했는지 확인

## 봐야 할 항목
- Scan 타입(Seq/Index)
- 추정/실측 row 수
- join 방식
- cost/actual time

## 실무 포인트
- 추정 row와 실제 row 차이가 크면 통계/조건식 점검
- 느린 쿼리는 실행 계획 캡처를 릴리즈 아티팩트로 보관
