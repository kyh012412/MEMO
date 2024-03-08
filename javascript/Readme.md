# 자바스크립트 Readme.md

## var와 let의 차이

- var는 함수 스코프를 가진다.

```js
function main() {
  if (true) {
    var x = 10;
  }
  console.log(x); //x는 main함수 내부 전체에서 접근이 가능하다.
}
```

- let은 블록 스코프를 가진다.

```js
function main() {
  if (true) {
    let x = 10;
  }
  console.log(x); //x는 if block을 나온 상태이므로 올바른 접근을 할 수 없다.
}
```
