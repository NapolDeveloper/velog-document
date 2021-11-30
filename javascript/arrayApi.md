### 배열 내장 함수

이번 포스트에서는 자주 사용하는 6개의 배열 내장 함수에 대해 공부할 것입니다. 먼저 배열 내장 함수를 공부하기 전 `callback` 함수에 대해서 알아보겠습니다. `callback` 함수는 중요한 개념이니 꼭 숙지하고 계셔야 합니다.
<br>

### 콜백함수 (Callback Function)

콜백함수는 파라미터로 함수를 전달받아서 함수 내부에서 실행되는 함수입니다.

```javascript
const champion = ['리신', '카직스', '니달리', '킨드레드'];
champion.forEach((champ) => {
  console.log(champ);
});
```

위 코드에서는 `forEach` 함수에서 익명의 함수를 넣어서 동작시킵니다.

```javascript
const champion = ['리신', '카직스', '니달리', '킨드레드'];
champion.forEach(function (champ) {
  console.log(champ);
});
```

위 코드는 화살표 함수(Arrow Function)에서 일반 함수로 변경한 코드입니다. 콜백함수는 **함수 내부에서 실행되기 때문에 함수명이 필요하지 않기 때문에 익명**으로 사용합니다.
<br>

### foreach

`forEach` 는 for문을 대체할 수 있는 함수 중 하나의 함수입니다. 우리는 평소 `for` 문과 배열의 길이를 구하는 `length` 를 이용하여 코드를 작성했습니다.

```javascript
const champion = ['리신', '카직스', '니달리', '킨드레드'];
for (let i = 0; i < champion.length; i++) {
  console.log(champion[i]);
}
```

`forEach` 를 이용하면 아래와 같이 `callback` 함수를 넘겨주어 이용할 수 있습니다. 여기서 `champ` 는 `champion` 배열의 각 원소를 가리키게 됩니다.

```javascript
const champion = ['리신', '카직스', '니달리', '킨드레드'];
champion.forEach((champ) => {
  console.log(champ);
});
```

<br>

### map

`map` 함수는 직접 지정한 조건에 의해 배열의 원소를 변환시켜줍니다. 이 과정에서 **기존 배열은 변경되지 않습니다.**

```javascript
const numArray = [10, 20, 30, 40, 50];
const newArray = numArray.map((n) => n * 2);
console.log(newArray);
```

아래와 같이 결과가 출력이 될 것입니다.

```
[20, 40, 60, 80, 100]
```

`map` 함수의 파라미터로는 변화시킬 로직이 들어있는 함수를 전달해줍니다. 위와같이 함수를 선언하지 않고 로직만 넣어도 작동합니다.
<br>

### filter

`filter` 함수는 특정 조건에 맞는 원소만 추출하여 새로운 배열을 만듭니다.
`todos` 객체의 `done`의 값이 false인 객체만을 추출하여 새로운 배열을 만들고 해당 배열의 길이를 구하는 코드입니다.

```javascript
const todos = [
  {
    id: 1,
    done: true
  },
  {
    id: 2,
    done: false
  },
  {
    id: 3,
    done: false
  },
  {
    id: 4,
    done: false
  }
];
const notDone = todos.filter((todo) => todo.done === false);
console.log(`해야할 일이 ${notDone.length}개 남았습니다`);
```

위 코드의 조건문은 아래의 코드와 동일하게 작동합니다.

```javascript
const notDone = todos.filter((todo) => !todo.done);
```

<br>

### splice

`splice` 는 배열의 원소를 지우기 위해 사용합니다. `splice` 의 파라미터로 첫 번째 파라미터에는 제거를 시작할 배열의 인덱스, 두 번째 파라미터에는 첫 번째 파라미터부터 지울 개수를 의미합니다.

```javascript
const fruits = ['🍎', '🍑', '🍓', '🍏'];
fruits.splice(1, 1);
console.log(fruits); // 복숭아가 제거된 배열 출력
```

<br>

### slice

`slice` 는 **기존의 배열을 건드리지 않습니다.**

```javascript
const fruits = ['🍎', '🍑', '🍓', '🍏'];
const sliceFruits = fruits.slice(0, 2);
console.log(sliceFruits);
```

첫 번째 파라미터에는 제거를 시작할 배열의 인덱스, 두 번째 파라미터에는 첫 번째 파라미터부터 자를 개수를 의미합니다.

```typescript
slice(start?: number, end?: number)
```

<br>

### concat

`concat` 함수는 여러개의 배열을 합치는 함수입니다. 중요한 점은 기존의 배열은 변경되지 않습니다. (array1, array2 배열의 값은 그대로 존재)

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const concatArray = array1.concat(array2);
console.log(concatArray);
```

`concatArray` 를 출력했을 때 아래와 같은 결과값이 나올 것입니다.

```
[1, 2, 3, 4, 5, 6]
```

> 해당 글은 velopert님의 gitbook을 참고하여 작성되었습니다. 항상 좋은 강의 감사드립니다!
> https://learnjs.vlpt.us/basics/06-object.html
