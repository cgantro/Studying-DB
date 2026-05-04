# DB / SQL / PostgreSQL

## DB 기본

1. 데이터베이스를 사용하는 이유는 무엇인가요?
    
2. 파일 시스템에 데이터를 저장하는 것과 DB를 사용하는 것의 차이는 무엇인가요?
    
3. RDBMS란 무엇인가요?
    
4. 관계형 데이터베이스의 핵심 특징은 무엇인가요?
    
5. 테이블, 행, 열의 개념을 설명해보세요.
    
6. Primary Key는 무엇인가요?
    
7. Foreign Key는 무엇인가요?
    
8. Unique 제약조건은 무엇인가요?
    
9. NOT NULL 제약조건은 왜 사용하나요?
    
10. CHECK 제약조건은 어떤 상황에서 사용하나요?
    
11. Primary Key와 Unique Key의 차이는 무엇인가요?
    
12. Natural Key와 Surrogate Key의 차이는 무엇인가요?
    
13. Auto Increment ID를 사용할 때 장단점은 무엇인가요?
    
14. UUID를 Primary Key로 사용할 때 장단점은 무엇인가요?
    
15. 데이터 무결성이란 무엇인가요?
    
## SQL 기본

16. SELECT 문의 기본 실행 흐름을 설명해보세요.
    
17. WHERE와 HAVING의 차이는 무엇인가요?
    
18. GROUP BY는 언제 사용하나요?
    
19. ORDER BY는 어떤 비용을 만들 수 있나요?
    
20. LIMIT과 OFFSET은 어떤 역할을 하나요?
    
21. INSERT, UPDATE, DELETE의 차이를 설명해보세요.
    
22. JOIN이란 무엇인가요?
    
23. INNER JOIN과 LEFT JOIN의 차이는 무엇인가요?
    
24. RIGHT JOIN과 FULL OUTER JOIN은 언제 사용하나요?
    
25. CROSS JOIN은 어떤 결과를 만드나요?
    
26. 서브쿼리란 무엇인가요?
    
27. 서브쿼리와 JOIN 중 어떤 것을 선택할지 어떻게 판단하나요?
    
28. EXISTS와 IN의 차이는 무엇인가요?
    
29. COUNT(*), COUNT(컬럼), COUNT(DISTINCT 컬럼)의 차이는 무엇인가요?
    
30. NULL 비교에서 = NULL이 아니라 IS NULL을 써야 하는 이유는 무엇인가요?
    
## 정규화 / 모델링

31. 정규화란 무엇인가요?
    
32. 정규화를 하는 이유는 무엇인가요?
    
33. 제1정규형은 무엇인가요?
    
34. 제2정규형은 무엇인가요?
    
35. 제3정규형은 무엇인가요?
    
36. 반정규화란 무엇인가요?
    
37. 반정규화는 언제 고려할 수 있나요?
    
38. 정규화를 너무 많이 하면 어떤 문제가 생길 수 있나요?
    
39. 일대일, 일대다, 다대다 관계를 설명해보세요.
    
40. 다대다 관계를 RDB에서 어떻게 표현하나요?
    
41. 중간 테이블을 설계할 때 주의할 점은 무엇인가요?
    
42. ERD를 설계할 때 가장 먼저 봐야 하는 것은 무엇인가요?
    
43. 컬럼 타입을 정할 때 고려할 기준은 무엇인가요?
    
44. 문자열 타입과 숫자 타입을 잘못 선택하면 어떤 문제가 생기나요?
    
45. 날짜와 시간 데이터를 저장할 때 주의할 점은 무엇인가요?
    
## 트랜잭션 / ACID

46. 트랜잭션이란 무엇인가요?
    
47. ACID를 설명해보세요.
    
48. Atomicity는 어떤 의미인가요?
    
49. Consistency는 어떤 의미인가요?
    
50. Isolation은 어떤 의미인가요?
    
51. Durability는 어떤 의미인가요?
    
52. Commit과 Rollback의 차이는 무엇인가요?
    
53. 트랜잭션을 너무 길게 유지하면 어떤 문제가 생기나요?
    
54. 동시에 같은 데이터를 수정하면 어떤 문제가 발생할 수 있나요?
    
55. Dirty Read란 무엇인가요?
    
56. Non-repeatable Read란 무엇인가요?
    
57. Phantom Read란 무엇인가요?
    
58. Isolation Level이 필요한 이유는 무엇인가요?
    
59. Read Committed와 Repeatable Read의 차이는 무엇인가요?
    
60. Serializable 격리 수준은 어떤 장단점이 있나요?
    
## Lock / 동시성 제어

61. DB Lock은 왜 필요한가요?
    
62. Shared Lock과 Exclusive Lock의 차이는 무엇인가요?
    
63. Row-level Lock과 Table-level Lock의 차이는 무엇인가요?
    
64. Deadlock은 DB에서 어떻게 발생하나요?
    
65. Deadlock이 발생했을 때 DB는 어떻게 처리하나요?
    
66. Deadlock을 줄이기 위한 방법은 무엇인가요?
    
67. Optimistic Lock과 Pessimistic Lock의 차이는 무엇인가요?
    
68. Optimistic Lock은 어떤 상황에서 적합한가요?
    
69. Pessimistic Lock은 어떤 상황에서 적합한가요?
    
70. SELECT FOR UPDATE는 어떤 상황에서 사용하나요?
    
## Index 기본

71. Index란 무엇인가요?
    
72. Index를 사용하는 이유는 무엇인가요?
    
73. Index를 걸면 조회가 항상 빨라지나요?
    
74. Index가 INSERT, UPDATE, DELETE 성능에 영향을 주는 이유는 무엇인가요?
    
75. B-Tree Index는 어떤 방식으로 동작하나요?
    
