# Exception

- 예외는 실행 중에 발생할 수 있는 오류를 말한다.
- 에외 처리는 예외가 발생할 때 프로그램이 중단되는 것을 방지하기 위해 예외가 발생했을 때 프로그램의 실행 흐름을 변경하는 것을 말한다.

## try ~ catch

```js
try {
  // code
} catch (error) {
  // error handling
}
```

- try 블록 안에는 예외가 발생할 수 있는 코드를 작성한다.
- 예외가 발생하면 try 블록의 코드의 실행을 중단하고 catch 블록으로 제어가 이동한다.

## throw

```js
try {
  throw new Error("Error Message");
} catch (error) {
  console.log(error.message);
}
```

- `throw` 키워드를 사용하면 예외를 강제로 발생시킬 수 있다.
