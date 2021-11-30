### 함수의 기본 파라미터

우리는 평소에 아래 코드와 같이 함수를 작성하고 사용했습니다.

```javascript
function add(x, y) {
  return x + y;
}
console.log(add(10, 20));
```

하지만 만약 함수에 인자값으로 아무것도 넘겨주지 않는다면 `javascript` 에서는 매개변수의 기본값을 `undefined` 로 설정하여 아래 코드에 경우에는 `add` 함수에서 `NaN` 이 반환되게 됩니다.

```javascript
function add(x, y) {
  return x + y;
}
console.log(add());
```

```
출력 : NaN
```

<br>

이러한 불편함을 개선하여 우리는 `ES6` 부터는 아래 두 가지 코드의 예제와 같이 파라미터에서 기본 값을 설정해 줄 수 있습니다.

#### 문자열을 기본값으로 설정하기

```javascript
function printMessage(message = 'default message') {
  console.log(message);
}
printMessage('hello'); // hello 인자값 출력
printMessage(); // default message 출력
```

#### 숫자를 기본값으로 설정하기

```javascript
function add(x = 1, y = 2) {
  return x + y;
}
console.log(add()); // 3출력
console.log(add(2, 5)); // 7출력
```

그리고 기본 파라미터 설정은 **화살표 함수**에서도 사용할 수 있습니다.

```javascript
const printMessage = (message = 'default message') => console.log(message);
const print = printMessage();
console.log(print);
```

> 해당 글은 velopert님의 gitbook을 참고하여 작성되었습니다. 항상 좋은 강의 감사드립니다!
> https://learnjs.vlpt.us/basics/06-object.html
> MDN
> https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Functions/Default_parameters
