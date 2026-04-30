# Autowing-Car

진행 상태: 진행 중
시작일: 2026년 1월 12일
종료일: 2026년 2월 6일
기술 스택: AWS EC2, Java, MQTT, Spring Boot, WebSocket
팀원 수: 6

## **🚗 자율주행 견인차 관제 시스템 (Autowing Car) - Backend & DevOps 담당**

## **📌 프로젝트 개요**

자율주행 견인차량(Autowing Car)과 관제 센터(ATC) 간의 실시간 통신 및 명령 제어를 위한 백엔드 및 인프라 구축 프로젝트입니다.

## **👨‍💻 주요 기여 (Role: Backend / DevOps)**

**ID:** `yoonpyo` / `홍윤표`

### **1. MSA 지향 인프라 아키텍처 및 CI/CD 파이프라인 구축**

- **기술 스택:** `GitLab CI`, `Docker`, `Nginx`, `EC2`, `Shell Script`
- **성과:** Repository 통합 관리 환경(Monorepo)에서 Backend, Frontend, AI, Embedded 각 모듈별 **조건부 CI/CD 파이프라인**을 설계하여 불필요한 빌드 시간을 단축함.
- **상세 내용:**
    - `Docker-in-Docker(DinD)` 기반의 컨테이너 빌드 자동화 및 Docker Hub 이미지 배포.
    - **Nginx Reverse Proxy**를 도입하여 SSL/TLS(LetsEncrypt) 적용 및 API(`/api`), WebSocket(`/ws-server`), Frontend 정적 파일(`/`) 라우팅 단일화.
    - EC2 배포 스크립트(`deploy.env` 주입, Docker Network 설정) 자동화로 **무중단 배포 초석 마련**.

### **2. 초저지연 실시간 관제 통신 시스템 (MQTT + WebSocket)**

- **기술 스택:** `Spring Boot`, `Spring Integration MQTT`, `STOMP`, `Redis`
- **성과:** 차량(IoT) ↔ 서버 ↔ 관제 웹(Frontend) 간의 **이종 프로토콜 브릿징** 구현.
- **상세 내용:**
    - **MQTT Inbound Adapter** 구현: 임베디드 차량의 텔레메트리(위치, 배터리, 상태) 데이터를 수신하여 실시간으로 파싱.
    - **WebSocket(STOMP) 브로드캐스팅**: 수신된 MQTT 데이터를 Spring Event로 변환 후, 구독 중인 관제 웹 클라이언트에게 즉시 전송(`SimpMessagingTemplate`).
    - **CoTURN(TURN Server) 구축**: WebRTC 영상 스트리밍을 위한 ICE Candidate 생성 및 미디어 릴레이 서버 컨테이너화 배포.

### **3. 보안 인증 시스템 (Custom JWT & Security)**

- **기술 스택:** `Spring Security`, `JWT`, `Bcrypt`
- **성과:** API 요청뿐만 아니라 **WebSocket 연결에 대한 보안 인증** 체계 수립.
- **상세 내용:**
    - 표준 `Authorization: Bearer` 토큰 인증 필터 체인 구현.
    - **WebSocket 핸드셰이크 보안**: `StompHandler` 인터셉터를 통해 소켓 연결 시 JWT 유효성 검증 로직 추가 (일반 Access Token과 Socket Token의 분리 운영).
    - Redis를 활용한 **RefreshToken 저장소** 운영으로 로그아웃 및 토큰 재발급 로직 최적화.

### **4. 도메인 로직 설계 및 데이터 무결성 강화**

- **기술 스택:** `JPA (Hibernate)`, `PostgreSQL / H2`
- **상세 내용:**
    - **Entity 구조 리팩토링**: 초기 `create-drop`으로 인한 데이터 유실 문제를 해결하기 위해 `InitData` 스크립트 도입 및 연관관계 매핑 최적화.
    - `TowingCar` 및 `Mission` 도메인의 비즈니스 로직(배차, 미션 생성, 상태 변경) 구현.
    - **트러블슈팅**: H2/PostgreSQL 방언(Dialect) 차이로 인한 예약어 충돌 문제(**User** 테이블 등) 해결 및 Docker Network 통신 장애(502 Bad Gateway) 디버깅 주도.

## **🛠️ 트러블슈팅 경험 (대표 사례)**

### **💥 이슈: Docker Container Network 간 502/500 에러**

