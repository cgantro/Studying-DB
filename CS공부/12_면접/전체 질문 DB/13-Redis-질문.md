# Redis / Cache

## Redis 기본

1. Redis는 무엇인가요?
    
2. Redis를 사용하는 이유는 무엇인가요?
    
3. Redis는 “DB”인가요, “Cache”인가요?
    
4. Redis가 인메모리인데도 영속성(persistence)을 지원하는 이유는 무엇인가요?
    
5. Redis가 빠른 이유는 무엇인가요?
    
6. Redis는 싱글 스레드라고 하는데, 어떤 의미인가요?
    
7. Redis에서 key 설계 시 주의할 점은 무엇인가요?
    
8. Redis value 직렬화(Serialization)에서 주의할 점은 무엇인가요?
    
9. Redis에서 O(1)이라고 해도 느려질 수 있는 이유는 무엇인가요?
    
10. Redis 커넥션을 매 요청마다 새로 만들면 안 되는 이유는 무엇인가요?

## 자료구조 / 명령

11. Redis String은 어떤 상황에서 사용하나요?
    
12. `INCR/DECR` 같은 카운터는 왜 원자적(atomic)이라고 말할 수 있나요?
    
13. Redis Hash는 어떤 상황에서 유용한가요?
    
14. Hash로 사용자 프로필을 저장하는 것과 JSON 문자열로 저장하는 것의 차이는 무엇인가요?
    
15. Redis List는 어떤 상황에서 사용하나요?
    
16. Redis Set은 어떤 상황에서 사용하나요?
    
17. Redis Sorted Set(ZSET)은 어떤 상황에서 사용하나요?
    
18. ZSET에서 score와 rank의 차이는 무엇인가요?
    
19. Redis Bitmap은 어떤 상황에서 유용한가요?
    
20. HyperLogLog는 어떤 문제를 해결하나요?
    
21. Redis Bloom Filter(또는 Cuckoo Filter)는 어떤 상황에서 사용하나요?
    
22. Redis GEO는 어떤 기능을 제공하나요?
    
23. Pub/Sub와 Streams의 차이는 무엇인가요?
    
24. Redis Streams는 어떤 문제를 해결하기 위한 구조인가요?
    
25. Redis에서 `SCAN`을 `KEYS`보다 선호하는 이유는 무엇인가요?

## TTL / 만료 / Eviction / 캐시 패턴

26. TTL은 무엇이고, 왜 필요한가요?
    
27. TTL을 설정하지 않으면 어떤 문제가 생길 수 있나요?
    
28. Cache-aside 패턴은 무엇인가요?
    
29. Write-through / Write-behind(Write-back)의 차이는 무엇인가요?
    
30. 캐시 스탬피드(Cache Stampede)란 무엇이고, 어떻게 완화하나요?
    
31. 캐시 관통(Cache Penetration)이란 무엇이고, 어떻게 완화하나요?
    
32. 캐시 붕괴(Cache Avalanche)란 무엇이고, 어떻게 완화하나요?
    
33. Hot key 문제는 무엇이고, 어떻게 완화하나요?
    
34. Redis eviction 정책이란 무엇인가요?
    
35. `volatile-lru`와 `allkeys-lru`는 어떤 차이가 있나요?
    
36. 만료 키 삭제는 즉시 일어나나요? (lazy expiration / active expiration)
    
37. TTL을 랜덤 지터(jitter)로 흩뿌리는 이유는 무엇인가요?

## Persistence (RDB / AOF)

38. RDB 스냅샷 방식의 장단점은 무엇인가요?
    
39. AOF(Append Only File) 방식의 장단점은 무엇인가요?
    
40. AOF의 fsync 정책(always/everysec/no)은 무엇을 의미하나요?
    
41. AOF rewrite(rewrite/compaction)는 왜 필요한가요?
    
42. RDB와 AOF를 함께 쓰는 전략은 어떤 장단점이 있나요?
    
43. Redis 장애 시 데이터 유실을 줄이려면 어떤 옵션/구성을 고려하나요?
    
44. 캐시 용도 Redis에서 “데이터 유실”을 어느 정도까지 허용할지 어떻게 결정하나요?

## Replication / Sentinel / Cluster

45. Redis Replication의 목적은 무엇인가요?
    
46. Read Replica를 둘 때 장점과 주의점은 무엇인가요?
    
47. Replication lag이 문제가 되는 경우는 언제인가요?
    
48. Sentinel은 어떤 역할을 하나요?
    
49. Failover 과정에서 클라이언트는 어떤 문제를 겪을 수 있나요?
    
50. Redis Cluster는 어떤 문제를 해결하나요?
    
51. Cluster의 샤딩 단위는 무엇이고, 키는 어떻게 분배되나요?
    
52. Redis Cluster에서 multi-key 연산이 제한되는 이유는 무엇인가요?
    
53. Hash tag(`{...}`)는 어떤 상황에서 사용하나요?
    
54. Cluster에서 리샤딩(resharding)은 어떤 상황에서 필요하나요?
    
55. 클러스터/레플리카 환경에서 “쓰기/읽기 일관성”은 어떻게 설명하나요?
    
56. Redis는 분산 트랜잭션(2PC) 같은 것을 기본 제공하나요?

## Transaction / Lua / Pipeline

57. Redis 트랜잭션(MULTI/EXEC)은 어떤 보장을 제공하나요?
    
58. WATCH는 어떤 문제를 해결하나요?
    
59. Lua 스크립트는 어떤 상황에서 유용한가요?
    
60. Lua 스크립트에서 주의할 점은 무엇인가요?
    
61. Pipeline은 무엇이고, 어떤 상황에서 효과가 있나요?
    
62. Pipeline과 트랜잭션은 무엇이 다른가요?
    
63. 분산 락(Distributed Lock)을 Redis로 구현할 때 주의할 점은 무엇인가요?
    
64. Redlock은 무엇이고, 실무에서 어떻게 접근하는 게 안전한가요?

## 운영 / 장애 / 모니터링

65. Redis 메모리 사용량이 계속 증가할 때 어떤 원인을 의심하나요?
    
66. 메모리 단편화(fragmentation)는 무엇이고, 어떤 문제가 되나요?
    
67. `maxmemory`를 설정할 때 주의할 점은 무엇인가요?
    
68. Redis가 느려졌을 때 어떤 순서로 분석하겠나요?
    
69. `INFO`, `SLOWLOG`는 어떤 상황에서 사용하나요?
    
70. 백업/복구 관점에서 Redis 운영 체크리스트는 무엇인가요?

## 보안

71. Redis를 외부에 그대로 노출하면 위험한 이유는 무엇인가요?
    
72. Redis ACL/권한 관리는 어떤 식으로 접근하나요?

