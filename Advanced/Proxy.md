# Proxy

- 중간에 대리 역할
- `person.name` 을 호출하면 `[[Get]]`(getter)를 이용하여 값을 가져옴, setter도 동
  - `person`의 `__proto__`에 `[[Get]]`, `[[Set]]`을 이용하여 값을 가져오거나 설정

## Trap

- OS에서 실행 중인 프로그램에 이상이 발생했을 때, 이를 감지하고 처리하는 기법
-
