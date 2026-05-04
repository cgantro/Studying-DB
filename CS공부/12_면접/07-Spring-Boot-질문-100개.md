# Spring Boot 질문 100개

답변이 아니라 질문만 모아둔 목록이다.

## Spring 기본
1. Spring Framework를 사용하는 이유는 무엇인가요?
2. Spring Boot와 Spring Framework의 차이는 무엇인가요?
3. Spring Boot의 장점은 무엇인가요?
4. IoC란 무엇인가요?
5. DI란 무엇인가요?
6. IoC Container란 무엇인가요?
7. Bean이란 무엇인가요?
8. Bean 생명주기를 설명해보세요.
9. Component Scan이란 무엇인가요?
10. `@Component`, `@Service`, `@Repository`, `@Controller`의 차이는 무엇인가요?
11. `@RestController`와 `@Controller`의 차이는 무엇인가요?
12. 생성자 주입을 권장하는 이유는 무엇인가요?
13. 필드 주입이 권장되지 않는 이유는 무엇인가요?
14. 순환 참조가 발생하는 이유는 무엇인가요?
15. 순환 참조를 해결하는 방법은 무엇인가요?
16. Spring Boot Auto Configuration은 어떻게 동작하나요?
17. `@SpringBootApplication` 안에는 어떤 어노테이션이 포함되어 있나요?
18. profile은 왜 사용하나요?
19. `application.yml`과 `application.properties`의 차이는 무엇인가요?
20. 환경변수로 설정을 주입하는 이유는 무엇인가요?

## Web / REST API
21. Spring Boot에서 REST API를 구현할 때 Controller의 책임은 어디까지라고 보나요?
22. Spring Boot에서 HTTP Method별 요청을 매핑하는 어노테이션은 무엇인가요?
23. Spring Boot에서 상태 코드와 응답 바디를 함께 제어하려면 어떤 방식을 사용하나요?
24. Spring Boot에서 예외별 HTTP Status Code를 어떻게 매핑하나요?
25. Spring Boot에서 CORS 설정을 전역으로 적용하는 방법은 무엇인가요?
26. Spring Security가 적용된 상황에서 CORS 설정 위치를 잘못 잡으면 어떤 문제가 생기나요?
27. RequestBody와 RequestParam의 차이는 무엇인가요?
28. PathVariable과 RequestParam의 차이는 무엇인가요?
29. DTO를 사용하는 이유는 무엇인가요?
30. API 응답을 공통 포맷으로 감싸는 장단점은 무엇인가요?
31. Validation은 어디에서 처리하는 것이 좋나요?
32. `@Valid`와 `@Validated`의 차이는 무엇인가요?
33. Global Exception Handler는 왜 필요한가요?
34. `@ControllerAdvice`는 어떤 역할을 하나요?
35. `@CrossOrigin`을 controller/method 수준에 적용할 때 장단점은 무엇인가요?
36. Preflight(OPTIONS) 요청이 401/403으로 떨어질 때 어떤 설정을 의심해야 하나요?
37. Cookie 기반 인증과 Header 기반 인증의 차이는 무엇인가요?
38. REST API에서 세션을 잘 쓰지 않는 이유는 무엇인가요?
39. API 버전 관리는 어떻게 할 수 있나요?
40. Spring Boot에서 `@ResponseStatus`와 `ResponseEntity`를 선택하는 기준은 무엇인가요?

## JPA / DB
41. JPA를 사용하는 이유는 무엇인가요?
42. ORM이란 무엇인가요?
43. JPA와 Hibernate의 차이는 무엇인가요?
44. Entity와 Table은 항상 1:1로 대응되어야 하나요?
45. Entity에 setter를 무분별하게 열면 안 되는 이유는 무엇인가요?
46. 영속성 컨텍스트란 무엇인가요?
47. 1차 캐시란 무엇인가요?
48. dirty checking이란 무엇인가요?
49. flush란 무엇인가요?
50. flush와 commit의 차이는 무엇인가요?
51. 지연 로딩과 즉시 로딩의 차이는 무엇인가요?
52. N+1 문제가 발생하는 이유는 무엇인가요?
53. N+1 문제를 해결하는 방법은 무엇인가요?
54. fetch join이란 무엇인가요?
55. EntityGraph는 언제 사용하나요?
56. cascade 옵션을 조심해야 하는 이유는 무엇인가요?
57. orphanRemoval은 무엇인가요?
58. 양방향 연관관계의 단점은 무엇인가요?
59. 연관관계의 주인은 무엇인가요?
60. ManyToOne은 기본 fetch type이 무엇인가요?
61. OneToMany는 기본 fetch type이 무엇인가요?
62. `ddl-auto=validate`는 어떤 의미인가요?
63. 운영 환경에서 `ddl-auto=update`를 조심해야 하는 이유는 무엇인가요?
64. DB migration 도구를 사용하는 이유는 무엇인가요?
65. Flyway와 Liquibase는 어떤 역할을 하나요?
66. transaction이란 무엇인가요?
67. ACID를 설명해보세요.
68. transaction isolation level을 설명해보세요.
69. read committed와 repeatable read의 차이는 무엇인가요?
70. optimistic lock과 pessimistic lock의 차이는 무엇인가요?

## Security / JWT / OAuth
71. Spring Security의 역할은 무엇인가요?
72. Security Filter Chain이란 무엇인가요?
73. 인증과 인가의 차이는 무엇인가요?
74. JWT를 사용하는 이유는 무엇인가요?
75. Access Token과 Refresh Token의 차이는 무엇인가요?
76. Refresh Token을 DB나 Redis에 저장하는 이유는 무엇인가요?
77. JWT의 단점은 무엇인가요?
78. JWT 탈취 시 어떻게 대응하나요?
79. 토큰 재발급 플로우를 설명해보세요.
80. OAuth2 로그인 흐름을 설명해보세요.
81. 일반 로그인 계정과 OAuth 계정을 연결할 때 고려할 점은 무엇인가요?
82. provider별 user id를 어떻게 저장하는 것이 좋나요?
83. 비밀번호는 어떻게 저장해야 하나요?
84. BCrypt를 사용하는 이유는 무엇인가요?
85. Cookie 기반 JWT와 Authorization Header 기반 JWT의 차이는 무엇인가요?
86. CSRF란 무엇인가요?
87. XSS란 무엇인가요?
88. HttpOnly Cookie는 어떤 공격을 줄여주나요?
89. SameSite 옵션은 무엇인가요?
90. CORS와 인증은 어떤 관계가 있나요?

## 운영 / 성능 / 메시징
91. AOP를 어디에 적용할 수 있나요?
92. 로깅 AOP를 적용할 때 주의할 점은 무엇인가요?
93. traceId를 로그에 남기는 이유는 무엇인가요?
94. actuator는 어떤 용도로 사용하나요?
95. health check는 왜 필요한가요?
96. Redis Cache를 사용하는 이유는 무엇인가요?
97. Cache Aside 패턴을 설명해보세요.
98. MQTT와 HTTP의 차이는 무엇인가요?
99. WebSocket과 HTTP polling의 차이는 무엇인가요?
100. Spring Boot 서버를 EC2 단일 인스턴스에 배포할 때 고려할 점은 무엇인가요?
