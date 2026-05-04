

# 1. Java / JVM

## Java 기본

1. Java의 핵심 특징을 설명해보세요.
    
2. Java가 플랫폼 독립적이라고 하는 이유는 무엇인가요?
    
3. JVM, JRE, JDK의 차이를 설명해보세요.
    
4. bytecode란 무엇인가요?
    
5. Java 소스 코드가 실행되기까지의 과정을 설명해보세요.
    
6. `javac`는 어떤 역할을 하나요?
    
7. Class Loader는 어떤 역할을 하나요?
    
8. Class Loading 과정의 Loading, Linking, Initialization을 설명해보세요.
    
9. Bytecode Verifier는 왜 필요한가요?
    
10. JIT Compiler는 어떤 역할을 하나요?
    
11. Interpreter와 JIT Compiler의 차이는 무엇인가요.
    
12. JVM이 HotSpot이라는 이름을 가지는 이유는 무엇인가요?
    
13. Java에서 `public static void main(String[] args)`의 각 키워드를 설명해보세요.
    
14. primitive type과 reference type의 차이는 무엇인가요?
    
15. `int`와 `Integer`의 차이는 무엇인가요?
    
16. autoboxing과 unboxing이란 무엇인가요?
    
17. autoboxing이 성능 문제를 만들 수 있는 경우는 언제인가요?
    
18. Java는 pass-by-value라고 하는데, reference type에서는 어떻게 동작하나요?
    
19. `==`와 `equals()`의 차이는 무엇인가요?
    
20. `equals()`와 `hashCode()`를 함께 재정의해야 하는 이유는 무엇인가요?
    

## String / 객체 / 예외

21. `String`은 왜 immutable인가요?
    
22. String Pool이란 무엇인가요?
    
23. `new String("abc")`와 `"abc"`의 차이는 무엇인가요?
    
24. `String.intern()`은 어떤 역할을 하나요?
    
25. `String`, `StringBuilder`, `StringBuffer`의 차이는 무엇인가요?
    
26. 문자열 비교에서 `==`를 쓰면 안 되는 이유는 무엇인가요?
    
27. `final` 키워드는 변수, 메서드, 클래스에서 각각 어떤 의미인가요?
    
28. `final` reference 변수의 내부 객체 상태는 변경 가능한가요?
    
29. `static` 키워드의 의미는 무엇인가요?
    
30. static 메서드에서 instance 변수에 직접 접근할 수 없는 이유는 무엇인가요?
    
31. Checked Exception과 Unchecked Exception의 차이는 무엇인가요?
    
32. Java에서 예외를 너무 넓게 catch하면 어떤 문제가 생기나요?
    
33. try-with-resources는 어떤 문제를 해결하나요?
    
34. `AutoCloseable`은 어떤 역할을 하나요?
    
35. `throw`와 `throws`의 차이는 무엇인가요?
    

## JVM 메모리 관리

36. JVM Runtime Data Area를 설명해보세요.
    
37. Heap 영역에는 무엇이 저장되나요?
    
38. Stack 영역에는 무엇이 저장되나요?
    
39. Method Area 또는 Metaspace에는 무엇이 저장되나요?
    
40. PC Register와 Native Method Stack은 어떤 역할을 하나요?
    
41. Java 객체는 Heap에 생성된다고 하는데, 모든 객체가 반드시 Heap에 남나요?
    
42. Escape Analysis란 무엇인가요?
    
43. Java에서도 메모리 누수가 발생할 수 있나요?
    
44. Java 메모리 누수가 발생하는 대표적인 경우는 무엇인가요?
    
45. static Collection이 메모리 누수를 만들 수 있는 이유는 무엇인가요?
    
46. ThreadLocal이 메모리 누수를 만들 수 있는 경우는 언제인가요?
    
47. GC가 필요한 이유는 무엇인가요?
    
48. GC Root란 무엇인가요?
    
49. Minor GC와 Major GC의 차이는 무엇인가요?
    
50. Stop-the-world란 무엇인가요?
    
51. Young Generation과 Old Generation을 나누는 이유는 무엇인가요?
    
