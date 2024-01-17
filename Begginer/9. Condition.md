# Condition

- 조건에 따라 코드를 실행할 수 있는 문법

## if

```js
if (조건식) {
  // 조건식이 참일 경우 실행
} else if (조건식) {
  // else if는 조건식을 여러개 사용할 수 있음
  // 조건식이 참일 경우 실행
} else {
  // 조건식이 거짓일 경우 실행
}
```

## switch

```js
switch (변수) {
  case 값:
    // 변수의 값이 값과 같을 경우 실행
    break;
  case 값:
    // 변수의 값이 값과 같을 경우 실행
    break;
  default:
    // 변수의 값이 case에 없을 경우 실행
    break;
}
```

- `break`를 사용하지 않으면 다음 case까지 실행됨
