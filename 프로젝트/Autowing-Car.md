# Autowing Car

## 한 줄 정의
자율주행 견인차 관제에서 MQTT-웹 브릿지, 인증, 인프라 자동화를 함께 설계한 실시간 백엔드 프로젝트.

## 내 역할
- Backend + DevOps
- Spring Boot, MQTT, WebSocket, Redis, JPA
- GitLab CI/CD, Docker, Nginx Reverse Proxy, EC2 배포

## 핵심 구조
- 차량(IoT) -> MQTT -> Spring Integration
- 서버 내부 이벤트 변환 -> WebSocket(STOMP) 브로드캐스트
- API/Auth/JWT + RefreshToken(Redis)
- PostgreSQL(H2 로컬) + 도메인 로직(Mission/TowingCar)

## 기술 선정 이유
- MQTT: 임베디드/저오버헤드 메시징
- WebSocket: 관제 웹의 실시간 상태 동기화
- Redis: 토큰/상태 캐시 및 저지연 조회
- Spring Boot: 빠른 API/보안/통합 구성

## 개선 경험
### 1) 502/500 네트워크 장애
- 원인: 컨테이너 네트워크 분리, localhost 바인딩
- 해결: 공통 Docker Network + 0.0.0.0 바인딩 + upstream DNS 고정
- 결과: 요청 경로 안정화

### 2) 프로세스 권한 흐름 재설계
- 기존: 기장 직접 경로 선택
- 개선: 기장 요청 -> 시스템 추천 -> 관제 승인
- 결과: 안전성/운영성 강화

### 3) 데이터 무결성/매핑 이슈
- 이슈: Mission.flight null, JSON 변환 오류
- 해결: DTO 필드 보강 + 엔티티 조회 매핑 + 직렬화 규약 정리

## CS 연결
- 네트워크: MQTT, WebSocket, TCP/UDP 선택, reverse proxy
- 데이터베이스: 트랜잭션, FK 무결성, 인덱스/쿼리
- 소프트웨어공학: CI/CD, 모듈 분리, 운영 관측
