# Java Collection / 동시성 / 네트워크

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
