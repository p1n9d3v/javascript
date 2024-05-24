# Variable

- 값을 저장하는 공간
- 값에 대한 재사용성 목적을 가지고 있다.
- `var <name> = <value>;`
- 변수명은 의미있는 값(Semantic)으로 작성하는 것이 좋다.

# var

- `var` 키워드는 함수 스코프를 가진다.
- 함수 내부에 변수를 선언하지 않고 사용하면 전역 변수로 선언된다.
- Lexical Environment 구조에서는 사용을 지양한다.
  - Lexical Environment는 오직 함수 내부, 외부 스코프를 기반으로 동작한다.

# let, const

- `let`, `const` 키워드는 블록 스코프를 가진다.
- `let`은 재할당이 가능하다.
- `const`는 재할당이 불가능하다.
