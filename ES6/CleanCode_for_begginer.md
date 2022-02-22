# 초심자를 위한 지금 바로 써먹을 수 있는 JavaScript 클린코드 팁

## if-else문 관련

### 조건문이 길어질 때

조건문 자체를 정수에 넣어 보기 쉽게합니다.

```jsx
// bad
if (
  superLoooooooooongCondition1231231231231231231231241 ===
  veryVeryLoooooooooooooooongConditionYeahhhhhhhhhhhh
) {
  console.log("it's too long");
}

// good
const isLong =
  superLoooooooooongCondition1231231231231231231231241 ===
  veryVeryLoooooooooooooooongConditionYeahhhhhhhhhhhh;

if (isLong) {
  console.log("much better");
}
```

### if문 자체가 너무 많을 때, 이중, 삼중 if문을 쓰고 있을 때

불필요한 if문을 사용하고 있지 않은지 로직을 재점검합니다.
간단한 실행문이라면 논리연산자를 활용합니다.

```jsx
if (foo) {
  doSomething();
}

foo && doSomething();
```

### else문이 많아질 때

불필요한 if문을 사용하고 있지 않은지 로직을 재점검합니다.
삼항연산자를 이용합니다.

## forEach, find, some, map 등 내장함수 200% 활용하기

```jsx
// this is same as
array.map((item) => addNumber(item));

// this!
array.map(addNumber);
```

## return 트릭

```jsx
const isFish = pet as Fish
const isBird = pet as Bird

// 둘 중 하나라도 true라면 true, 둘 다 false라면 false
const isTrue = () => {
    return isFish || isBird
}

```

## 변수 관련

정확한 이름을 사용합니다. 발음할 수 있고, 누가봐도 무엇을 뜻하는지 알 수 있는 이름이어야합니다.

```jsx
const asdf; // X
const hey; // x
const users; // O
```

```jsx
export const foo;
export const bar;
export const zoo;

export const foo,bar,zoo
```

2개 이상의 변수를 넣지 않습니다.
두 개 이상이 되는경우, 변수를 합치거나, 함수를 나눕니다.

```jsx
// bad
const tooMuchParams = (foo, bar, zoo, hoge) => {
  console.log(foo, bar, zoo, hoge);
};

// good
const options = { foo, bar, zoo, hoge };
const oneParams = ({ options }) => {
  console.log({ options });
};
```

```jsx
// bad
const a = foo[0];
const b = foo[1];

// good
const [a, b] = foo;
```
