# Loop

- 코드를 반복적으로 실행할 때 사용하는 구문

## while

```js
while (조건식) {
  // code
}
```

- `while` 구문은 조건식이 `true` 일 때 코드를 실행
- 조건식이 계속 `true` 이면 무한 반복을 하게 되므로 주의 필요

## do ~ while

```js
do {
  // code
} while (조건식);
```

- `do ~ while` 구문은 코드를 먼저 실행한 후 조건식을 검사

## for

```js
for (초기화식; 조건식; 증감식) {
  // code
}
```

- 초기화식은 최초 한 번만 실행
- 조건식이 `true` 일 때 코드를 실행
- 코드 실행 후 증감식을 실행

## break, continue

- `break` 구문은 반복문을 중단
- `continue` 구문은 반복문의 코드 실행을 건너뜀