52. 객체가 Old Generation으로 승격되는 기준은 무엇인가요?
    
53. G1 GC는 어떤 특징을 가지나요?
    
54. ZGC는 어떤 목적의 GC인가요?
    
55. Java에서 `System.gc()`를 직접 호출하는 것이 권장되지 않는 이유는 무엇인가요?
    

## Java 8 / 11 / 17 / 21 변화

56. Java 8에서 도입된 주요 기능은 무엇인가요?
    
57. Lambda Expression은 기존 익명 클래스와 무엇이 다른가요?
    
58. Stream API의 장점과 단점은 무엇인가요?
    
59. Optional은 어떤 문제를 해결하기 위해 도입되었나요?
    
60. Java 8 default method는 왜 필요했나요?
    
61. Java 11이 기업 환경에서 많이 쓰이는 이유는 무엇인가요?
    
62. Java 11의 `var`는 어떤 상황에서 유용하고 언제 피해야 하나요?
    
63. Java 17의 `record`는 어떤 문제를 해결하나요?
    
64. Java 17의 sealed class는 어떤 상황에서 유용한가요?
    
65. Java 21의 Virtual Thread는 기존 Platform Thread와 무엇이 다른가요?
    

---

# 2. Java Collection / 동시성 / 네트워크

## Collection

1. `ArrayList`와 `LinkedList`의 차이는 무엇인가요?
    
2. `HashMap`의 내부 동작 방식을 설명해보세요.
    
3. `HashMap`에서 해시 충돌은 어떻게 처리되나요?
    
4. `HashMap`과 `ConcurrentHashMap`의 차이는 무엇인가요?
    
5. `HashSet`은 중복을 어떻게 판단하나요?
    
6. `TreeMap`과 `HashMap`의 차이는 무엇인가요?
    
7. `PriorityQueue`는 내부적으로 어떤 자료구조를 사용하나요?
    
8. `Stack`보다 `Deque`를 권장하는 이유는 무엇인가요?
    
9. `Iterator` 사용 중 Collection을 수정하면 어떤 문제가 생기나요?
    
10. `Collections.synchronizedList()`와 `CopyOnWriteArrayList`의 차이는 무엇인가요?
    

## Java 멀티스레딩 / 동시성

11. Java에서 스레드를 생성하는 방법에는 무엇이 있나요?
    
12. `Thread`, `Runnable`, `Callable`의 차이는 무엇인가요?
    
13. `Future`와 `CompletableFuture`의 차이는 무엇인가요?
    
14. `ExecutorService`를 사용하는 이유는 무엇인가요?
    
15. 스레드를 직접 생성하는 것보다 스레드 풀을 사용하는 이유는 무엇인가요?
    
16. CPU-bound 작업과 I/O-bound 작업에서 스레드 풀 크기 전략은 어떻게 달라지나요?
    
17. `synchronized`는 어떤 문제를 해결하나요?
    
18. 객체 락과 클래스 락의 차이는 무엇인가요?
    
19. `volatile`은 어떤 문제를 해결하나요?
    
20. `volatile`이 원자성을 보장하지 못한다는 말은 무슨 뜻인가요?
    
21. `AtomicInteger`는 어떻게 동시성 문제를 해결하나요?
    
22. CAS란 무엇인가요?
    
23. `ReentrantLock`은 `synchronized`와 무엇이 다른가요?
    
24. Immutable 객체가 멀티스레딩에서 유리한 이유는 무엇인가요?
    

## Java Network / DNS

25. Java에서 `UnknownHostException`은 어떤 경우에 발생하나요?
    
26. Java HTTP Client에서 connect timeout과 read timeout의 차이는 무엇인가요?
    
27. 외부 API 호출 시 timeout을 설정하지 않으면 어떤 문제가 생기나요?
    
28. Java 애플리케이션에서 DNS 변경이 바로 반영되지 않을 수 있는 이유는 무엇인가요?
    
29. Java에서 TLS 인증서 검증 실패 시 어떤 예외가 발생할 수 있나요?
    

---

# 3. 객체지향

## OOP 기본

1. 객체지향 프로그래밍이란 무엇인가요?
    
