# Docker / Container / Network

## Docker 기본

1. Docker를 사용하는 이유는 무엇인가요?
    
2. Container와 Virtual Machine의 차이는 무엇인가요?
    
3. Docker Image와 Container의 차이는 무엇인가요?
    
4. Dockerfile은 어떤 역할을 하나요?
    
5. Docker Image Layer란 무엇인가요?
    
6. Docker Image Layer 캐시는 왜 중요한가요?
    
7. `docker build`와 `docker run`의 차이는 무엇인가요?
    
8. `CMD`와 `ENTRYPOINT`의 차이는 무엇인가요?
    
9. `COPY`와 `ADD`의 차이는 무엇인가요?
    
10. `.dockerignore`를 사용하는 이유는 무엇인가요?
    

## Container 실행 / 상태 / 메모리

11. Container는 기본적으로 어떤 프로세스를 실행하나요?
    
12. Container에서 메인 프로세스가 종료되면 어떤 일이 발생하나요?
    
13. Container 내부에서 PID 1 문제란 무엇인가요?
    
14. Docker Container의 로그는 어떻게 확인하나요?
    
15. Container가 재시작되는 대표적인 원인은 무엇인가요?
    
16. `restart: always`와 `restart: unless-stopped`의 차이는 무엇인가요?
    
17. Container에 메모리 제한을 걸지 않으면 어떤 문제가 생길 수 있나요?
    
18. JVM 애플리케이션을 Docker에서 실행할 때 메모리 설정을 조심해야 하는 이유는 무엇인가요?
    
19. Container 내부 시간대 설정은 왜 중요할 수 있나요?
    
20. Container 내부 파일 시스템은 왜 휘발성으로 봐야 하나요?
    

## Volume / Network

21. Docker Volume을 사용하는 이유는 무엇인가요?
    
22. Bind Mount와 Docker Volume의 차이는 무엇인가요?
    
23. DB Container에서 Volume을 사용하지 않으면 어떤 문제가 생기나요?
    
24. Container 간 통신은 어떻게 이루어지나요?
    
25. Docker Bridge Network는 어떤 역할을 하나요?
    
26. Host Network Mode는 어떤 경우에 사용하나요?
    
27. Port Mapping은 어떻게 동작하나요?
    
28. `-p 8080:8080`의 의미는 무엇인가요?
    
29. Container 내부에서 `localhost`는 무엇을 의미하나요?
    
30. Container에서 Host의 서비스에 접근하려면 어떻게 해야 하나요?
    

## Docker Compose / 운영

31. Docker Compose를 사용하는 이유는 무엇인가요?
    
32. `docker-compose.yml`에서 service는 무엇을 의미하나요?
    
33. `depends_on`은 애플리케이션 준비 완료까지 보장하나요?
    
34. DB가 완전히 뜨기 전에 서버가 시작되는 문제는 어떻게 해결하나요?
    
35. Healthcheck는 왜 필요한가요?
    
36. 환경변수는 Docker Compose에서 어떻게 주입하나요?
    
37. Secret 값을 image에 넣으면 안 되는 이유는 무엇인가요?
    
38. Multi-stage build를 사용하는 이유는 무엇인가요?
    
39. Java 애플리케이션 Dockerfile에서 JAR만 복사하는 방식의 장점은 무엇인가요?
    
40. Node나 Java 빌드 산출물을 이미지에 넣을 때 주의할 점은 무엇인가요?
    

## Docker 배포 / 트러블슈팅

41. Docker 이미지 크기를 줄이는 방법은 무엇인가요?
    
42. Alpine 이미지를 사용할 때 주의할 점은 무엇인가요?
    
43. Container가 실행 직후 종료될 때 어떻게 디버깅하나요?
    
44. Container 내부에 접속하는 명령어는 무엇인가요?
    
45. `docker exec`와 `docker run`의 차이는 무엇인가요?
    
46. 실행 중인 Container의 환경변수를 확인하려면 어떻게 하나요?
    
47. 실행 중인 Container의 Mount 정보를 확인하려면 어떻게 하나요?
    
48. Docker Network 문제를 디버깅할 때 어떤 명령어를 사용하나요?
    
49. Docker 로그가 너무 커지는 문제는 어떻게 제어하나요?
    
50. 운영 서버에서 Docker image prune을 조심해야 하는 이유는 무엇인가요?
    

## 보안 / CI 연동

51. Docker image에 `.env`를 포함하면 안 되는 이유는 무엇인가요?
    
52. Container를 root user로 실행하면 어떤 문제가 생길 수 있나요?
    
53. non-root user로 Container를 실행하는 이유는 무엇인가요?
    
54. Docker Hub 이미지 사용 시 보안상 확인할 점은 무엇인가요?
    
55. 이미지 취약점 스캔은 왜 필요한가요?
    
56. CI에서 Docker image를 build/push하는 일반적인 흐름은 무엇인가요?
    
57. GitHub Actions에서 Docker build cache를 활용하는 이유는 무엇인가요?
    
58. GitLab CI에서 Docker-in-Docker를 사용할 때 주의할 점은 무엇인가요?
    
59. Blue-Green 배포와 Rolling 배포의 차이는 무엇인가요?
    
60. Docker Compose 기반 단일 서버 배포의 한계는 무엇인가요?
    
## Docker Compose DNS / Network

61. Docker Compose에서 service 이름으로 컨테이너에 접근할 수 있는 이유는 무엇인가요?
    
62. 같은 Docker network에 있지 않은 컨테이너끼리 service name으로 접근할 수 없는 이유는 무엇인가요?
    
63. Docker Compose 환경에서 앱 컨테이너가 `localhost`로 다른 컨테이너(DB 등)에 접속하면 실패하는 이유는 무엇인가요?
    
64. 컨테이너에서 host machine의 서비스에 접근하려면 어떤 방법을 사용할 수 있나요?
    
65. Docker Compose에서 `ports`와 `expose`의 차이는 무엇인가요?
    
66. 컨테이너 재시작 후 IP가 바뀌어도 service name 접근이 유리한 이유는 무엇인가요?
    
67. Docker에서 DNS 문제가 발생했을 때 어떤 명령어로 확인할 수 있나요?
    
68. Docker Compose에서 DB는 떴지만 애플리케이션이 연결 실패하는 이유는 무엇일 수 있나요?
