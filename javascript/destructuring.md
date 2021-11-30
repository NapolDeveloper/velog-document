## 비구조화 할당

함수의 파라미터에서 비구조화 할당을 할 수 있습니다. 또한 인자로 넘겨준 객체에서 특정 값이 주어지지 않았을 경우를 대비하여 기본값을 설정할 수 있습니다.

### 함수의 파라미터에서의 비구조화 할당

```javascript
const student = {
  name: 'napol',
  level: 1
};

function printStudent({ name, level }) {
  console.log(name);
  console.log(level);
}
printStudent(student);
```

### 기본값 설정

아래 코드는 위 코드와 다르게 `student` 객체에 `level` 이 선언되지 않았습니다. 하지만 비구조화 할당과 동시에 기본값을 **1**로 지정해 주었기 때문에 결과값은 위 코드와 동일하게 출력됩니다.

```javascript
const student = {
  name: 'napol'
};
function printStudent({ name, level = 1 }) {
  console.log(name);
  console.log(level);
}
printStudent(student);
```

### 배열에서의 이용방법

```javascript
const animals = ['🐶', '😸'];
const [first, second] = animals;
console.log(first, second);
```

배열에서도 비구조화 할당과 동시에 기본값을 설정 할 수 있습니다.

```javascript
const animals = ['🐶'];

const [first, second = '😸'] = animals;
console.log(first, second);
```

### 다른 이름으로 변경

때로는 비구조화 할당을 할 때 선언할 값의 이름은 변경해야 할 때가 있습니다. 이름의 변경은 `:` 변경할 수 있습니다.

```javascript
const student = {
  name: 'napol'
};
const { name: studentName, level: studentLevel = 2 } = student;
console.log(studentName);
console.log(studentLevel);
```

위 코드에서는 객체 비구조화 할당과 동시에 이름을 변경해 주었고 `studentLevel`의 기본값으로 `2` 를 지정해 주었습니다.

> 해당 글은 velopert님의 gitbook을 참고하여 작성되었습니다. 항상 좋은 강의 감사드립니다!
> https://learnjs.vlpt.us/basics/06-object.html
> MDN
> https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
