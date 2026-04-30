# 자동설정과 Starter

## 자동설정 원리
- classpath, property, bean 조건(`@Conditional...`)으로 빈을 자동 등록한다.
- `spring-boot-autoconfigure`의 조건 매칭 결과가 핵심이다.

## Starter
- `spring-boot-starter-*`로 의존성 묶음을 표준화한다.
- 버전 호환성은 BOM이 관리한다.

## override 전략
- 커스텀 빈 등록
- `@Primary`, `@Qualifier`
- `application.yml` 설정

## 실무 포인트
- 문제 발생 시 Condition Evaluation Report를 먼저 확인한다.
