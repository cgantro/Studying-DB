# Redis

## 목차
- [[CS공부/프레임워크/Redis/01_Redis(면접 DB 13) 개념정리]]

## 핵심
- 인메모리 데이터 저장소, 저지연 접근
- 캐시/세션/분산락/카운터 용도로 널리 사용

## 실무 패턴
- cache-aside
- write-through/write-behind(요건 따라 선택)
- TTL 기반 만료 + 이벤트 기반 무효화 조합

## 주의점
- 캐시 스탬피드
- 핫키 편중
- 메모리 eviction 정책 오설정

