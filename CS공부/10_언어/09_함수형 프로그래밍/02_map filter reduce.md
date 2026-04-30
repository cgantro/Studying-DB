# map filter reduce

## map
- 컬렉션의 각 원소를 변환한다.

## filter
- 조건에 맞는 원소만 남긴다.

## reduce
- 컬렉션을 하나의 값으로 축약한다.

## 실무 패턴
- 로그 집계: filter(유효 이벤트) -> map(필드 추출) -> reduce(카운트/합계)
- 비용 계산: map(단가 적용) -> reduce(총합)

## 성능 포인트
- 중간 컬렉션 생성 비용 고려
- Java Stream 병렬화는 데이터 크기/연산 비용 기준으로 판단
