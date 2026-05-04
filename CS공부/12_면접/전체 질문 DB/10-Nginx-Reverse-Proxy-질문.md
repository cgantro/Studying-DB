# Nginx / Reverse Proxy

## Nginx 기본

1. Nginx는 어떤 역할을 하는 서버인가요?
    
2. Web Server와 WAS의 차이는 무엇인가요?
    
3. Nginx와 Spring Boot 내장 Tomcat의 역할 차이는 무엇인가요?
    
4. Nginx를 Spring Boot 앞단에 두는 이유는 무엇인가요?
    
5. Reverse Proxy란 무엇인가요?
    
6. Forward Proxy와 Reverse Proxy의 차이는 무엇인가요?
    
7. Nginx가 정적 파일 서빙에 강한 이유는 무엇인가요?
    
8. Nginx의 event-driven 구조는 어떤 장점이 있나요?
    
9. Nginx worker process와 worker connection은 무엇인가요?
    
10. Nginx 설정 파일의 server block과 location block은 무엇인가요?
    

## Reverse Proxy / Load Balancing

11. Nginx에서 `proxy_pass`는 어떤 역할을 하나요?
    
12. Upstream 설정은 어떤 상황에서 사용하나요?
    
13. Load Balancing이 필요한 이유는 무엇인가요?
    
14. Round Robin, Least Connections 방식의 차이는 무엇인가요?
    
15. Sticky Session이 필요한 경우는 언제인가요?
    
16. Spring Boot 서버 여러 대를 Nginx 뒤에 둘 때 고려할 점은 무엇인가요?
    
17. Health Check는 왜 필요한가요?
    
18. Nginx에서 timeout 설정이 중요한 이유는 무엇인가요?
    
19. `proxy_connect_timeout`, `proxy_read_timeout`, `proxy_send_timeout`의 차이는 무엇인가요?
    
20. 502 Bad Gateway는 보통 어떤 경우에 발생하나요?
    

## Header / HTTPS / 보안

21. Nginx에서 Host Header를 백엔드로 넘겨야 하는 이유는 무엇인가요?
    
22. `X-Forwarded-For`는 어떤 역할을 하나요?
    
23. `X-Forwarded-Proto`는 왜 필요한가요?
    
24. 백엔드 서버가 실제 클라이언트 IP를 얻으려면 무엇을 설정해야 하나요?
    
25. HTTPS를 Nginx에서 종료한다는 말은 무슨 뜻인가요?
    
26. TLS Termination의 장단점은 무엇인가요?
    
27. HTTP에서 HTTPS로 리다이렉트하는 이유는 무엇인가요?
    
28. HSTS란 무엇인가요?
    
29. Nginx에서 CORS Header를 처리할 때 주의할 점은 무엇인가요?
    
30. Nginx에서 보안 Header를 추가하는 이유는 무엇인가요?
    

## 정적 파일 / 압축 / 캐싱

31. Nginx로 정적 파일을 서빙하면 어떤 장점이 있나요?
    
32. Gzip 압축은 어떤 효과가 있나요?
    
33. Brotli는 Gzip과 어떤 차이가 있나요?
    
34. Nginx에서 정적 리소스 캐시 정책을 설정할 때 어떤 지시어/헤더를 사용하고, 설정 위치에 따라 어떤 차이가 있나요?
    
35. 정적 리소스에 긴 캐시 시간을 줄 때 주의할 점은 무엇인가요?
    
36. 파일명에 hash를 붙이는 이유는 무엇인가요?
    
37. SPA를 Nginx로 배포할 때 `try_files`가 필요한 이유는 무엇인가요?
    
38. React/Vue SPA에서 새로고침 시 404가 나는 이유는 무엇인가요?
    
39. Upload 파일 크기 제한은 Nginx에서 어떻게 제어하나요?
    
40. `client_max_body_size`는 어떤 역할을 하나요?
    

## WebSocket / 로그 / 트러블슈팅

41. WebSocket을 Nginx로 프록시할 때 필요한 설정은 무엇인가요?
    
42. HTTP Upgrade Header는 어떤 역할을 하나요?
    
43. Nginx access log와 error log의 차이는 무엇인가요?
    
44. Nginx 로그에서 요청 지연을 분석하려면 어떤 값을 봐야 하나요?
    
45. 404, 502, 504 에러의 차이는 무엇인가요?
    
46. 504 Gateway Timeout은 보통 어떤 경우에 발생하나요?
    
47. Nginx 설정 변경 후 적용하는 명령 흐름은 무엇인가요?
    
48. `nginx -t`를 실행하는 이유는 무엇인가요?
    
49. Nginx reload와 restart의 차이는 무엇인가요?
    
50. 운영 중 Nginx 설정을 잘못 바꾸면 어떤 문제가 생길 수 있나요?
    

## 배포 구조

51. Nginx + Spring Boot 단일 서버 구조를 설명해보세요.
    
52. Nginx + Docker Compose 구조에서 포트 매핑은 어떻게 설계하나요?
    
53. Nginx가 Host에서 돌고 Spring Boot가 Container에서 돌 때 연결 방식은 어떻게 되나요?
    
54. Nginx도 Container로 올릴 때 장단점은 무엇인가요?
    
55. Blue-Green 배포에서 Nginx는 어떤 역할을 할 수 있나요?
    
56. 무중단 배포에서 Nginx upstream 전환은 어떻게 활용할 수 있나요?
    
57. Nginx에서 rate limiting을 거는 이유는 무엇인가요?
    
58. Nginx에서 IP allow/deny를 사용하는 경우는 언제인가요?
    
59. Nginx와 API Gateway의 차이는 무엇인가요?
    
60. Nginx 앞에 CDN을 두는 이유는 무엇인가요?
    
## DNS / Upstream

61. Nginx upstream에 도메인을 넣었을 때 DNS 조회는 언제 수행되나요?
    
62. upstream 서버 IP가 바뀌었는데 Nginx가 계속 예전 IP로 요청할 수 있는 이유는 무엇인가요?
    
63. Nginx에서 `resolver` 지시어는 어떤 상황에서 사용하나요?
    
64. Docker Compose 환경에서 Nginx가 `backend` 같은 service name으로 백엔드 컨테이너에 접근하려면 무엇이 필요하나요?
    
65. Nginx 컨테이너와 백엔드 컨테이너가 같은 Docker network에 있어야 하는 이유는 무엇인가요?
    
66. Nginx가 HTTPS upstream에 연결할 때 SNI가 필요한 경우는 언제인가요?
    
67. Nginx에서 502와 504를 구분해서 봐야 하는 이유는 무엇인가요?
    
68. Nginx access log에서 upstream 응답 시간이 길면 어떤 병목을 의심할 수 있나요?
