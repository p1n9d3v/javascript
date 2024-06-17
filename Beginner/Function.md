# Function

- 특정 기능을 처리하는 코드의 집합
- 함수명은 동사로 시작하는 것이 좋다
- 함수의 기능을 한눈에 파악할 수 있도록 의미(semantic)있게 작성
- 결과값이 없을 경우 `undefined`를 반환한다.
- Javascript는 함수도 객체이다.

## function

```js
function 함수명(매개변수) {
  // 코드
  return 결과값;
}

함수명(); // call function
```

## arrow function

```js
const 함수명 = (매개변수) => {
  // 코드
  return 결과값;
};

함수명(); // call function
```

# Function 오브젝트 생성 과정

```js
function sports() {}
```

```js
// engine
sports = {
	arguments: {},
	caller: {},
	length: 0,
	name: 'sports',
	prototype: {
		constructor: sports
		__proto__: Object.prototype
	},
	__proto__: Function.prototype
}
```

- 빈 객체를 생성
- `arguments`, `caller`, `length`, `name`, `prototype`을 설정
- `__proto__`에 Function.prototype을 설정

# 함수 실행 환경

- `function` 키워드를 만나 오브젝트를 생성할 때 실행 환경이 설정된다
- 환경은 생성한 function 오브젝트에 설정된다.

| 내부 프로퍼티 (내부 슬롯/메서드) | 설명                                                                                                    |
| -------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `[[Prototype]]`                  | 객체의 프로토타입을 가리킵니다. 다른 객체로부터 상속된 속성과 메서드를 포함합니다.                      |
| `[[Class]]`                      | 객체의 타입을 나타내는 문자열입니다. 예: `"Object"`, `"Array"`, `"Function"`, `"Date"` 등.              |
| `[[Extensible]]`                 | 객체가 확장 가능한지 여부를 나타냅니다. `true`면 속성을 추가할 수 있고, `false`면 불가능합니다.         |
| `[[Get]]`                        | 객체의 특정 속성 값을 가져오는 내부 메서드입니다.                                                       |
| `[[Set]]`                        | 객체의 특정 속성 값을 설정하는 내부 메서드입니다.                                                       |
| `[[Call]]`                       | 함수 객체가 호출될 때 실행되는 내부 메서드입니다.                                                       |
| `[[Construct]]`                  | 함수 객체가 `new` 연산자와 함께 호출될 때 실행되는 내부 메서드로, 새로운 객체를 초기화합니다.           |
| `[[HasProperty]]`                | 객체에 특정 속성이 존재하는지 확인하는 내부 메서드입니다.                                               |
| `[[Delete]]`                     | 객체에서 특정 속성을 삭제하는 내부 메서드입니다.                                                        |
| `[[DefineOwnProperty]]`          | 객체에 새로운 속성을 정의하거나 기존 속성을 변경하는 내부 메서드입니다.                                 |
| `[[OwnPropertyKeys]]`            | 객체 자신의 속성 키들을 반환하는 내부 메서드입니다.                                                     |
| `[[Enumerate]]`                  | 객체의 열거 가능한 속성들을 반환하는 내부 메서드입니다.                                                 |
| `[[PreventExtensions]]`          | 객체의 확장을 방지하는 내부 메서드입니다.                                                               |
| `[[IsExtensible]]`               | 객체가 확장 가능한지 여부를 확인하는 내부 메서드입니다.                                                 |
| `[[GetOwnProperty]]`             | 객체 자신의 특정 속성에 대한 속성 설명자를 반환하는 내부 메서드입니다.                                  |
| `[[DefineProperty]]`             | 객체에 속성을 정의하는 내부 메서드입니다.                                                               |
| `[[HasOwnProperty]]`             | 객체 자신의 특정 속성이 존재하는지 확인하는 내부 메서드입니다.                                          |
| `[[SetPrototypeOf]]`             | 객체의 프로토타입을 설정하는 내부 메서드입니다.                                                         |
| `[[GetPrototypeOf]]`             | 객체의 프로토타입을 가져오는 내부 메서드입니다.                                                         |
| `[[Scope]]`                      | 함수 객체가 생성된 렉시컬 환경을 가리킵니다. 함수가 선언된 스코프 체인 정보를 포함합니다.               |
| `[[Environment]]`                | 함수 객체가 생성된 렉시컬 환경을 나타냅니다. 클로저와 관련된 환경 정보를 포함합니다.                    |
| `[[HomeObject]]`                 | ES6에서 메서드의 `super` 키워드 사용을 위해, 메서드가 정의된 객체를 가리킵니다.                         |
| `[[BoundTargetFunction]]`        | `Function.prototype.bind` 메서드에 의해 생성된 바운드 함수 객체가 참조하는 원본 함수 객체를 나타냅니다. |
| `[[BoundThis]]`                  | 바운드 함수가 호출될 때 사용되는 `this` 값을 나타냅니다.                                                |
| `[[BoundArguments]]`             | 바운드 함수가 호출될 때 사용할 초기 인수들의 리스트를 나타냅니다.                                       |
| `[[PrimitiveValue]]`             | 래퍼 객체 (예: `new Number(5)`)가 래핑하는 원시 값입니다.                                               |
| `[[PromiseState]]`               | 프로미스 객체의 현재 상태를 나타냅니다 (`pending`, `fulfilled`, `rejected`).                            |
| `[[PromiseResult]]`              | 프로미스 객체가 `fulfilled` 또는 `rejected` 상태일 때 그 결과 값입니다.                                 |
| `[[PromiseFulfillReactions]]`    | 프로미스가 성공적으로 이행될 때 실행될 리액션 핸들러들의 리스트입니다.                                  |
| `[[PromiseRejectReactions]]`     | 프로미스가 거부될 때 실행될 리액션 핸들러들의 리스트입니다.                                             |
| `[[PromiseIsHandled]]`           | 프로미스가 이미 처리되었는지 여부를 나타냅니다.                                                         |
| `[[WeakMapData]]`                | `WeakMap` 객체의 내부 데이터 구조입니다.                                                                |
| `[[WeakSetData]]`                | `WeakSet` 객체의 내부 데이터 구조입니다.                                                                |
| `[[MapData]]`                    | `Map` 객체의 내부 데이터 구조입니다.                                                                    |
| `[[SetData]]`                    | `Set` 객체의 내부 데이터 구조입니다.                                                                    |
| `[[ArrayBufferData]]`            | `ArrayBuffer` 객체의 내부 데이터입니다.                                                                 |
| `[[ArrayBufferByteLength]]`      | `ArrayBuffer` 객체의 바이트 길이입니다.                                                                 |
| `[[ViewedArrayBuffer]]`          | `TypedArray` 객체가 참조하는 `ArrayBuffer` 객체입니다.                                                  |
| `[[TypedArrayByteOffset]]`       | `TypedArray` 객체의 바이트 오프셋입니다.                                                                |
| `[[TypedArrayByteLength]]`       | `TypedArray` 객체의 바이트 길이입니다.                                                                  |
| `[[TypedArrayLength]]`           | `TypedArray` 객체의 길이입니다.                                                                         |

# 함수 코드 해석

1. 함수 선언문을 해석
2. 선언된 변수를 undefined로 초기화
3. 처음부터 코드를 실행

### 호이스팅

- 변수 및 함수 선언을 해석 단계에서 메모리에 저장
- 선언된 변수 및 함수 선언되기 전의 코드에서 호출 가능

# Arguments Object

- 함수 인자를 저장하는 객체

```js
{ 0 : '인자1', 1 : '인자2', 2 : '인자3', length : 3 }
```
