# ACID와 commit rollback

## ACID
- Atomicity: 전부 성공 또는 전부 실패
- Consistency: 제약조건을 지키는 상태로 전이
- Isolation: 동시 실행 간 간섭 제어
- Durability: 커밋 결과는 장애 후에도 보존

## commit/rollback
- commit: 변경 확정
- rollback: 트랜잭션 시작 이전 상태로 복구

## 실무 팁
- 트랜잭션 범위를 짧게 유지
- 외부 API 호출은 트랜잭션 밖으로 분리
- 장애 복구를 위해 idempotency 키 사용
