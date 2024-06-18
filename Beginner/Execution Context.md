# Execution Context

- 실행 컨텍스트는 코드가 실행되는 환경을 의미한다.
- 자바스크립트 엔진이 코드 실행을 위해 필요한 정보를 수집하고 유지하기 위해 사용된다.

## Global Execution Context

- 코드가 처음 실행될 때 생성
- 전역 객체 생성, `this`를 전역 객체에 바인딩
- 모든 전역 변수와 함수는 전역 객체에 저장

## Function Execution Context

- 함수가 호출될 때 생성
- 함수 내부의 변수, 매개변수, 선언된 함수 등에 대한 정보를 포

### Lexical Environment

- Lexical Environment는 실행 컨텍스트 생성 시 초기화
- 함수가 정의될 때의 스코프를 기반 하여, 클로저와 관련된 변수 접근을 관리

## Variable Environment

- 함수가 호출될 떄 생성
- 함수가 실행될 떄 변수의 값이 저장되는 환경
- 일반적으로 Lexiclal Environment와 동일한 객체를 참조

## Environment Record

- DeclarativeEnvironmentRecord: 함수의 인수, 변수, 함수 선언 등을 저장
- ObjectEnvironmentRecord: 전역 객체(예: 브라우저 환경에서는 window 객체)의 속성을 저장

## outer

- 현재 실행 컨텍스트의 부모 Lexical Environment를 가르킴
- 스코프 체인을 형성하여 외부 Lexical Environment에 접근 가능

## thisBinding

- 현재 실행 컨텍스트에서 this 키워드가 참조하는 객체를 가르킴
- 글로벌 컨텍스트에서는 전역 객체(window)
- 함수 컨텍스트에서는 호출 방법에 따라 달라질 수 있음

## Example

```javascript
var a = 10;

function foo() {
  var b = 20;
  function bar() {
    var c = 30;
    console.log(a + b + c);
  }
  bar();
}

foo();
```

```javascript
GlobalExecutionContext = {
	LexicalEnvironment: {
		EnvironmentRecord: {
			DeclarativeEnvironmentRecord: {
				a: 10,
				foo: <function>
			},
			ObjectEnvironmentRecord: {
				// 전역 객체의 속성들(전역 변수, 전역 함수 등)이 저장
			}
		},
		outer: null
	},
	VariableEnvironment: {
		EnvironmentRecord: {
			DeclarativeEnvironmentRecord: {
				a: 10,
				foo: <function>
			},
			ObjectEnvironmentRecord: {}
		},
		outer: null
	},
	thisBinding: <Global Object>
}

FooExecutionContext = {
    LexicalEnvironment: {
        EnvironmentRecord: {
            DeclarativeEnvironmentRecord: {
                b: 20,
                bar: <function>
            }
        },
        outer: GlobalExecutionContext.LexicalEnvironment
    },
    VariableEnvironment: {
        EnvironmentRecord: {
            DeclarativeEnvironmentRecord: {
                b: 20,
                bar: <function>
            }
        },
        outer: GlobalExecutionContext.VariableEnvironment
    },
    thisBinding: globalObject
}

BarExecutionContext = {
    LexicalEnvironment: {
        EnvironmentRecord: {
            DeclarativeEnvironmentRecord: {
                c: 30
            }
        },
        outer: FooExecutionContext.LexicalEnvironment
    },
    VariableEnvironment: {
        EnvironmentRecord: {
            DeclarativeEnvironmentRecord: {
                c: 30
            }
        },
        outer: FooExecutionContext.VariableEnvironment
    },
    thisBinding: globalObject
}
```
