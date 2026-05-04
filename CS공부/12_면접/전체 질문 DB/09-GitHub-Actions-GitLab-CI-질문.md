# GitHub Actions / GitLab CI

## CI/CD 기본

1. CI와 CD의 차이는 무엇인가요?
    
2. CI/CD를 사용하는 이유는 무엇인가요?
    
3. Pipeline이란 무엇인가요?
    
4. CI에서 테스트를 자동화하는 이유는 무엇인가요?
    
5. PR 또는 MR 단위로 CI를 돌리는 이유는 무엇인가요?
    
6. main branch merge 후 CD를 돌리는 일반적인 이유는 무엇인가요?
    
7. CI 실패를 무시하면 어떤 문제가 생기나요?
    
8. Branch Protection 또는 Merge Rule은 왜 필요한가요?
    
9. Required Check가 필요한 이유는 무엇인가요?
    

## GitHub Actions

11. GitHub Actions의 Workflow란 무엇인가요?
    
12. `on: push`, `on: pull_request`의 차이는 무엇인가요?
    
13. Job과 Step의 차이는 무엇인가요?
    
14. Runner란 무엇인가요?
    
15. GitHub-hosted runner와 self-hosted runner의 차이는 무엇인가요?
    
16. Matrix build는 어떤 상황에서 사용하나요?
    
17. OS별 build matrix를 구성하는 이유는 무엇인가요?
    
18. `actions/checkout`은 어떤 역할을 하나요?
    
19. GitHub Actions에서 cache를 사용하는 이유는 무엇인가요?
    
20. Dependency cache와 build cache의 차이는 무엇인가요?
    
21. Cache key를 잘못 잡으면 어떤 문제가 생기나요?
    
22. GitHub Actions artifact는 어떤 용도로 사용하나요?
    
23. Secret과 Variable의 차이는 무엇인가요?
    
24. Secret을 로그에 출력하면 안 되는 이유는 무엇인가요?
    
25. Release workflow와 PR workflow를 분리하는 이유는 무엇인가요?
    

## GitLab CI

26. GitLab CI의 `.gitlab-ci.yml`은 어떤 역할을 하나요?
    
27. Stage와 Job의 차이는 무엇인가요?
    
28. GitLab Runner는 어떤 역할을 하나요?
    
29. Shared Runner와 Specific Runner의 차이는 무엇인가요?
    
30. Shell executor와 Docker executor의 차이는 무엇인가요?
    
31. GitLab CI에서 cache와 artifact의 차이는 무엇인가요?
    
32. `only`, `except`, `rules`는 어떤 용도로 사용하나요?
    
33. `needs`를 사용하는 이유는 무엇인가요?
    
34. Pipeline 병렬 실행은 어떤 장점이 있나요?
    
35. GitLab CI에서 manual job은 언제 사용하나요?
    

## Build / Test / Quality Gate

36. Java 프로젝트 CI에서 일반적으로 어떤 단계를 구성하나요?
    
37. Gradle build와 test를 분리하는 이유는 무엇인가요?
    
38. `./gradlew test`와 `./gradlew build`의 차이는 무엇인가요?
    
39. 정적 분석 도구를 CI에 넣는 이유는 무엇인가요?
    
40. SpotBugs, Checkstyle, PMD는 각각 어떤 성격의 도구인가요?
    
41. Dependency vulnerability scan은 왜 필요한가요?
    
42. CI에서 테스트가 로컬과 다르게 실패하는 이유는 무엇인가요?
    
43. 환경변수 누락으로 CI가 실패하는 경우를 어떻게 찾나요?
    
44. CI에서 DB나 Redis가 필요한 테스트는 어떻게 구성하나요?
    
45. Testcontainers는 어떤 상황에서 유용한가요?
    

## Docker / 배포 연동

46. CI에서 Docker image를 빌드하는 이유는 무엇인가요?
    
47. Docker image tag는 어떻게 설계하는 것이 좋나요?
    
48. `latest` 태그만 사용하는 것이 위험한 이유는 무엇인가요?
    
49. CI에서 Docker registry login은 어떻게 처리하나요?
    
50. 배포용 Secret은 어디에 보관해야 하나요?
    
51. 배포 단계에서 SSH를 사용할 때 주의할 점은 무엇인가요?
    
52. CI에서 운영 서버로 직접 배포하는 방식의 장단점은 무엇인가요?
    
53. Rollback 가능한 배포를 만들려면 무엇을 기록해야 하나요?
    
54. 배포 후 health check를 CI/CD에 넣는 이유는 무엇인가요?
    
55. 배포 성공 후에도 서비스가 죽을 수 있는 이유는 무엇인가요?
    

## 운영 안정성 / 실무 질문

56. CI 시간이 너무 길어질 때 어떻게 개선하나요?
    
57. Cache를 적용했는데 CI가 빨라지지 않는 이유는 무엇일 수 있나요?
    
58. Flaky Test란 무엇인가요?
    
59. Flaky Test를 방치하면 어떤 문제가 생기나요?
    
60. CI에서 병렬화를 적용할 때 주의할 점은 무엇인가요?
    
61. CI에서 Secret이 유출되었을 때 어떻게 대응해야 하나요?
    
62. `.env` 파일이 Git에 올라갔을 때 어떻게 조치해야 하나요?
    
63. Git history에서 민감 정보를 제거하는 방법에는 무엇이 있나요?
    
64. Force push가 필요한 상황과 위험성은 무엇인가요?
    
65. Tag 기반 Release와 Branch 기반 Release의 차이는 무엇인가요?
    
66. Semantic Versioning은 무엇인가요?
    
67. Release note 자동화는 어떤 장점이 있나요?
    
68. CI/CD에서 “빠른 실패” 전략이 중요한 이유는 무엇인가요?
    
69. Quality Gate를 너무 엄격하게 잡으면 어떤 문제가 생기나요?
    
70. 반대로 Quality Gate를 너무 느슨하게 잡으면 어떤 문제가 생기나요?
    
71. CI runner가 외부 패키지 저장소에 접근하지 못할 때 어떤 원인을 의심할 수 있나요?
    
72. CI에서 `npm install`, `gradle build`, `apt-get update`가 간헐적으로 실패하는 이유는 무엇일 수 있나요?
    
73. GitHub-hosted runner와 self-hosted runner의 네트워크 접근 범위는 어떻게 다를 수 있나요?
    
74. GitLab CI에서 service container와 job container는 어떻게 통신하나요?
    
75. CI에서 테스트용 DB가 준비되기 전에 테스트가 실행되는 문제는 어떻게 해결하나요?
    
76. CI에서 외부 API 의존 테스트를 그대로 돌리면 어떤 문제가 생기나요?
    
77. Mock server나 stub server를 CI 테스트에 사용하는 이유는 무엇인가요?
    
78. 배포 단계에서 SSH 접속 실패 시 DNS, 방화벽, 키 권한을 어떻게 나눠 점검하나요?