- **현상:** Nginx 컨테이너에서 Backend로 요청 시 `Connection Refused` 발생.
- **원인:** Spring Boot가 컨테이너 내부의 `localhost(127.0.0.1)`에만 바인딩되거나, Nginx와 Backend가 서로 다른 Docker Network(`app-net` vs `default`)에 존재함.
- **해결:**
    1. Docker Network(`app-net`)를 생성하여 모든 컨테이너(Nginx, Backend, Redis, CoTURN)를 동일 네트워크로 그룹화.
    2. Backend Listen Address를 `0.0.0.0`으로 보장하고, Nginx Upstream 설정을 `http://backend-app:8080`과 같이 컨테이너 DNS로 변경하여 해결.

---

**💡 한 줄 요약:** 인프라(DevOps)부터 백엔드 코어(Auth, MQTT/WebSocket), 데이터베이스 설계까지 **서비스의 E2E(End-to-End) 흐름을 모두 설계하고 구현**함.

## 📝 [Project Log] Autowing 관제 시스템 백엔드 개발 일지(~1.22)

## 1. 개발 개요

- **목표:** 기장(Pilot)의 요청부터 관제사(Admin)의 승인, 그리고 로봇(TowingCar)의 실제 주행 명령(MQTT)까지 이어지는 전체 파이프라인 구축.
- **핵심 기술:** Spring Boot, WebSocket (STOMP), MQTT (Mosquitto), JPA, Javascript (Test Client).

---

## 2. 시행착오 (Trial & Error)

### ① 프로세스 설계의 오류 수정 (권한 흐름)

- **문제:** 초기에는 기장이 경로를 직접 선택하는 방식이었으나, 실제 항공 관제 프로세스와 맞지 않음.
- **수정:** **[기장 요청] → [시스템 분석/추천] → [관제사 최종 승인] → [로봇 배차]** 순서로 로직을 전면 재설계. 관제사가 '슈퍼맨'이 되어 최종 권한을 갖도록 변경함.

### ② `AnonymousPilot` 식별 문제 (WebSocket 인증)

- **증상:** 기장이 요청을 보내도 서버 로그에 `AnonymousPilot`으로 찍히고, 승인 결과 알림(User Destination)을 받지 못함.
- **원인:** Spring Security 없이 WebSocket을 연결할 때, `Principal` 객체가 생성되지 않아 특정 유저에게 메시지를 보낼 수 없음.
- **해결:** `WebSocketConfig`에 **ChannelInterceptor**를 구현. 클라이언트가 `CONNECT` 시 헤더에 담아 보낸 `login` 정보를 가로채 강제로 `Principal`을 주입하는 로직 추가.

### ③ 데이터 무결성 위반 (`DataIntegrityViolationException`)

- **증상:** 미션 생성 시 `not-null property references a null... Mission.flight` 에러 발생.
- **원인:** DB 설계상 `Mission`은 반드시 `Flight`(항공편) 정보가 필요한데, DTO에서 누락됨.
- **해결:**
    1. `PilotRequestDto`에 `flightId` 필드 추가.
    2. `MissionService`에서 `FlightRepository`를 통해 엔티티 조회 후 매핑.
    3. 테스트 클라이언트에서도 필수값 전송하도록 수정.

### ④ JSON 파싱 및 컨버터 오류 (`JpaSystemException`)

- **증상:** `routeEdgeIds` (경로 리스트) 저장/조회 시 `MismatchedInputException` 발생.
- **원인:** `StringListConverter`가 DB에 저장된 JSON 문자열을 `List<String>`으로 변환하는 과정에서, 입력값이 올바른 JSON Array 형식이 아니거나 이중 파싱 시도.
- **해결:** 테스트 클라이언트에서 경로 데이터를 단순 문자열이 아닌 **JSON Array (`["E1", "E2"]`)** 형태로 정확히 직렬화하여 전송하도록 수정.

### ⑤ 비즈니스 로직 누락으로 인한 로그 중단

- **증상:** 기장 요청 후 DB 조회 로그(`select ...`)에서 서버 동작이 멈춤. 관제사에게 알림이 가지 않음.
- **원인:** `MissionService` 메서드가 실제 구현체 없이 껍데기만 존재했거나, `webSocketService` 호출 코드가 누락됨.
- **해결:** DB 저장 후 즉시 `webSocketService.notifyAdminRequest()`를 호출하여 관제사에게 데이터를 밀어주는(Push) 로직 완성.

---

## 3. 주요 고민 및 의사결정 (Deliberation)

