# Object

- Object는 key-value의 집합체이다
- key는 유일한 값이다
  - 중복된 key가 존재하면 마지막 key-value만 남는다

```js
const book = {
  title: "Title",
  description: "Description",
};
console.log(book.title);
console.log(book["title"]);
console.log(typeof book); // object
```

## for in

- Object는 for in을 통해 property를 순회할 수 있다.
- ES3에서는 프로퍼티를 작성한 순서대로 순회하지 않았지만 ES5부터는 작성한 순서대로 순회한다

```js
const book = {
  title: "Title",
  description: "Description",
};

for (let key in book) {
  console.log(`${key} : ${book[key]}`);
}
```
