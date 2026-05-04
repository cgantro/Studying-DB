# C++ 메모리 / 스레딩 / 네트워크

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