### Q1. 로봇과 프론트엔드 통신을 어떻게 분리할 것인가?

- **고민:** 로봇(임베디드)은 MQTT가 표준이고, 웹 관제 화면은 WebSocket이 적합함. 이 둘을 어떻게 유기적으로 연결할지 고민.
- **결정:**
    - **Inbound (로봇 → 서버):** MQTT로 들어온 데이터를 `MqttInboundHandler`가 받아 `RobotSignalProcessor`를 통해 파싱 후, DB 저장과 동시에 WebSocket으로 브로드캐스팅(실시간 모니터링).
    - **Outbound (서버 → 로봇):** 관제사가 승인 버튼을 누르는 즉시 `MqttOutboundService`를 통해 로봇에게 명령 JSON 전송.
    - **결론:** 서버가 **Protocol Bridge** 역할을 수행하여 이기종 프로토콜 간의 통신을 중개함.

### Q2. 테스트 데이터 관리 전략

- **고민:** 로컬 개발 시마다 H2 DB가 초기화되어 `Node`, `Edge` 등 연관관계가 복잡한 데이터를 매번 넣기 번거로움.
- **결정:** `data.sql` 대신 **`CommandLineRunner` (Java Code)** 방식을 채택.
    - *이유:* `Edge` 생성 시 `Node`의 ID(FK)를 알아야 하는데, SQL 스크립트는 ID를 하드코딩해야 해서 관리가 어려움. 자바 코드로 객체를 생성해 연결(`edge.setSrcNode(node1)`)하는 것이 유지보수에 유리함.

### Q3. 테스트 효율성 증대

- **고민:** 백엔드 개발 시 프론트엔드 없이 복잡한 시나리오(요청->승인->제어)를 검증하기 어려움. 매번 ID를 찾아 입력하는 비효율 발생.
- **결정:** **기능성 테스트 클라이언트(HTML/JS)** 자체 제작.
    - 서버 응답을 구독하여 미션 ID, 차량 코드 등을 **자동으로 입력창에 채워주는(Auto-fill)** 기능 구현. 이를 통해 테스트 시간을 획기적으로 단축.

---

## 4. 향후 계획 (Next Steps)

- **경로 탐색 알고리즘 적용:** 현재 MockData로 들어가는 경로를 실제 `A* 알고리즘` 기반의 `PathFindingService`로 교체.
- **예외 처리 고도화:** 로봇 통신 단절(Timeout)이나 배차 실패 시에 대한 보상 트랜잭션 로직 추가.
- **보안 강화:** 현재 인터셉터 방식의 간단한 인증을 JWT 기반의 Spring Security로 고도화 필요.

---

## 일지 2

## 1. 시스템 아키텍처 설계 (Architecture)

### 🏗️ 하이브리드 통신 아키텍처 구축

일반적인 웹 서비스(REST API)와 달리, 로봇 제어와 실시간 관제를 위해 **세 가지 통신 프로토콜**을 혼합하여 설계함.

1. **REST API:** 정적인 데이터 조회 (로그인, 이력 조회)
2. **WebSocket (STOMP):** 관제사(Web)와 기장(App) 간의 초저지연 상태 동기화 & 푸시 알림.
3. **MQTT:** 하드웨어(로봇)와의 경량 메시징 통신.

> 💡 핵심 설계 의도 (Protocol Bridge):
로봇은 웹소켓을 모르고, 웹 클라이언트는 MQTT를 직접 구독하기 어렵다.
따라서 Spring Boot 서버가 "중계소(Bridge)" 역할을 수행하여, MQTT로 들어온 로봇의 위치 정보를 WebSocket으로 변환해 관제 화면에 뿌려주는 구조를 채택함.
> 

---

## 2. 도메인 모델링 및 DB 설계 (Domain Logic)

### ① 맵(Map) 데이터 - Node & Edge

- **구현:** 공항 지도를 그래프 자료구조로 모델링.
    - `Node`: 좌표(x, y)와 타입(GATE, RUNWAY, TAXIWAY) 저장.
    - `Edge`: 두 노드 간의 연결 정보(`srcNode`, `dstNode`)와 거리(가중치) 저장.
- **고민했던 점:**
    - 단순히 좌표만 저장할 것인가, 관계를 맺을 것인가?
    - ➡ 향후 *A 경로 탐색 알고리즘*적용을 위해 JPA 연관관계(`@ManyToOne`)로 노드 간 연결성을 명시함.

### ② 임무(Mission) 라이프사이클 관리