2. 절차지향과 객체지향의 차이는 무엇인가요?
    
3. 클래스와 객체의 차이는 무엇인가요?
    
4. 객체지향의 4대 특징을 설명해보세요.
    
5. 캡슐화란 무엇인가요?
    
6. 정보 은닉과 캡슐화의 차이는 무엇인가요?
    
7. 추상화란 무엇인가요?
    
8. 상속이란 무엇인가요?
    
9. 다형성이란 무엇인가요?
    
10. 객체지향에서 메시지를 보낸다는 말은 무슨 뜻인가요?
    

## 설계 품질

11. 좋은 객체지향 설계란 무엇이라고 생각하나요?
    
12. 응집도와 결합도를 설명해보세요.
    
13. 높은 응집도와 낮은 결합도가 왜 중요한가요?
    
14. 하나의 클래스가 너무 많은 책임을 가지면 어떤 문제가 생기나요?
    
15. getter/setter를 무분별하게 열면 어떤 문제가 생기나요?
    
16. 객체의 상태를 외부에서 직접 변경하지 못하게 하는 이유는 무엇인가요?
    
17. 불변 객체는 왜 유용한가요?
    
18. 불변 객체를 만들기 위한 조건은 무엇인가요?
    
19. 값 객체와 엔티티 객체의 차이는 무엇인가요?
    
20. DTO와 Domain 객체를 분리하는 이유는 무엇인가요?
    

## 상속 / 인터페이스 / 추상화

21. 상속의 장점과 단점은 무엇인가요?
    
22. 상속보다 조합을 선호하라는 말의 의미는 무엇인가요?
    
23. Composition이 Inheritance보다 나은 경우는 언제인가요?
    
24. 추상 클래스와 인터페이스의 차이는 무엇인가요?
    
25. 인터페이스를 사용하는 이유는 무엇인가요?
    
26. Java에서 클래스 다중 상속을 허용하지 않는 이유는 무엇인가요?
    
27. 인터페이스 다중 구현은 왜 가능한가요?
    
28. default method 충돌은 어떻게 해결하나요?
    
29. 오버로딩과 오버라이딩의 차이는 무엇인가요?
    
30. 오버라이딩 시 접근 제어자를 더 좁힐 수 없는 이유는 무엇인가요?
    

## SOLID

31. SOLID 원칙을 설명해보세요.
    
32. SRP를 위반한 코드의 예시는 무엇인가요?
    
33. OCP를 지키는 설계란 무엇인가요?
    
34. LSP를 위반하면 어떤 문제가 생기나요?
    
35. ISP가 필요한 이유는 무엇인가요?
    
36. DIP는 DI와 어떻게 연결되나요?
    
37. 구현체가 아니라 추상화에 의존한다는 말은 무슨 뜻인가요?
    
38. 의존성 역전과 의존성 주입은 같은 개념인가요?
    
39. SOLID를 과하게 적용하면 어떤 문제가 생기나요?
    
40. 객체지향 설계와 성능은 충돌할 수 있나요?
    

## 패턴 / 실무 설계

41. Strategy Pattern은 어떤 문제를 해결하나요?
    
42. Factory Pattern은 언제 사용하나요?
    
43. Template Method Pattern은 언제 유용한가요?
    
44. Builder Pattern은 왜 사용하나요?
    
45. Singleton Pattern의 장단점은 무엇인가요?
    
46. Singleton이 테스트를 어렵게 만드는 이유는 무엇인가요?
    
47. Adapter Pattern은 어떤 상황에서 사용하나요?
    
48. Facade Pattern은 어떤 장점이 있나요?
    
49. Repository Pattern은 어떤 책임을 가지나요?
    
50. Service Layer는 어떤 책임을 가지나요?
    

## 객체지향 면접 꼬리질문

51. 객체지향적으로 설계했다는 것을 어떻게 판단할 수 있나요?
    
52. 도메인 모델에 비즈니스 로직을 넣는 것에 대해 어떻게 생각하나요?
    
53. Anemic Domain Model이란 무엇인가요?
    
54. Entity에 setter를 열지 않는 이유는 무엇인가요?
    
