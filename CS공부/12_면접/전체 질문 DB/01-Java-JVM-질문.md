# Java / JVM

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