- **구현:** 항공기 견인 요청부터 완료까지의 상태 전이 관리.
    - `Status Enum`: `WAITING` (대기) → `RUNWAY` (주행중) → `COMPLETED` (완료)
- **시행착오 (오늘 수정된 핵심):**
    - *초기 설계:* 기장이 경로를 선택하고 차량을 호출함.
    - *문제점:* 기장은 공항의 트래픽 상황을 모름. 사고 위험 존재.
    - *변경 설계:* **[기장 요청] → [시스템 추천] → [관제사 승인]** 구조로 변경하여 안전성 확보.

### ③ 차량(TowingCar) 및 주행 로그

- **구현:** 로봇의 실시간 상태(`IDLE`, `MOVING`, `ERROR`)와 배터리, 위치 관리.
- **데이터 처리:**
    - 로봇은 1초에 수십 번 위치를 보낼 수 있음.
    - 이를 매번 DB에 `Update` 치면 부하가 심함.
    - ➡ **Master 테이블(`TowingCar`)은 현재 상태만 갱신**하고, 이동 궤적은 **History 테이블(`DrivingLog`)에 쌓는 방식**으로 이원화.

---

## 3. 핵심 기능 구현 및 기술적 도전 (Key Challenges)

### 🚀 Challenge 1: 이기종 프로토콜 간 동기화

- **상황:** 로봇이 "나 출발해"라고 MQTT로 메시지를 보냄. 관제사 화면의 아이콘도 즉시 움직여야 함.
- **해결:** **`MqttInboundHandler`** 구현.
    - **Spring Integration**을 사용하여 MQTT 메시지를 수신.
    - 수신 즉시 **`SimpMessagingTemplate`**을 통해 WebSocket Topic(**`/topic/mission/updates`**)으로 재전송(Broadcasting).
    - 결과적으로 **하드웨어 신호가 웹 화면에 0.1초 내 반영**되는 실시간성 확보.

### 🔐 Challenge 2: WebSocket 사용자 식별 (Auth)

- **문제:** HTTP 요청과 달리 WebSocket은 연결이 지속되는데, "누가" 보낸 메시지인지 식별이 어려움 (**`Principal`**이 null).
- **해결:** **STOMP 인터셉터(**`ChannelInterceptor`**)** 도입.
    - **`CONNECT`** 프레임의 헤더(**`login: pilot_01`**)를 가로채서, Spring의 **`Principal`** 객체를 수동으로 생성 및 주입.
    - 이를 통해 **`convertAndSendToUser`** 같은 **개인화 메시지 전송(Private Queue)** 기능 구현 성공.

### 💾 Challenge 3: 복잡한 데이터 타입의 DB 매핑

- **문제:** 주행 경로(**`["E1", "E2", "E3"]`**)는 리스트 형태인데, RDB에 저장하기 까다로움.
- **시행착오:** **`AttributeConverter`**를 사용하여 JSON 문자열로 변환해 저장 시도.
    - *오류:* Jackson 라이브러리가 이중 직렬화(String 안에 String)를 시도하며 **`MismatchedInputException`** 발생.
    - *해결:* 클라이언트(Test UI)에서 전송 시 **엄격한 JSON Array 포맷**을 준수하도록 수정하고, 컨버터의 예외 처리를 강화함.

### 🛠 Challenge 4: 테스트 환경의 생산성

- **문제:** 로봇도 없고, 프론트엔드도 완성되지 않은 상태에서 백엔드 로직 검증이 불가능에 가까움.
- **해결:**
    1. **데이터 시딩:** **`LocalDataInit`**을 만들어 서버 실행 시 맵/차량 데이터를 메모리에 자동 로드.
    2. **통합 테스트 콘솔(HTML) 제작:** 기장과 관제사 역할을 동시에 수행하며 시나리오를 검증하는 도구 자체 제작.
        - *Auto-fill 기능:* 서버 응답값을 파싱해 다음 요청의 입력값으로 자동 채워주는 스크립트 작성으로 테스트 속도 500% 향상.

---

## 4. 향후 고도화 계획 (Roadmap)

1. *경로 탐색 알고리즘 (A / Dijkstra):*
    - 현재 Mock-up으로 되어 있는 경로 추천 로직을, `Edge`의 가중치(거리+트 혼잡도)를 계산하는 실제 알고리즘으로 대체.
2. **동시성 제어:**
    - 여러 관제사가 동시에 같은 차량을 배차하려 할 때 발생하는 Race Condition 방지 (Redis Lock 또는 DB Lock 고려).