55. 객체의 책임을 나누는 기준은 무엇인가요?
    
56. 유틸 클래스가 많아지면 객체지향적으로 어떤 문제가 생기나요?
    
57. 상속을 잘못 사용한 예시는 무엇인가요?
    
58. 인터페이스를 너무 많이 만들면 어떤 문제가 생기나요?
    
59. 객체지향과 테스트 용이성은 어떤 관계가 있나요?
    
60. 유지보수하기 좋은 객체지향 코드는 어떤 코드인가요?
    

---

# 4. Spring Boot

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
    
45. Idempotency(멱등성)는 무엇이고 왜 중요한가요?
    

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
    

---

# 5. Spring Boot 운영 / 외부 연동 / 커넥션 풀

## 외부 API 호출 / 복원력

1. `RestTemplate`, `RestClient`, `WebClient`의 차이는 무엇인가요?
    
2. Spring Boot에서 외부 API 호출 시 timeout을 어디에 설정하나요?
    
3. 외부 API 호출 실패 시 retry를 무조건 적용하면 어떤 문제가 생기나요?
    
4. Circuit Breaker는 어떤 문제를 해결하기 위한 패턴인가요?
    
5. 서버가 외부 API에 의존할 때 장애 전파를 막으려면 어떻게 설계해야 하나요?
    
## Connection Pool / 운영

6. HTTP Connection Pool을 사용하는 이유는 무엇인가요?
    
7. Connection Pool을 너무 크게 잡으면 어떤 문제가 생기나요?
    
8. HikariCP는 어떤 역할을 하나요?
    
9. DB Connection Pool이 고갈되면 애플리케이션에는 어떤 증상이 나타나나요?
    
10. Spring Boot Actuator는 운영 관점에서 어떤 용도로 사용하나요?
    

---

# 6. C++ / Modern C++20

## C++ 기본

1. C++의 특징을 설명해보세요.
    
2. C와 C++의 차이는 무엇인가요?
    
3. C++이 절차지향, 객체지향, 제네릭 프로그래밍을 모두 지원한다는 말의 의미는 무엇인가요?
    
4. C++ 컴파일 과정은 어떻게 이루어지나요?
    
5. Header file과 Source file을 분리하는 이유는 무엇인가요?
    
6. Include Guard가 필요한 이유는 무엇인가요?
    
7. `#pragma once`와 Include Guard의 차이는 무엇인가요?
    
8. Namespace를 사용하는 이유는 무엇인가요?
    
9. Header에서 `using namespace std;`를 쓰면 안 되는 이유는 무엇인가요?
    
10. Declaration과 Definition의 차이는 무엇인가요?
    
11. ODR, One Definition Rule이란 무엇인가요?
    
12. Link Error와 Compile Error의 차이는 무엇인가요?
    
13. Static Library와 Dynamic Library의 차이는 무엇인가요?
    
14. CMake를 사용하는 이유는 무엇인가요?
    
15. Debug Build와 Release Build의 차이는 무엇인가요?
    

## Pointer / Reference / const

16. Pointer와 Reference의 차이는 무엇인가요?
    
17. Null Pointer와 Dangling Pointer의 차이는 무엇인가요?
    
18. `nullptr`가 `NULL`보다 나은 이유는 무엇인가요?
    
19. `const int*`, `int* const`, `const int* const`의 차이는 무엇인가요?
    
20. const correctness가 왜 중요한가요?
    
21. `static` 키워드는 C++에서 어떤 의미를 가지나요?
    
22. 전역 변수를 조심해야 하는 이유는 무엇인가요?
    
23. Macro와 inline function의 차이는 무엇인가요?
    
24. `enum`과 `enum class`의 차이는 무엇인가요?
    
25. `auto`를 사용할 때 주의할 점은 무엇인가요?
    

## 객체지향 C++

26. `class`와 `struct`의 차이는 무엇인가요?
    
27. 생성자와 소멸자의 역할은 무엇인가요?
    
28. Copy Constructor란 무엇인가요?
    
29. Move Constructor란 무엇인가요?
    
