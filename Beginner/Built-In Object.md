# Built-In Object

## Primitive Value

- 언어에 있어 가장 기본이 되는 데이터
- object는 primitive value를 제공하지 않음
  - `Boolean` , `Date` , `Number` , `String` built-in object들은 primitive value를 제공함
  - `[[PrimitiveValue]]`라는 내부 슬롯에 저장되어 있음
  - `[[PrimitiveValue]]`는 engine이 만듬

```js
const num = 1;
const str = "string";

const obj = {
  name: "joon",
}; // no have primitive value

const numObj = new Number(1);
console.log(numObj);
console.log(numObj.valueOf());
```

## Number

- 숫자형 데이터를 다루는 Object
- [MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number)

## String

- 문자열 데이터를 다루는 Object
- [MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String)

## Object

- [MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object)

### ES3

- `new Object()`는 파라미터 데이터 타입의 인스턴스를 생성
  - `new`를 생략하여도 생성 가능하다
- `valueOf()`, `hasOwnProperty()`, `propertyIsEnumerable()`, `isPrototypeOf()`, `toString()`, `toLocaleString()`은 ES3에서 6개 함수가 인스턴스(prototype)에 포함된다.

### prototype

- 빌트인 오브젝트는 `prototype`에 인스턴스를 생성할 때 사용하는 메소드를 포함한다.
- `prototype`은 인스턴스의 `__proto__` 에 연결된다.
- 인스턴스 `prototype`을 통해 연결된 메소드를 호출할 때는 `__proto__`를 생략하여 호출할 수 있다.

### 함수 , 메소드

`prototype`에 포함되면 메소드라고 불린다.

- 함수 : `Object.create()`
- 메소드 : `Object.prototype.toString()`

## Function

- Function도 Object이다.

```js
var obj = new Function("book", "return book");
obj("js"); // js

vsr add = new Functino('one','two', 'return one + two')
add(1,3) // 4
```

### call

- apply와 다르게 인자를 직접적으로 받는다.

```js
const obj = { one: 10, two: 20 };
function getTotal() {
  return this.one + this.two;
}

function getTotal2(one, two) {
  return one + two;
}

console.log(getTotal.call(obj));
console.log(getTotal2.call(null, 10, 20));
```

### apply

- apply는 배열을 인자로 받는다.

```js
function getTotal(one, two) {
  return one + two;
}

getTotal.apply(null, [10, 20]);
```

### arguments

- 함수 인자를 `arguments`로 접근할 수 있다.

```js
function getTotal(basis) {
  return basis + arguments[1] + arguments[2];
}

getTotal(10, 20, 30);
```

# Global(Window)

- 모든 코드에서 공유 가능한 오브젝트
- `new` 연산자로 인스턴스를 생성할 수 없다.

## Global Object vs Window Object

- Global Object의 개념은 js 엔진에서 사용하는 용어
- Window Object는 브라우저에서 사용하는 용어
- Window Object는 Global Object를 상속받는다.

# Array

- 배열을 다루는 Object
- Javascript는 배열도 Object이기 떄문에 `isArray()` 메소드로 배열을 확인할 수 있다.
- `forEach`는 `break`,`continue` 사용 불가(`throw` 가능)
  - `for`가 다른점은 모든 원소를 순회한다는 시멘틱을 가지고 있다.
- `every`, `some`, `map`, `filter` 등 다양한 메소드를 제공
- [MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array)

# Boolean

- true, false 값을 다루는 Object
