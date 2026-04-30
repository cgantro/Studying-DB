# mm-bot (Mattermost + n8n RAG 봇)

## 현재 상태
- **진행중**
- 근거: mm-bot 저장소 마지막 커밋 `2026-04-18 (+09:00)`

## 한 줄 정의
Mattermost Slash Command를 트리거로 n8n에서 “의도 분류 → (실시간 MM 조회 또는 벡터 검색) → LLM 응답 → Mattermost 게시”까지 오케스트레이션하고, 배치 적재(OCR/임베딩) 파이프라인을 분리해 운영 리스크를 줄인 RAG 봇.

## 내 역할
- (내 담당) 전체 아키텍처 설계: 수집/저장/검색/응답 파이프라인 분리
- (내 담당) n8n 워크플로우 설계/운영: ask/summary/배치 적재, 스케줄/중복방지 규칙
- (내 담당) CI 배포 자동화: 워크플로우 JSON 병합/검증 후 n8n API로 업데이트

## 핵심 구조(요약)
- 데이터 수집:
  - Mattermost 채널 공지/식단 텍스트+이미지(OCR) → 문서 청크 → 임베딩 → pgvector 저장
- 질의 처리:
  - Slash Command(`/mattermost/ask`) → 의도 분류(`meal/domain_rag/general_chat`) → 검색/조회 → LLM → Mattermost 응답
- 인프라:
  - n8n(Oracle Cloud) + DB(로컬) 간은 사설 네트워크(Tailscale)로 연결하는 구조

## 문제 -> 원인 -> 해결 (요약)
### 1) Slash Command 응답 3초 제한
- 문제: RAG/LLM 처리는 3초 내에 끝나기 어렵다.
- 원인: Slash Command는 “즉시 응답”을 요구.
- 해결: webhook 수신 즉시 “처리 중...”을 반환하고, 후속으로 Mattermost API로 실제 답변을 POST.

### 2) 질의 경로에서 OCR/임베딩/쓰기까지 하면 느려지고 비용이 튄다
- 문제: 실시간 질의에 무거운 작업이 섞이면 latency와 실패율이 올라간다.
- 원인: OCR/임베딩/DB upsert는 I/O/CPU/외부 API 의존도가 크다.
- 해결: “질의 워크플로우”는 읽기 전용, “배치 적재 워크플로우”에서만 OCR/임베딩/쓰기 수행.

### 3) 워크플로우를 파일로 관리하면 배포/충돌이 잦다
- 문제: n8n UI에서 수정한 내용을 파일로 되돌리거나, 파일 병합 시 노드 충돌이 나기 쉽다.
- 원인: 노드 name/id 충돌, 연결(source/target) 불일치, UI 좌표 겹침.
- 해결: CI에서 ask+summary(+optional overlay) JSON을 병합하고, name/id/connection 검증 후 n8n API로 PUT 배포.

## CS 연결
- 네트워크/시스템: 비동기 처리(즉시 응답 + 후속 POST), 실패 격리(배치/질의 분리)
- 데이터: 중복 방지 키/업서트, 체크포인트(커서) 기반 적재
- SW 공학: 워크플로우를 “코드/아티팩트”로 관리하고 배포 전 검증을 자동화

## 상세 문서
- [00-상태-요약](mm-bot/00-상태-요약.md)
- [01-아키텍처-흐름](mm-bot/01-아키텍처-흐름.md)
- [02-슬래시-3초-제한-대응](mm-bot/02-슬래시-3초-제한-대응.md)
- [03-배치-적재-질의-분리](mm-bot/03-배치-적재-질의-분리.md)
- [04-n8n-워크플로우-CI-배포](mm-bot/04-n8n-워크플로우-CI-배포.md)