30. Copy Assignment와 Move Assignment의 차이는 무엇인가요?
    
31. Rule of Three를 설명해보세요.
    
32. Rule of Five를 설명해보세요.
    
33. Rule of Zero를 설명해보세요.
    
34. Virtual Destructor가 필요한 이유는 무엇인가요?
    
35. Virtual Function은 어떻게 동작하나요?
    
36. Pure Virtual Function이란 무엇인가요?
    
37. Abstract Class란 무엇인가요?
    
38. vtable이란 무엇인가요?
    
39. Dynamic Dispatch는 어떻게 동작하나요?
    
40. 다중 상속의 문제점은 무엇인가요?
    
41. Diamond Problem이란 무엇인가요?
    
42. Virtual Inheritance는 어떤 문제를 해결하나요?
    
43. Function Overloading과 Overriding의 차이는 무엇인가요?
    
44. Object Slicing이란 무엇인가요?
    
45. C++에서 상속(가상 함수) 기반 다형성을 쓰기보다 Composition이나 정적 다형성(Template)을 선택하는 기준은 무엇인가요?
    
## Move / Template / STL

46. Move Semantics가 필요한 이유는 무엇인가요?
    
47. lvalue와 rvalue의 차이는 무엇인가요?
    
48. rvalue reference란 무엇인가요?
    
49. `std::move`는 실제로 객체를 이동시키나요?
    
50. Perfect Forwarding이란 무엇인가요?
    
51. STL의 주요 구성 요소를 설명해보세요.
    
52. `vector`와 `array`의 차이는 무엇인가요?
    
53. `vector`와 `list`의 차이는 무엇인가요?
    
54. `vector`에서 `reserve()`와 `resize()`의 차이는 무엇인가요?
    
55. `map`과 `unordered_map`의 차이는 무엇인가요?
    
56. Iterator invalidation이란 무엇인가요?
    
57. Template을 사용하는 이유는 무엇인가요?
    
58. Template Specialization이란 무엇인가요?
    
59. Compile-time Polymorphism과 Runtime Polymorphism의 차이는 무엇인가요?
    
60. `constexpr`은 어떤 상황에서 사용하나요?
    
## C++20 변화

61. C++20의 `concept`은 Template 코드의 어떤 문제를 해결하나요?
    
62. C++20의 coroutine은 어떤 상황에서 유용한가요?
    

---

# 7. C++ 메모리 / 스레딩 / 네트워크

## 메모리 / RAII / 스마트 포인터

1. C++에서 메모리 관리를 개발자가 직접 신경 써야 하는 이유는 무엇인가요?
    
2. Stack 객체와 Heap 객체의 차이는 무엇인가요?
    
3. C++에서 메모리 누수가 발생하는 대표적인 경우는 무엇인가요?
    
4. Dangling Pointer가 발생하는 대표적인 경우는 무엇인가요?
    
5. Double Free는 왜 위험한가요?
    
6. RAII란 무엇인가요?
    
7. RAII가 예외 안정성과 어떤 관련이 있나요?
    
8. `new/delete`를 직접 사용하는 것이 위험한 이유는 무엇인가요?
    
9. Smart Pointer를 사용하는 이유는 무엇인가요?
    
10. `unique_ptr`은 언제 사용하나요?
    
11. `shared_ptr`은 언제 사용하나요?
    
12. `weak_ptr`은 왜 필요한가요?
    
13. shared_ptr 순환 참조 문제를 설명해보세요.
    
14. `make_unique`와 `make_shared`를 사용하는 이유는 무엇인가요?
    
15. Shallow Copy와 Deep Copy의 차이는 무엇인가요?
    
16. Memory Alignment란 무엇인가요?
    
17. Cache Locality가 성능에 미치는 영향은 무엇인가요?
    
18. Stack Overflow는 언제 발생하나요?
    
19. Heap Fragmentation이란 무엇인가요?
    
20. 실시간 처리 코드에서 동적 할당을 줄여야 하는 이유는 무엇인가요?
    
## 멀티스레딩

21. C++에서 `std::thread`는 어떻게 사용하나요?
    
22. `join()`과 `detach()`의 차이는 무엇인가요?
    
