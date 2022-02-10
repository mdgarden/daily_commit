# Strings

## 문자열 다루기 기초

expression

```jsx
// bad
const sayHi = (name = "madang") => "hello" + name;

// good
const sayHi = (name = "madang") => `hello ${name}`;
```

함수는 넣을 수 없지만 이렇게 하는 방법은 있음

```jsx
const add = (a, b) => a + b;

console.log(`hello how are you ${add(6, 6)}`);

// 함수만 쓰게 되면
console.log(`hello how are you ${add}`);
// hello how are you (a, b) => a + b
```
