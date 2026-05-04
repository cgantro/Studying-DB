# Spring Boot

## Spring 기본

1. Spring Framework를 사용하는 이유는 무엇인가요?
    
2. Spring Boot와 Spring Framework의 차이는 무엇인가요?
    
3. Spring Boot의 핵심 장점은 무엇인가요?
    
4. IoC란 무엇인가요?
    
5. DI란 무엇인가요?
    
6. IoC Container는 어떤 역할을 하나요?
    
7. Bean이란 무엇인가요?
    
8. Bean 생명주기를 설명해보세요.
    
9. Component Scan은 어떻게 동작하나요?
    
10. Auto Configuration은 어떻게 동작하나요?
    
11. `@SpringBootApplication`에는 어떤 어노테이션이 포함되어 있나요?
    
12. Starter Dependency는 어떤 장점이 있나요?
    
13. `application.yml`과 `application.properties`의 차이는 무엇인가요?
    
14. Profile을 사용하는 이유는 무엇인가요?
    
15. 환경변수로 설정을 주입하는 이유는 무엇인가요?
    

## Bean / DI / 싱글톤 동시성

16. `@Component`, `@Service`, `@Repository`, `@Controller`의 차이는 무엇인가요?
    
17. `@RestController`와 `@Controller`의 차이는 무엇인가요?
    
18. 생성자 주입을 권장하는 이유는 무엇인가요?
    
19. 필드 주입이 권장되지 않는 이유는 무엇인가요?
    
20. 순환 참조는 왜 발생하나요?
    
21. 순환 참조를 해결하는 방법은 무엇인가요?
    
22. Spring Bean은 기본적으로 어떤 scope를 가지나요?
    
23. Singleton Bean은 멀티스레드 환경에서 안전한가요?
    
24. Service Bean을 무상태로 설계해야 하는 이유는 무엇인가요?
    
25. Service 클래스에 요청별 상태를 instance 변수로 저장하면 어떤 문제가 생기나요?
    
26. Spring MVC에서 여러 요청이 같은 Controller 인스턴스를 공유해도 되는 이유는 무엇인가요?
    
27. Thread-safe한 Spring Bean을 만들려면 어떻게 설계해야 하나요?
    
28. Request Scope Bean은 언제 사용하나요?
    
29. Prototype Scope Bean은 Singleton Bean에 주입될 때 어떤 문제가 생기나요?
    
30. `ObjectProvider`는 어떤 상황에서 사용하나요?
    

## Web / REST

31. Spring Boot에서 REST API를 구현할 때 Controller의 책임은 어디까지라고 보나요?
    
32. Spring Boot에서 HTTP Method별 요청을 매핑하는 어노테이션은 무엇인가요?
    
33. Spring Boot에서 상태 코드와 응답 바디를 함께 제어하려면 어떤 방식을 사용하나요?
    
34. Spring Boot에서 예외별 HTTP Status Code를 어떻게 매핑하나요?
    
35. Spring Boot에서 CORS 설정을 전역으로 적용하는 방법은 무엇인가요?
    
36. Spring Security가 적용된 상황에서 CORS 설정 위치를 잘못 잡으면 어떤 문제가 생기나요?
    
37. `@RequestBody`, `@RequestParam`, `@PathVariable`의 차이는 무엇인가요?
    
38. Validation은 어느 계층에서 처리하는 것이 좋나요?
    
39. `@Valid`와 `@Validated`의 차이는 무엇인가요?
    
40. Global Exception Handler는 왜 필요한가요?
    
41. `@ControllerAdvice`는 어떤 역할을 하나요?
    
42. API 응답을 공통 포맷으로 감싸는 것의 장단점은 무엇인가요?
    
43. API 버전 관리는 어떻게 할 수 있나요?
    
44. REST API에서 세션을 잘 쓰지 않는 이유는 무엇인가요?
    
