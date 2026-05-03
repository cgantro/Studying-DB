# Java 기본 - 답변 정리

`CS공부/12_면접/05-Java-질문-100개.md`의 **Java 기본(1~20번)** 답변만 분리한 문서다.  
각 답변 하단에 관련 개념 정리 링크를 붙였다.

---

## 1. Java의 특징을 설명해보세요.
### 답변(면접용)
- Java는 **JVM 위에서 동작**하는 정적 타입 객체지향 언어다.
- 소스 코드를 바이트코드로 컴파일하고, JVM이 인터프리터/JIT로 실행한다.
- 메모리는 런타임이 GC로 관리해서 메모리 안전성을 높인다.

개념: [[CS공부/언어/Java/04_Java 기본#Java의 특징]]

---

## 2. JVM, JRE, JDK의 차이를 설명해보세요.
### 답변(면접용)
- JVM은 **바이트코드를 실행**하는 가상 머신이다(클래스 로딩, 실행 엔진, GC 포함).
- JRE는 **실행 환경**이다(JVM + 표준 라이브러리).
- JDK는 **개발 도구 모음**이다(JRE + `javac`, 디버거, 진단 도구 등).

개념: [[CS공부/언어/Java/04_Java 기본#JVM / JRE / JDK]]

---

## 3. Java가 플랫폼 독립적이라고 하는 이유는 무엇인가요?
### 답변(면접용)
- Java는 OS/CPU용 기계어가 아니라 JVM용 **바이트코드**로 컴파일한다.
- 각 플랫폼에 맞는 JVM이 바이트코드를 실행해 주기 때문에, 같은 `.class`가 여러 환경에서 동작한다.

개념: [[CS공부/언어/Java/04_Java 기본#Bytecode(.class)]]

---

## 4. bytecode란 무엇인가요?
### 답변(면접용)
- `javac`가 `.java`를 컴파일해서 만드는 **JVM용 중간 코드**다(`.class` 파일).
- JVM이 로딩/검증 후 실행한다.

개념: [[CS공부/언어/Java/04_Java 기본#Bytecode(.class)]]

---

## 5. Java 컴파일 과정과 실행 과정을 설명해보세요.
### 답변(면접용)
- 컴파일: `.java` → `javac` → `.class`(바이트코드)
- 실행: JVM이 클래스를 로딩/검증하고, 인터프리터로 실행을 시작한다.
- 실행 중 자주 호출되는 코드는 JIT가 기계어로 컴파일해 성능을 끌어올린다.

개념: [[CS공부/언어/Java/04_Java 기본#Java 컴파일/실행 과정]]

---

## 6. `public static void main(String[] args)`의 각 키워드를 설명해보세요.
### 답변(면접용)
- `public`: JVM이 외부에서 엔트리포인트를 호출할 수 있게 공개.
- `static`: 객체 생성 없이 클래스 레벨로 호출 가능.
- `void`: 반환값 없음.
- `main`: JVM이 찾는 약속된 메서드 이름.
- `String[] args`: 커맨드라인 인자.

개념: [[CS공부/언어/Java/04_Java 기본#`public static void main(String[] args)`]]

---

## 7. primitive type과 reference type의 차이는 무엇인가요?
### 답변(면접용)
- primitive는 **값 자체**를 담고, reference는 **객체를 가리키는 참조값**을 담는다.
- reference 타입의 “객체 본체”는 보통 힙에 있고, 지역 변수로 들고 있는 참조값은 스택 프레임에 잡힌다.

개념: [[CS공부/언어/Java/04_Java 기본#Primitive type vs Reference type]]

---

## 8. Java에서 `int`와 `Integer`의 차이는 무엇인가요?
### 답변(면접용)
- `int`는 primitive라서 값 자체를 담고, `Integer`는 wrapper 객체라서 reference 타입이다.
- 컬렉션/제네릭에 넣을 때는 primitive를 직접 담을 수 없어 wrapper가 필요하다.
- wrapper는 `null`이 가능하고, 오토박싱/언박싱이 섞이면 성능/예외 이슈가 생길 수 있다.

개념: [[CS공부/언어/Java/04_Java 기본#Primitive type vs Reference type]]  
개념: [[CS공부/언어/Java/04_Java 기본#Autoboxing / Unboxing]]

---

## 9. autoboxing과 unboxing이란 무엇인가요?
### 답변(면접용)
- autoboxing은 primitive를 wrapper로 자동 변환하는 것(`int` → `Integer`).
- unboxing은 wrapper를 primitive로 자동 변환하는 것(`Integer` → `int`).
- `null` wrapper를 unboxing하면 `NullPointerException`이 날 수 있다.

개념: [[CS공부/언어/Java/04_Java 기본#Autoboxing / Unboxing]]

---

## 10. autoboxing이 성능 문제를 만들 수 있는 경우는 언제인가요?
### 답변(면접용)
- 반복문/대량 연산에서 boxing/unboxing이 반복되면 객체 생성과 GC 부담이 커진다.
- 가능하면 primitive 특화 타입/스트림(`IntStream` 등)이나 자료구조 선택으로 boxing을 줄인다.

개념: [[CS공부/언어/Java/04_Java 기본#Autoboxing / Unboxing]]

---

## 11. `==`와 `equals()`의 차이는 무엇인가요?
### 답변(면접용)
- `==`는 primitive는 값 비교, reference는 참조 동일성 비교다.
- `equals()`는 객체의 논리적 동등성 비교를 위해 제공되고, 클래스가 재정의할 수 있다.

개념: [[CS공부/언어/Java/04_Java 기본#`==` vs `equals()` vs `hashCode()`]]

---

## 12. `equals()`와 `hashCode()`를 같이 재정의해야 하는 이유는 무엇인가요?
### 답변(면접용)
- 해시 컬렉션(`HashMap`, `HashSet`)의 계약 때문이다.
- `equals()`가 `true`인 객체는 반드시 같은 `hashCode()`를 가져야 버킷 탐색이 일관된다.

개념: [[CS공부/언어/Java/04_Java 기본#`==` vs `equals()` vs `hashCode()`]]

---

## 13. `String`은 왜 immutable인가요?
### 답변(면접용)
- 문자열은 공유/재사용되는 경우가 많아서, 값이 바뀌면 안전하지 않다(특히 String Pool).
- immutable이면 `hashCode()` 캐싱 같은 최적화가 가능하고, 공유가 쉬워 멀티스레드에서 다루기 유리하다.

개념: [[CS공부/언어/Java/04_Java 기본#`String` immutability와 String Pool]]

---

## 14. `String`, `StringBuilder`, `StringBuffer`의 차이는 무엇인가요?
### 답변(면접용)
- `String`은 불변이라 잦은 연결/수정에서 객체가 많이 생길 수 있다.
- `StringBuilder`는 가변이고 동기화가 없어 단일 스레드에서 빠르다.
- `StringBuffer`는 가변이지만 동기화가 있어 멀티스레드에서 안전하게 쓰기 좋다(대신 오버헤드가 있을 수 있다).

개념: [[CS공부/언어/Java/04_Java 기본#`String` / `StringBuilder` / `StringBuffer`]]

---

## 15. 문자열 비교 시 `==`를 쓰면 안 되는 이유는 무엇인가요?
### 답변(면접용)
- `==`는 reference 타입에서 “내용”이 아니라 “참조 동일성”을 비교한다.
- 내용 비교는 `equals()`를 써야 하고, 정렬/대소문자 무시 등 조건이 있으면 그에 맞는 메서드를 선택한다.

개념: [[CS공부/언어/Java/04_Java 기본#`==` vs `equals()` vs `hashCode()`]]

---

## 16. String Pool이란 무엇인가요?
### 답변(면접용)
- JVM이 문자열 리터럴을 재사용하기 위해 관리하는 풀이다.
- 같은 리터럴 문자열을 여러 번 써도 재사용될 수 있어 메모리 절약에 도움이 된다.

개념: [[CS공부/언어/Java/04_Java 기본#`String` immutability와 String Pool]]

---

## 17. `final` 키워드는 변수, 메서드, 클래스에서 각각 어떤 의미인가요?
### 답변(면접용)
- 변수: 재할당을 막는다(참조 변수면 “참조 변경”만 막고 객체 내부 변경까지 막는 건 아님).
- 메서드: 오버라이딩을 막는다.
- 클래스: 상속을 막는다.

개념: [[CS공부/언어/Java/04_Java 기본#`final`]]

---

## 18. `static` 키워드의 의미는 무엇인가요?
### 답변(면접용)
- 인스턴스가 아니라 클래스에 귀속되는 멤버라는 뜻이다.
- 모든 인스턴스가 값을 공유하므로 전역 상태처럼 동작할 수 있어, 동시성/테스트 관점에서 신중하게 써야 한다.

개념: [[CS공부/언어/Java/04_Java 기본#`static`]]

---

## 19. static 메서드에서 instance 변수에 직접 접근할 수 없는 이유는 무엇인가요?
### 답변(면접용)
- static 메서드는 객체가 없어도 호출되는데, instance 변수는 객체마다 값이 다르다.
- 어떤 객체의 필드에 접근할지 결정할 수 없기 때문에 “직접 접근”이 불가능하고, 인스턴스를 통해 접근해야 한다.

개념: [[CS공부/언어/Java/04_Java 기본#`static`]]

---

## 20. Java에서 pass-by-value라는 말의 의미는 무엇인가요?
### 답변(면접용)
- Java는 항상 “값 복사”로 인자를 전달한다(pass-by-value).
- reference type도 예외가 아니라, 객체 자체가 아니라 **참조값이 복사**되어 전달되는 것이다.

개념: [[CS공부/언어/Java/04_Java 기본#Java는 pass-by-value인가?]]

