# 스티커(STICKY) - CI/CD/배포 구조

## 배포 흐름(문서 기준)
- MR: Server 변경 시에만 backend build/test
- develop push: staging 배포
- main push: prod 배포
- 단일 EC2 듀얼 스택:
  - compose 프로젝트명으로 `sticker-staging`, `sticker-prod` 분리
  - Traefik edge 스택(`sticker-edge`)이 호스트 기반으로 라우팅

## 선택 이유
- staging/prod를 같은 서버에 두면 비용/운영 부담이 줄어든다.
- 대신 “환경 변수/리소스/라우팅”을 강하게 분리하는 가드레일이 필수다.

## 대안
- 환경별 EC2 분리:
  - 장점: 격리 쉬움
  - 단점: 비용↑, 운영 대상↑
- k8s:
  - 장점: 선언적 배포/오토스케일 등
  - 단점: 학습/운영 복잡도↑ (현재 단계에서 과투자 가능)

