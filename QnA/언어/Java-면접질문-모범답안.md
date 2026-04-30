# Java 면접질문-모범답안

## 면접 질문
- Java 17과 Java 21의 실무 차이는?
- virtual thread를 언제 도입하나요?
- GC 튜닝은 어디서부터 시작하나요?

## 모범 답안
<details>
  <summary>Java 17과 Java 21의 실무 차이는?</summary>

- 결론: 17은 안정적인 LTS 기반, 21은 동시성/표현력 측면 개선이 커서 점진 도입 가치가 큽니다.
- 근거: 21의 virtual thread, pattern matching 강화는 서버 코드 유지보수성과 처리량 개선에 직접적입니다.
- 트레이드오프: 신규 기능 도입 시 라이브러리 호환성과 운영 지표 재검증 비용이 듭니다.

</details>

<details>
  <summary>virtual thread를 언제 도입하나요?</summary>

- 결론: I/O 대기가 많은 요청 처리 경로에서 우선 검토합니다.
- 근거: blocking 비용을 줄여 동시 처리량을 높일 수 있습니다.
- 트레이드오프: CPU-bound 작업은 이점이 제한적이며, 기존 모니터링/스레드 모델과의 정합성을 점검해야 합니다.

</details>

<details>
  <summary>GC 튜닝은 어디서부터 시작하나요?</summary>

- 결론: 힙 증설보다 먼저 할당 패턴과 GC pause 지표를 봅니다.
- 근거: 객체 생명주기/할당률이 문제 원인인 경우가 많습니다.
- 트레이드오프: 공격적 튜닝은 특정 워크로드 최적화로 일반 상황 안정성을 해칠 수 있습니다.

</details>
