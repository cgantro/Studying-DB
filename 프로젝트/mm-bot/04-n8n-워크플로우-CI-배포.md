# mm-bot - n8n 워크플로우 CI 배포

## 문제
- 워크플로우 JSON을 여러 파일로 관리하면 병합 과정에서 충돌/깨짐이 자주 발생한다.

## 해결
- CI에서 ask + summary(+ optional overlay) 워크플로우를 병합한 뒤,
  - 노드 name/id 중복 검증
  - connections의 source/target 유효성 검증
  - (UI 편의) summary/overlay 노드들의 y 좌표를 offset해서 겹침을 피함
- 검증 통과 후 n8n API로 workflow를 PUT 업데이트한다.

## 대안
- 워크플로우를 한 파일로만 유지:
  - 장점: 병합이 단순
  - 단점: 기능 모듈화/옵션화(overlay) 확장이 어려움

