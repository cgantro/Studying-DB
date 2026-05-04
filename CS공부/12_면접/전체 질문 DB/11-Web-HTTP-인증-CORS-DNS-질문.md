# Web / HTTP / 인증 / CORS / DNS

## HTTP 기본

1. HTTP란 무엇인가요?
    
2. HTTP Request와 Response의 구조를 설명해보세요.
    
3. HTTP Method GET, POST, PUT, PATCH, DELETE의 차이는 무엇인가요?
    
4. GET과 POST의 차이는 무엇인가요?
    
5. PUT과 PATCH의 차이는 무엇인가요?
    
6. HTTP Status Code 2xx, 3xx, 4xx, 5xx의 차이는 무엇인가요?
    
7. 200, 201, 204의 차이는 무엇인가요?
    
8. 301과 302의 차이는 무엇인가요?
    
9. 400, 401, 403, 404의 차이는 무엇인가요?
    
10. 500, 502, 503, 504의 차이는 무엇인가요?
    

## HTTP 버전 / 연결

11. HTTP/1.1의 Keep-Alive는 무엇인가요?
    
12. HTTP/1.1의 Head-of-Line Blocking 문제는 무엇인가요?
    
13. HTTP/2는 HTTP/1.1의 어떤 문제를 개선했나요?
    
14. HTTP/2 Multiplexing이란 무엇인가요?
    
15. HTTP/3는 어떤 특징을 가지나요?
    
16. TCP와 UDP 기반 웹 통신의 차이는 무엇인가요?
    
17. TLS Handshake는 왜 필요한가요?
    
18. HTTPS는 HTTP와 무엇이 다른가요?
    
19. 인증서가 만료되면 어떤 문제가 발생하나요?
    
20. 브라우저가 HTTPS 인증서를 검증하는 과정은 어떻게 되나요?
    

## Header / Cookie / Caching

21. HTTP Header는 어떤 역할을 하나요?
    
22. `Content-Type`과 `Accept`의 차이는 무엇인가요?
    
23. `Authorization` Header는 언제 사용하나요?
    
24. Cookie는 어떤 방식으로 서버에 전달되나요?
    
25. Cookie의 Domain과 Path 옵션은 무엇인가요?
    
26. HttpOnly Cookie는 어떤 공격을 줄여주나요?
    
27. Secure Cookie는 어떤 의미인가요?
    
28. SameSite 옵션은 어떤 역할을 하나요?
    
29. Cache-Control Header는 어떤 역할을 하나요?
    
30. ETag는 어떤 문제를 해결하나요?
    

## CORS / SOP / 브라우저 보안

31. Same-Origin Policy란 무엇인가요?
    
32. Origin은 무엇으로 구성되나요?
    
33. CORS란 무엇인가요?
    
34. Preflight Request란 무엇인가요?
    
35. Simple Request와 Preflight Request의 차이는 무엇인가요?
    
36. `Access-Control-Allow-Origin`은 어떤 역할을 하나요?
    
37. `Access-Control-Allow-Credentials`는 언제 필요한가요?
    
38. Credential 포함 요청에서 wildcard origin을 사용할 수 없는 이유는 무엇인가요?
    
39. 모바일 앱에서도 CORS가 적용되나요?
    
40. 브라우저 환경과 서버-서버 통신에서 CORS 차이는 무엇인가요?
    

## 인증 / 인가

41. 웹 애플리케이션에서 Session 기반과 JWT 기반(Stateless) 인증을 선택하는 기준은 무엇인가요?
    
42. Session 기반 인증은 어떻게 동작하나요?
    
43. JWT 기반 인증은 어떻게 동작하나요?
    
44. JWT를 브라우저에 저장할 때 Cookie vs LocalStorage 선택 기준은 무엇인가요?
    
45. Refresh Token을 서버에 저장하는 이유는 무엇인가요?
    
46. JWT의 장점과 단점은 무엇인가요?
    
47. JWT 탈취 시 어떻게 대응할 수 있나요?
    
48. Cookie 기반 인증과 Authorization Header 기반 인증의 차이는 무엇인가요?
    
49. CSRF 공격은 어떤 방식으로 발생하나요?
    
50. XSS 공격은 어떤 방식으로 발생하나요?
    
51. CSRF와 XSS의 차이는 무엇인가요?
    
52. OAuth2는 어떤 문제를 해결하기 위한 프로토콜인가요?
    
53. Authorization Code Flow를 설명해보세요.
    
54. OAuth2에서 Redirect URI가 중요한 이유는 무엇인가요?
    
55. OpenID Connect는 OAuth2와 무엇이 다른가요?
    