76. 인덱스를 걸기 좋은 컬럼의 특징은 무엇인가요?
    
77. 카디널리티가 낮은 컬럼에 인덱스를 걸면 효과가 적은 이유는 무엇인가요?
    
78. 복합 인덱스란 무엇인가요?
    
79. 복합 인덱스에서 컬럼 순서가 중요한 이유는 무엇인가요?
    
80. LIKE '%keyword%' 검색에서 일반 B-Tree 인덱스가 잘 안 먹는 이유는 무엇인가요?
    
## Query 성능 / 실행 계획

81. 실행 계획이란 무엇인가요?
    
82. EXPLAIN은 어떤 상황에서 사용하나요?
    
83. EXPLAIN ANALYZE와 EXPLAIN의 차이는 무엇인가요?
    
84. Sequential Scan과 Index Scan의 차이는 무엇인가요?
    
85. Index가 있는데도 Sequential Scan이 선택될 수 있는 이유는 무엇인가요?
    
86. Query 성능이 느릴 때 어떤 순서로 분석하겠나요?
    
87. N+1 Query 문제는 DB 관점에서 어떤 문제를 만드나요?
    
88. Pagination에서 OFFSET이 커질수록 느려지는 이유는 무엇인가요?
    
89. Cursor 기반 Pagination은 Offset 방식의 어떤 문제를 줄이나요?
    
90. 대량 데이터를 조회할 때 한 번에 모두 가져오면 어떤 문제가 생기나요?
    
## PostgreSQL 특화

91. PostgreSQL의 특징은 무엇인가요?
    
92. PostgreSQL과 MySQL의 차이를 아는 대로 설명해보세요.
    
93. PostgreSQL에서 Schema는 어떤 의미인가요?
    
94. PostgreSQL의 SERIAL과 IDENTITY의 차이는 무엇인가요?
    
95. PostgreSQL에서 TEXT와 VARCHAR는 어떤 차이가 있나요?
    
96. PostgreSQL에서 TIMESTAMP와 TIMESTAMPTZ의 차이는 무엇인가요?
    
97. PostgreSQL에서 JSON/JSONB 타입은 언제 사용하나요?
    
98. JSON과 JSONB의 차이는 무엇인가요?
    
99. PostgreSQL의 MVCC는 어떤 문제를 해결하기 위한 구조인가요?
    
100. PostgreSQL에서 Vacuum은 왜 필요한가요?
    
## PostgreSQL 인덱스 / 성능

101. PostgreSQL에서 GIN Index는 언제 사용하나요?
    
102. PostgreSQL에서 GiST Index는 어떤 상황에서 사용하나요?
    
103. JSONB 컬럼 검색 성능을 개선하려면 어떤 인덱스를 고려할 수 있나요?
    
104. 부분 인덱스, Partial Index는 어떤 상황에서 유용한가요?
    
105. Expression Index는 어떤 경우에 사용하나요?
    
106. LOWER(email) 검색을 빠르게 하려면 어떤 인덱스를 만들 수 있나요?
    
107. PostgreSQL에서 통계 정보가 쿼리 플랜에 영향을 주는 이유는 무엇인가요?
    
108. ANALYZE는 어떤 역할을 하나요?
    
109. VACUUM과 ANALYZE의 차이는 무엇인가요?
    
110. Index Scan보다 Seq Scan이 더 빠른 경우는 언제인가요?
    
## PostgreSQL 트랜잭션 / MVCC

111. PostgreSQL의 MVCC는 읽기와 쓰기 충돌을 어떻게 줄이나요?
    
112. MVCC 때문에 dead tuple이 생긴다는 말은 무슨 뜻인가요?
    
113. Dead tuple이 많아지면 어떤 문제가 생기나요?
    
114. Autovacuum은 어떤 역할을 하나요?
    
115. Autovacuum이 제대로 동작하지 않으면 어떤 증상이 나타날 수 있나요?
    
116. PostgreSQL의 기본 Isolation Level은 무엇인가요?
    
117. PostgreSQL에서 Repeatable Read는 어떤 특성을 가지나요?
    
118. PostgreSQL에서 장기 트랜잭션이 Vacuum에 악영향을 줄 수 있는 이유는 무엇인가요?
    
119. idle in transaction 상태가 위험한 이유는 무엇인가요?
    
120. Lock 대기가 발생했을 때 어떤 현상이 나타날 수 있나요?
    
## PostgreSQL 운영 / 백업

121. PostgreSQL에서 pg_dump는 어떤 용도로 사용하나요?
    
122. 논리 백업과 물리 백업의 차이는 무엇인가요?
    
123. WAL은 무엇인가요?
    
124. WAL이 장애 복구에 중요한 이유는 무엇인가요?
    
125. Replication은 왜 사용하나요?
    
126. Read Replica를 사용하면 어떤 장점이 있나요?
    
127. Read Replica를 사용할 때 replication lag이 문제가 되는 경우는 언제인가요?
    
128. Connection Pooler가 필요한 이유는 무엇인가요?
    
129. PgBouncer는 어떤 역할을 하나요?
    
130. PostgreSQL에서 너무 많은 커넥션이 문제가 되는 이유는 무엇인가요?

---

## 면접 우선순위(추천)

```text
1) SQL 기본: JOIN, GROUP BY, WHERE/HAVING, NULL
2) 트랜잭션: ACID, Isolation Level, Lock
3) 인덱스: B-Tree, 복합 인덱스, 실행 계획
4) 성능 분석: EXPLAIN, Seq Scan, Index Scan, Pagination
5) PostgreSQL 특화: MVCC, Vacuum, JSONB, TIMESTAMPTZ
6) 운영: Connection Pool, Backup, Replication, WAL
```

