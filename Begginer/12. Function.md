# Function

- 특정 기능을 처리하는 코드의 집합
- 함수명은 동사로 시작하는 것이 좋다
- 함수의 기능을 한눈에 파악할 수 있도록 의미(semantic)있게 작성
- 결과값이 없을 경우 `undefined`를 반환한다.

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