45. Spring Boot에서 `@ResponseStatus`와 `ResponseEntity`로 상태 코드를 제어하는 방식의 차이는 무엇인가요?
    

## Spring MVC / 요청 처리 / 스레드

46. Spring MVC에서 요청 하나가 처리되는 흐름을 설명해보세요.
    
47. DispatcherServlet은 어떤 역할을 하나요?
    
48. HandlerMapping과 HandlerAdapter는 어떤 역할을 하나요?
    
49. Filter와 Interceptor의 차이는 무엇인가요?
    
50. ArgumentResolver는 어떤 역할을 하나요?
    
51. Tomcat은 요청을 어떤 방식으로 멀티스레드 처리하나요?
    
52. Tomcat request thread pool이 고갈되면 어떤 일이 발생하나요?
    
53. Spring MVC는 blocking I/O 기반인가요?
    
54. `@Async`는 어떤 상황에서 사용하나요?
    
55. `@Async` 사용 시 주의할 점은 무엇인가요?
    
56. `@Async`가 같은 클래스 내부 호출에서 동작하지 않는 이유는 무엇인가요?
    
57. ThreadPoolTaskExecutor 설정에서 corePoolSize, maxPoolSize, queueCapacity는 각각 무엇인가요?
    
58. 비동기 작업에서 예외 처리는 어떻게 해야 하나요?
    
59. Virtual Thread를 Spring Boot에서 사용할 때 기대 효과는 무엇인가요?
    
60. Virtual Thread를 사용해도 DB Connection Pool이 병목이 될 수 있는 이유는 무엇인가요?
    

## JPA / DB / 메모리

61. JPA를 사용하는 이유는 무엇인가요?
    
62. ORM이란 무엇인가요?
    
63. JPA와 Hibernate의 차이는 무엇인가요?
    
64. Entity는 왜 기본 생성자가 필요한가요?
    
65. Entity에 setter를 무분별하게 열면 어떤 문제가 생기나요?
    
66. 영속성 컨텍스트란 무엇인가요?
    
67. 1차 캐시란 무엇인가요?
    
68. Dirty Checking이란 무엇인가요?
    
69. Flush와 Commit의 차이는 무엇인가요?
    
70. 지연 로딩과 즉시 로딩의 차이는 무엇인가요?
    
71. N+1 문제가 발생하는 이유는 무엇인가요?
    
72. N+1 문제를 해결하는 방법은 무엇인가요?
    
73. Fetch Join이란 무엇인가요?
    
74. EntityGraph는 언제 사용하나요?
    
75. 대량 조회에서 JPA 영속성 컨텍스트가 메모리 문제를 만들 수 있는 이유는 무엇인가요?
    
76. 대량 insert/update에서 `flush()`와 `clear()`를 사용하는 이유는 무엇인가요?
    
77. Open Session In View는 무엇이고 어떤 장단점이 있나요?
    
78. Transaction이란 무엇인가요?
    
79. `@Transactional`은 내부적으로 어떻게 동작하나요?
    
80. Transaction Context가 ThreadLocal과 관련되는 이유는 무엇인가요?
    

## Security / Spring Boot 버전 변화

81. Spring Security는 어떤 역할을 하나요?
    
82. Security Filter Chain이란 무엇인가요?
    
83. 인증과 인가의 차이는 무엇인가요?
    
84. JWT를 사용하는 이유는 무엇인가요?
    
85. Access Token과 Refresh Token의 차이는 무엇인가요?
    
86. Cookie 기반 JWT와 Authorization Header 기반 JWT의 차이는 무엇인가요?
    
87. Spring Security에서 CSRF 보호를 적용/비활성화할 때 판단 기준은 무엇인가요?
    
88. HttpOnly, Secure, SameSite 옵션의 의미는 무엇인가요?
    
89. Spring Boot 2에서 3으로 넘어갈 때 가장 큰 변화는 무엇인가요?
    
90. `javax.*`에서 `jakarta.*`로 바뀐 것이 왜 중요한가요?
