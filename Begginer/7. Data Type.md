# Data Type

- JS는 값이 할당될 때 타입이 결정
- `typeof` 연산자로 타입 확인 가능

```js
const str = "Hello";
const num = 1;
const obj = {};

console.log(typeof str); // string
console.log(typeof num); // number
console.log(typeof obj); // object
console.log(typeof true); // boolean
console.log(typeof undefined); // undefined
```

# Primitive Type

데이터의 가장 기본적인 형태를 의미한다. 기본형(Primitive Type)은 값이 할당될 때 메모리 상에 고정된 크기로 저장되며, 해당 변수에 데이터를 저장한다.
Primitive Type에 해당하는 값은 메모리에 그대로 저장한다. 필요에 따라서 내부 엔진이 자동으로 객체로 변환해주기도 한다. 예를 들어 `"joon".toUpperCase()`의 코드를 실행할 때 내부적으로 `"joon"`이 `String` 객체로 변환되어 `toUpperCase()` 메서드를 사용할 수 있게 된다.

## Number Type

- 숫자를 의미하는 데이터 타입
- 3개의 특수한 값이 존재
  - `Infinity`: 양의 무한대
  - `-Infinity`: 음의 무한대
  - `NaN`: 숫자가 아님 (Not a Number)
    - `A / 0`과 같은 연산의 결과

## String Type

- 문자열을 의미하는 데이터 타입
- `const str = "Hello";`

## Undefined Type

- 값이 할당되지 않은 상태를 의미하는 데이터 타입
- `let undefinedValue;`와 같이 값을 할당하지 않으면 엔진에서 자동으로 `undefined`를 할당

## Null Type

- `undefined`와 마찬가지로 값이 할당되지 않은 상태를 의미하는 데이터 타입
- `null`은 프로그래머가 의도적으로 값이 없음을 표현할 때 사용
- `typeof`로 타입을 확인하면 `object`가 반환
  - `console.log(typeof null); // object`

## Boolean Type

- `true`와 `false` 두 가지 값을 가지는 데이터 타입

## Object Type

- `{<key>: <value>}`(Property) 형태로 이루어진 데이터 타입
- 0개 이상의 Property로 구성

## Symbol Type

- ES6에서 추가된 데이터 타입
- Symbol은 유일한 값을 나타내기 위해 사용
- 값이 유일(고유)하기 때문에 다른 값과 절대로 충돌(동일)하지 않는다.
- `let sym = Symbol('symbol');`

## BigInt Type

- ES2020에서 추가된 데이터 타입
- `Number` 타입으로 표현할 수 없는 정수를 표현할 때 사용
  - JS는 IEEE754 표준에 따라 64비트 부동소수점을 사용하기 때문에, 가수 영역인 52비트를 넘어가면 안전하게 표현할 수 없다.
- `2^53 - 1`보다 큰 정수를 안전하게 표현하기 위해 사용
- `let bigInt = 1234567890123456789012345678901234567890n;`(`n`을 마지막에 붙여준다.)
- `Number`와 `BigInt`는 서로 다른 타입이기 때문에 직접 비교, 연산은 불가능하여 연산을 수행하기 전 한 타입으로 통일해야 한다.
