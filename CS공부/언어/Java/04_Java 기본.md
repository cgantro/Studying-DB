# Java 기본

## Java의 특징
### 개념
- Java는 JVM 위에서 동작하는 정적 타입(Static Typing) 객체지향 언어다.
- 소스(`.java`)를 JVM용 바이트코드(`.class`)로 컴파일하고, 런타임에 JVM이 이를 실행한다.
- 런타임이 GC로 메모리를 관리한다.

### 왜 필요한가
- **플랫폼 독립성**: 운영체제/CPU가 달라도 “JVM만 있으면” 동일한 바이트코드를 실행한다.
- **안전/생산성**: 포인터 산술 같은 위험을 줄이고, 표준 라이브러리와 생태계가 크다.

### 동작 원리(요약)
- JVM은 클래스를 로딩/검증한 뒤, 인터프리터와 JIT 컴파일러를 함께 사용해 실행한다.
- “자주 실행되는 코드(Hot)”는 JIT가 기계어로 컴파일해 이후 실행 속도를 올린다.

### 장단점 / 한계
- 장점: 이식성, 생태계, 런타임 최적화(JIT), GC로 인한 메모리 안전성.
- 한계: 워밍업(초기 JIT 전), GC pause 가능성, 런타임/메모리 오버헤드.

---

## JVM / JRE / JDK
### 정의
- **JVM**: 바이트코드를 실행하는 가상 머신(클래스 로딩, 실행 엔진, GC 등 포함).
- **JRE**: “실행 환경” (JVM + 표준 라이브러리 등 런타임 구성 요소).
- **JDK**: “개발 도구” (JRE + `javac`, 디버거, 빌드/진단 도구 등).

### 실무 관점 포인트
- 서버 운영에서 JVM 튜닝이라고 하면 보통 **GC/메모리/스레드/클래스 로딩/옵션** 조합을 의미한다.
- 개발자는 JDK를 설치하고, 배포 환경은 JRE 또는 JDK(진단 도구 필요 시)를 쓴다.

---

## Bytecode(.class)
### 개념
- Java 소스를 컴파일(`javac`)하면 생성되는 **JVM용 중간 표현**이다.
- OS/CPU에 종속적인 기계어가 아니라, JVM이 이해하는 명령 집합이다.

### 왜 필요한가
- 같은 `.class`를 여러 OS에서 실행(플랫폼 독립).
- 실행 전 **바이트코드 검증**으로 안전성(타입/스택 사용 등) 확보에 도움.

---

## Java 컴파일/실행 과정
### 흐름(요약)
1. `.java` → `javac` → `.class`(바이트코드)
2. JVM: Class Loader가 클래스 로딩
3. JVM: Bytecode Verifier가 검증
4. JVM: 인터프리터로 실행 시작
5. JVM: 자주 실행되는 코드(Hot Spot)를 JIT로 컴파일해 최적화

### 런타임 메모리(키워드)
- (개념 연결) 스택/힙, 메서드 영역(메타데이터), GC Root 등은 `[[CS공부/언어/Java/03_JVM 메모리와 GC 실무]]`로 확장.

---

## `public static void main(String[] args)`
### 각 키워드 의미
- `public`: JVM이 어디서든 엔트리포인트를 호출할 수 있게 공개.
- `static`: 인스턴스 생성 없이 클래스 수준에서 호출 가능(프로그램 시작 시점에 객체가 없을 수 있음).
- `void`: 반환값 없음(프로세스 종료 코드는 관례적으로 예외/시스템 호출로 처리).
- `main`: JVM이 찾는 약속된 메서드 이름.
- `String[] args`: 커맨드라인 인자 전달.

---

## Primitive type vs Reference type
### 개념
- **Primitive**: 값 자체를 담는 타입(`int`, `long`, `boolean` 등).
- **Reference**: 객체를 가리키는 참조값을 담는 타입(클래스 인스턴스, 배열 등).

### 메모리 관점(주의점)
- “지역 변수”의 값(primitive 값, reference 값)은 보통 스택 프레임에 잡힌다.
- “객체 본체”는 힙에 생성된다(대부분의 일반적인 객체/배열).

### 실무 포인트
- 컬렉션/제네릭은 참조 타입만 담는다 → primitive는 wrapper(`Integer` 등)로 박싱된다.

---

## Autoboxing / Unboxing
### 정의
- **Autoboxing**: primitive → wrapper로 자동 변환 (`int` → `Integer`)
- **Unboxing**: wrapper → primitive로 자동 변환 (`Integer` → `int`)

### 위험 포인트
- wrapper가 `null`이면 unboxing 시 `NullPointerException`이 날 수 있다.
- 반복문/대량 처리에서 boxing/unboxing이 반복되면 객체 생성/GC 부담으로 성능 문제가 될 수 있다.

---

## `==` vs `equals()` vs `hashCode()`
### `==`와 `equals()`
- `==`: primitive는 “값”, reference는 “참조(주소) 동일성”을 비교한다.
- `equals()`: 객체의 “논리적 동등성” 비교를 위한 메서드(클래스가 재정의 가능).

### `equals()`와 `hashCode()`를 같이 재정의해야 하는 이유
- `HashMap/HashSet` 같은 해시 기반 컬렉션의 계약(Contract) 때문이다.
- `equals()`가 `true`인 두 객체는 **같은 `hashCode()`**를 반환해야 해시 버킷 탐색이 일관된다.

---

## `String` immutability와 String Pool
### `String`이 immutable인 이유(대표 포인트)
- 문자열 리터럴 재사용(String Pool) 시, 값이 바뀌면 전역적으로 영향이 생길 수 있어 안전하지 않다.
- `hashCode()` 캐싱 등 최적화에 유리하다.
- 공유가 쉬워 멀티스레드 환경에서 안전하게 다루기 유리하다(단, “모든 문자열 조작이 안전하다”와는 다른 얘기).

### String Pool
- JVM이 문자열 리터럴을 재사용하기 위한 풀(공유 저장소)이다.
- 동일한 문자열 리터럴이 여러 번 등장해도 재사용될 수 있다.

---

## `String` / `StringBuilder` / `StringBuffer`
### 차이
- `String`: 불변(immutable)
- `StringBuilder`: 가변(mutable), 동기화 없음(단일 스레드에 유리)
- `StringBuffer`: 가변(mutable), 동기화 있음(멀티스레드에서 안전하지만 오버헤드 가능)

---

## `final`
### 의미
- 변수: 재할당 금지(참조 변수면 “참조 변경”만 막고, 객체 내부 변경까지 막는 건 아님)
- 메서드: 오버라이딩 금지
- 클래스: 상속 금지

---

## `static`
### 의미
- 인스턴스가 아니라 **클래스에 귀속**되는 멤버(공유 상태).

### `static` 메서드에서 인스턴스 변수 접근이 제한되는 이유
- `static`은 인스턴스가 없어도 호출되므로 “어느 객체의 필드인지”가 정해지지 않는다.
- 접근하려면 인스턴스 참조를 받아서 쓰거나, 인스턴스 메서드에서 다루는 게 안전하다.

---

## Java는 pass-by-value인가?
### 결론
- Java는 **항상 pass-by-value**다.

### 오해가 생기는 이유
- reference type을 인자로 넘길 때 “객체 자체”가 아니라 “참조값”이 복사되어 전달된다.
- 그래서 메서드 안에서 객체의 내부 상태 변경은 호출자에서도 보이지만, 참조 자체를 다른 객체로 바꾸는 것은 호출자에 반영되지 않는다.

