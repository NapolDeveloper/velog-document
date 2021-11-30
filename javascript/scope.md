### 스코프

Javascript에는 `scope` 라고 불리는 개념이 있습니다. `scope`는 우리가 변수 또는 함수를 선언하고 사용할 수 있는 유효 범위를 의미합니다.

#### Global Scope - 전역

전역 스코프는 함수 안에 포함되지 않은 곳에 정의하는 것으로 코드 어디에서든 참조할 수 있습니다.

```javascript
const value = 'hello!';

function myFunction() {
  console.log('myFunction; ');
  console.log(value);
}
```

#### Function-level Scope - 함수

아래 코드에서는 `otherFunction` 내에 `value` 변수를 선언해 주었습니다. 함수를 실행 시키면 `value` 에 접근하여 `console` 함수를 통해 출력해주지만 함수 바깥에서 실행시킨 `console` 함수에서는 `value`에 접근하지 못합니다.

```javascript
function otherFunction() {
  console.log('otherFunction: ');
  const value = 'bye!';
  console.log(value);
}
console.log(value); // value is not defined
```

#### Block-level Scope - 블록

블록 스코프는 `if`, `switch`와 같은 조건문, `for`, `while`과 같은 반복문에서 사용됩니다.
javascript es6부터 `let`, `const`를 이용하여 선언할 수 있습니다. `var`로 선언된 변수는 밖에서도 접근이 가능합니다.

```javascript
function foo() {
  if (true) {
    var a = 0;
    let b = 1;
    const c = 2;
  }
  console.log(a); // 0
  console.log(b); // b is not defined
  console.log(c); // c is not defined
}
```

> 해당 글은 velopert님의 gitbook을 참고하여 작성되었습니다. 항상 좋은 강의 감사드립니다!
> https://learnjs.vlpt.us/useful/08-scope.html