3. **예외 상황 복구:**
    - 로봇이 주행 중 MQTT 연결이 끊겼을 때(Heartbeat Loss), 서버가 이를 감지하고 '통신 두절' 상태로 변경하는 로직 추가.

### 01.23 일지

### 1. 상태 동기화 전략: "DB vs MQTT Retain"

**🤔 고민:**

> "로봇의 상태(위치, 배터리 등)는 MQTT 브로커가 Retain 옵션으로 기억하고 있는데, 굳이 DB에 TowingCar 테이블을 만들어 중복 관리해야 하는가?"
> 

**💡 결정: Hybrid Approach (DB + MQTT)**

- **DB (`TowingCar` Entity) 사용 이유:**
    1. **동시성 제어 (Locking):** 관제사 A, B가 동시에 배차를 시도할 때, DB의 `Pessimistic Lock`(비관적 락) 없이는 **중복 배차** 사고를 막을 수 없음. MQTT는 락 기능이 없음.
    2. **복합 쿼리 (Business Logic):** "배터리 80% 이상이고 쉬고 있는(IDLE) 차 중 가장 가까운 차"를 찾으려면 SQL(`WHERE`, `ORDER BY`)이 필수임. MQTT는 단순 Key-Value 조회만 가능함.
    3. **무결성 (Integrity):** `Mission` 테이블과 `TowingCar`의 `FK(Foreign Key)` 관계를 통해 데이터의 정확성을 보장해야 함.
- **결론:** **"로직 판단(Control)"은 DB**를 기준으로 하고, **"단순 관제 화면(View)"은 MQTT**를 활용한다.

### 2. 성능 최적화: "Smart Update (Throttling)"

**🤔 고민:**

> "로봇이 1초에 10번(10Hz) 위치를 보내는데, 이걸 매번 DB에 UPDATE 하면 DB가 버틸 수 있는가?"
> 

**💡 결정: Event-Driven & Throttling (이벤트 기반 및 스로틀링)**

- **문제점:** 무지성 업데이트 시, 로봇 100대 기준 초당 1,000 TPS 발생 → DB 부하 폭증.
- **해결책 (`TowingCarService`):**
    1. **Critical Change (즉시 반영):** 상태가 `IDLE` ↔ `MOVING`으로 변하거나, 에러가 발생하면 **즉시 DB 저장**. (반응성 보장)
    2. **Minor Change (지연 반영):** 단순히 좌표(`x`, `y`)나 배터리가 조금 변한 건 **3초에 한 번만 저장** (또는 변화폭이 클 때만).
- **효과:** 데이터 정합성은 유지하면서 **DB 쓰기(Write) 부하를 약 90% 이상 절감**.

### 3. 트랜잭션 안전성: "DB Commit 후 MQTT 발송"

**🤔 고민:**

> "미션 승인 로직에서 DB INSERT 후 로봇에게 MQTT 명령을 보냈는데, DB 트랜잭션이 마지막에 실패(Rollback)하면? 로봇은 출발했는데 시스템엔 기록이 없는 '유령 미션'이 발생한다."
> 

**💡 결정: Transaction Synchronization**

- **문제점:** 외부 시스템(MQTT, Kafka 등) 호출은 트랜잭션 롤백이 불가능함.
- **해결책 (`MissionService`):**
    - `TransactionSynchronizationManager.registerSynchronization`을 사용하여 **DB 커밋이 완전히 성공한 직후(`afterCommit`)**에만 MQTT 메시지를 발송하도록 스케줄링.
- **효과:** 데이터 불일치(Inconsistency) 원천 차단.

### 4. 추적성(Traceability): "Mission Log 도입"

**🤔 고민:**

> "시스템이 복잡해질수록 '누가' 명령을 내렸고, '언제' 상태가 변했는지 이력을 추적하기 힘들다. 현재 상태만 있는 Mission 테이블로는 부족하다."
> 

**💡 결정: Audit Log 분리**

- **해결책:** `MissionLog` 엔티티 도입.
    - **행위자(Actor):** 기장(Pilot), 관제사(Admin), 혹은 시스템(System).
    - **행위(Action):** `REQUEST`(요청), `APPROVE`(승인), `Dispatch`(배차), `Moving`(이동), `Complete`(완료).
- **효과:** 사고 발생 시 원인 분석(Forensic) 가능, 운영 리포트 생성 기반 마련.

## 인프라