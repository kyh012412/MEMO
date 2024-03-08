# 자바스크립트 Readme.md

## var와 let의 차이

### var의 특징

- var는 함수 스코프를 가진다.
- 변수의 중복 선언을 허용한다. (값의 덮어쓰기)
- var를 사용하면 window객체에 등록이된다. (window.(변수명)으로 접근가능)

```js
// javascript코드
function main() {
  if (true) {
    var x = 10;
  }
  console.log(x); //x는 main함수 내부 전체에서 접근이 가능하다.
}
```

---

### let의 특징

- let은 블록 스코프를 가진다.
- let은 중복 선언을 허용하지 않는다.

```js
// javascript코드
function main() {
  if (true) {
    let x = 10;
  }
  console.log(x); //x는 if block을 나온 상태이므로 올바른 접근을 할 수 없다.
}
```

---

## 호이스팅

### var의 경우 호이스팅

```js
// javascript코드
console.log(num);

var num = 10;

console.log(num);
//위 코드는 에러가 발생하지 않는다.
```

호이스팅은 변수의 선언과 초기화를 분리해서
변수의 선언을 위에서 먼저 해주는것
호이스팅된 변수는 일단은 undefined라는 값을 가진다.

### let의 경우 호이스팅

```js
// javascript코드
console.log(num);
// 이 경우는 에러가 발생
// 이유는 TDZ (Temporal Dead Zone(일시적 사각지대)) 때문에
// 자바스크립트는 TDZ에 대한 접근을 허용하지 않는다.
let num = 10;

console.log(num);
```

## Const

- Block Scope
- 중복 선언 불가
- 선언문 이전 접근 불가
- 상수 선언 (변수x)

* Bad Case

```js
const a = {
  x: 1,
  y: 2,
};

a = {}; //이런식으로 수정하려고하면 에러가발생
```

- Good Case

```js
const a = {
  x: 1,
  y: 2,
};

a.x = 3; // 객체의 속성을 바꾸는 것은 가능
```

- 속성값 마저 변경하지 못하게 하려면 Object.freeze()사용

```js
const a = Object.freeze({
  x: 1,
  y: 2,
});

a.x = 3; // 객체의 속성을 바꾸는 것은 가능
```
