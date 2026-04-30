# Autowing Car - CI/CD/배포 이슈

## 1) GitLab CI Docker-in-Docker 연결 실패
- 증상: Docker build/push 단계에서 2375 포트/TLS 관련 오류가 발생.
- 원인: `docker:dind`가 TLS 인증서 생성 모드로 올라가며 통신이 꼬임.
- 해결: CI 설정에서 `DOCKER_TLS_CERTDIR=""`로 TLS 인증서 생성을 끄고 HTTP(2375) 통신을 강제.
- 근거 위치: `Backend/.gitlab-ci.yml` 주석에 원인/해결이 명시되어 있음.

## 대안
- Kaniko/BuildKit 기반 빌드로 전환:
  - 장점: dind 의존성 감소, 보안/성능 이점
  - 단점: 셋업 비용, 캐시 정책 재설계 필요

## 2) 런타임 환경 변수/네트워크 의존성
- 배포 시 `deploy.env`로 MQTT/Redis/JWT/DB 같은 런타임 변수를 주입한다.
- 컨테이너 네트워크를 공용 네트워크로 묶지 않으면(예: `app-net`) Redis/Backend 간 통신이 깨질 수 있다.