23. `std::mutex`는 어떤 문제를 해결하나요?
    
24. `std::lock_guard`와 `std::unique_lock`의 차이는 무엇인가요?
    
25. `std::condition_variable`은 어떤 상황에서 사용하나요?
    
26. `std::atomic`은 어떤 상황에서 사용하나요?
    
27. mutex와 atomic의 차이는 무엇인가요?
    
28. Producer-Consumer 패턴을 C++에서 어떻게 구현할 수 있나요?
    
## Network

29. C++ 표준 라이브러리만으로 네트워크 프로그래밍이 제한적인 이유는 무엇인가요?
    
30. TCP와 UDP를 C++에서 사용할 때 보통 어떤 API나 라이브러리를 사용하나요?
    
31. TCP stream에서 message boundary가 없다는 말은 무슨 뜻인가요?
    
32. 네트워크로 구조체를 그대로 전송하면 어떤 문제가 생길 수 있나요?
    
33. Endian 문제는 네트워크 프로그래밍에서 왜 중요한가요?
    
34. `htonl`, `ntohl`, `htons`, `ntohs`는 어떤 역할을 하나요?
    
35. Socket 자원을 RAII로 관리하면 어떤 장점이 있나요?
    
36. 네트워크 read/write에서 부분 송수신이 발생할 수 있는 이유는 무엇인가요?
    
## Build / Linking

37. Header-only library의 장단점은 무엇인가요?
    
38. ABI 호환성이란 무엇인가요?
    
39. Debug/Release 빌드에서 동작이 달라질 수 있는 이유는 무엇인가요?
    
40. 정적 링크와 동적 링크를 선택하는 기준은 무엇인가요?
    
41. CMake에서 target 단위로 include path와 link library를 관리하는 이유는 무엇인가요?
    

---

# 8. Docker / Container / Network

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
    

---

# 9. GitHub Actions / GitLab CI

## CI/CD 기본

1. CI와 CD의 차이는 무엇인가요?
    
2. CI/CD를 사용하는 이유는 무엇인가요?
    
3. Pipeline이란 무엇인가요?
    
4. Job과 Step의 차이는 무엇인가요?
    
5. CI에서 테스트를 자동화하는 이유는 무엇인가요?
    
6. PR 또는 MR 단위로 CI를 돌리는 이유는 무엇인가요?
    
7. main branch merge 후 CD를 돌리는 일반적인 이유는 무엇인가요?
    
8. CI 실패를 무시하면 어떤 문제가 생기나요?
    
9. Branch Protection 또는 Merge Rule은 왜 필요한가요?
    
10. Required Check가 필요한 이유는 무엇인가요?
    

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
    

---

# 10. Nginx / Reverse Proxy

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
    
34. Cache-Control Header는 어떤 역할을 하나요?
    
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
    

---

# 11. Web / HTTP / 인증 / CORS / DNS

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

41. 인증과 인가의 차이는 무엇인가요?
    
42. Session 기반 인증은 어떻게 동작하나요?
    
43. JWT 기반 인증은 어떻게 동작하나요?
    
44. Access Token과 Refresh Token의 차이는 무엇인가요?
    
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
---

# 우선순위

면접 대비용이면 이 순서로 보면 된다.

1. **Java/JVM + Spring Boot**
    
2. **객체지향**
    
3. **C++ 메모리 관리 + Modern C++**
    
4. **멀티스레딩: Java Executor/Virtual Thread, Spring Singleton Bean, C++ thread/atomic**
    
5. **Docker + CI/CD**
    
6. **Nginx + HTTP + 인증/CORS**
    
7. **웹소켓/실시간 통신**
    

특히 너한테 중요한 건 이 축이다.

```text
Java/Spring: JVM 메모리, GC, Singleton Bean 동시성, Transaction ThreadLocal, Virtual Thread
C++: RAII, smart pointer, move semantics, thread/mutex/atomic, C++20 concept/coroutine
배포: Docker image/container/volume/network, CI pipeline, secret 관리
웹: HTTP, CORS, Cookie/JWT, Nginx reverse proxy, WebSocket
```
