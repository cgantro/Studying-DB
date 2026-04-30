# Autowing Car

## 현재 상태
- **완료(시연/MVP 기준)** (autowing_Car 저장소 기준 마지막 커밋: `2026-02-09 +09:00`)
- 프로덕션 서비스 운영까지는 아님

## 한 줄 정의
스마트 토잉카(견인차) 관제에서 “MQTT 실시간 데이터 → 서버 도메인 처리 → WebSocket(STOMP) 브로드캐스트” 흐름과, JWT 인증/Redis 토큰, GitLab CI/CD 배포를 같이 만든 프로젝트.

## 내 역할
- (내 담당) Backend + DevOps (실시간 데이터 흐름/인증/배포 자동화)
- Spring Boot, MQTT(Spring Integration), WebSocket(STOMP), Redis, JPA
- GitLab CI/CD(Docker-in-Docker), EC2 배포 스크립트

## 핵심 구조
- 차량(IoT/AI) → MQTT → Backend(inbound)
- Backend 내부 이벤트/검증/상태 전이 → WebSocket topic broadcast
- 명령(Connect/Drive/Emergency 등) → Backend → MQTT(outbound)
- Auth: JWT + Refresh Token(Redis)

## 기술 선택 이유 + 대안/트레이드오프(요약)
- MQTT:
  - 선택: 임베디드 장치에 맞는 경량 pub/sub
  - 대안: Kafka/AMQP (운영 복잡도↑, 임베디드 친화도↓)
- WebSocket(STOMP):
  - 선택: 관제 웹 실시간 상태 동기화
  - 대안: SSE(단방향), polling(지연/부하↑)
- Redis Refresh Token:
  - 선택: 토큰 회수/TTL 관리
  - 대안: DB 저장(조회/쓰기 비용↑, 만료 관리 복잡)

## 문제 -> 원인 -> 해결 (요약)
### 1) GitLab CI에서 Docker-in-Docker 연결 실패
- 문제: Docker build/push 단계에서 2375 포트/TLS 관련 에러로 파이프라인이 깨짐
- 원인: dind 서비스 TLS 인증서 생성/통신 방식이 CI 컨테이너와 맞지 않음
- 해결: `DOCKER_TLS_CERTDIR=""`로 TLS 인증서 생성을 끄고 HTTP(2375) 통신을 강제

### 2) Docker/JAR 환경에서 “맵 파일 로딩”이 깨짐
- 문제: 로컬 경로 기반 파일 I/O가 컨테이너/JAR 배포에서 실패
- 원인: classpath 리소스와 외부 파일 시스템의 경로/권한/배포 방식이 다름
- 해결: classpath/file 후보를 수집해 로딩 + 외부 맵 우선 + 일부 메타데이터는 안전한 fallback 제공

### 3) 로그인 처리 비용(BCrypt)로 병목 가능성
- 문제: 동시 접속 증가 시 로그인 구간에서 CPU 병목 가능성
- 원인: BCrypt는 설계상 비용이 큰 해시
- 대응: MVP 조건에서는 strength를 낮춰 성능 실험이 가능하게 하고, 운영 전환 시에는 scale-out/rate limit 같은 운영 전략과 분리

## CS 연결
- 네트워크: pub/sub(MQTT), WebSocket, 실시간 상태 전파
- OS/성능: 병목 지점 분리(암호화 비용, 브로커/서버 부하)
- DB: 상태 전이/무결성, 트랜잭션 경계와 “커밋 후 외부 발행” 설계
- SW 공학: CI/CD, 환경 변수/프로파일 분리, 배포 형태(Docker/JAR)에 따른 설계 차이

## 상세 문서
- [00-상태-요약](Autowing-Car/00-상태-요약.md)
- [01-구조-흐름](Autowing-Car/01-구조-흐름.md)
- [02-CI-CD-배포-이슈](Autowing-Car/02-CI-CD-배포-이슈.md)
- [03-인증-세션-토큰](Autowing-Car/03-인증-세션-토큰.md)
- [04-맵-리소스-로딩-Docker-JAR](Autowing-Car/04-맵-리소스-로딩-Docker-JAR.md)