## REST / API 설계

56. REST란 무엇인가요?
    
57. RESTful API란 무엇인가요?
    
58. Resource 중심 URL 설계란 무엇인가요?
    
59. API에서 동사를 URL에 넣는 것이 권장되지 않는 이유는 무엇인가요?
    
60. Pagination은 왜 필요한가요?
    
61. Offset Pagination과 Cursor Pagination의 차이는 무엇인가요?
    
62. API 응답 공통 포맷의 장단점은 무엇인가요?
    
63. API 에러 응답은 어떻게 설계하는 것이 좋나요?
    
64. Idempotency란 무엇인가요?
    
65. 멱등성이 중요한 API 예시는 무엇인가요?
    

## 실시간 통신 / 웹소켓

66. Polling, Long Polling, SSE, WebSocket의 차이는 무엇인가요?
    
67. WebSocket은 HTTP와 어떤 관계가 있나요?
    
68. WebSocket Handshake는 어떻게 이루어지나요?
    
69. WebSocket은 어떤 상황에서 적합한가요?
    
70. SSE는 어떤 상황에서 WebSocket보다 단순한 선택이 될 수 있나요?
    
71. 실시간 통신에서 Heartbeat가 필요한 이유는 무엇인가요?
    
72. WebSocket 연결이 끊겼을 때 재연결 전략은 어떻게 설계하나요?
    
73. STOMP는 WebSocket 위에서 어떤 역할을 하나요?
    
74. 메시지 브로커를 사용하는 이유는 무엇인가요?
    
75. 실시간 서비스에서 Backpressure는 왜 중요한가요?
    

## 웹 성능 / 운영

76. CDN을 사용하는 이유는 무엇인가요?
    
77. 브라우저 렌더링 과정은 어떻게 이루어지나요?
    
78. Critical Rendering Path란 무엇인가요?
    
79. Lazy Loading은 어떤 성능 이점이 있나요?
    
80. 웹 서비스 장애 분석 시 클라이언트, Nginx, WAS, DB 중 어디부터 확인하겠나요?
    
## DNS / 요청 흐름 / 네트워크 디버깅

81. 브라우저 주소창에 URL을 입력했을 때 DNS, TCP, TLS, HTTP 요청 순서로 설명해보세요.
    
82. DNS는 어떤 역할을 하나요?
    
83. DNS Resolver는 어떤 역할을 하나요?
    
84. DNS Cache는 왜 필요한가요?
    
85. DNS TTL은 무엇이고, DNS 변경 후 바로 반영되지 않는 이유는 무엇인가요?
    
86. A Record, AAAA Record, CNAME Record의 차이는 무엇인가요?
    
87. DNS 조회는 브라우저, OS, 공유기, 외부 DNS 서버 중 어디에서 캐시될 수 있나요?
    
88. DNS 조회가 실패하면 브라우저에서는 어떤 형태의 오류가 발생하나요?
    
89. DNS 조회는 성공했지만 TCP 연결이 실패하면 어떤 원인을 의심할 수 있나요?
    
90. TCP 연결은 성공했지만 TLS Handshake가 실패하면 어떤 문제를 의심할 수 있나요?
    
91. 브라우저 개발자 도구 Network 탭에서 DNS Lookup, Initial Connection, SSL, TTFB는 각각 무엇을 의미하나요?
    
92. 도메인은 맞는데 접속이 안 될 때 DNS, Nginx, WAS, 방화벽 중 어떤 순서로 확인하겠나요?
    
93. `nslookup` 또는 `dig`는 어떤 상황에서 사용하나요?
    
94. HTTP 응답이 느릴 때 DNS 문제인지 서버 처리 문제인지 어떻게 구분하나요?
    
95. CDN은 DNS와 어떤 관계가 있나요?

96. TCP 3-way handshake는 웹 요청 흐름에서 언제 발생하나요?
    
97. TLS Handshake는 HTTPS 요청에서 어떤 역할을 하나요?
    
98. 웹 요청이 느릴 때 DNS Lookup, Initial Connection, SSL, TTFB 중 어디가 긴지 어떻게 확인하나요?
    
99. `nslookup`과 `dig`의 차이는 무엇이고, 어떤 정보를 주로 확인하나요?
    
100. 도메인은 맞는데 특정 지역/네트워크에서만 접속이 안 될 때 어떤 원인을 의심하나요?
    
101. DNS 레코드 변경 후 일부 사용자에게만 접속이 안 되는 상황을 어떻게 설명하겠나요?
    
102. 클라이언트에서는 DNS가 되는데 서버(컨테이너)에서만 DNS가 실패하면 어떤 지점을 점검하나요?
