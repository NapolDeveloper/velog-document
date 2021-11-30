### 객체 생성하기

객체는 `{ }` 문자 안에 원하는 값을 넣어 생성할 수 있습니다. 객체를 이용하면 하나의 객체에 여러 데이터 타입의 값을 넣을 수 있습니다.
아래 코드를 보면 car라는 객체의 name과 speed의 값을 지정해준 후 `console` 함수를 통해 출력해주는 모습을 볼 수 있습니다.

```javascript
const car = {
  name: 'bmw i8',
  speed: 10
};
console.log(car.name); // bmw i8
console.log(car.speed); // 10
```

객체의 값은 아래와 같은 형식으로 추가할 수 있습니다.

```javascript
key: value;
```

<br>

### 함수에서 객체를 파라미터로 받기

객체를 함수의 인자값으로 넘겨주어 사용할 수 있습니다. 아래 코드에서는 `printChampion` 함수를 통하여 미리 정의해둔 `leesin` 객체와 `nidalee` 객체의 값을 참조하여 출력하도록 작성하였습니다.

```javascript
const leesin = {
  name: '리신',
  type: 'AD',
  position: 'Jungle'
};
const nidalee = {
  name: '니달리',
  type: 'AP',
  position: 'Jungle'
};

function printChampion(champ) {
  const text = `${champ.name}는 ${champ.type}이며 ${champ.position} 포지션의 챔피언입니다 `;
  console.log(text);
}
printChampion(leesin);
printChampion(nidalee);
```

> 위 `printChampion` 에 사용된 문법은 아래 링크를 통해 자세히 알아보실 수 있습니다.
> https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Template_literals

<br>

### 객체 비구조화 할당 (Destructuring Assignment)

위 `printChampion` 함수를 보면 객체의 값에 접근할 때 `champ.` 를 입력하고 있습니다. 하지만 객체 비구조화 할당 문법을 이용하면 더욱 가독성이 좋은 코드로 변경할 수 있습니다.

```javascript
const leesin = {
  name: '리신',
  type: 'AD',
  position: 'Jungle'
};
const nidalee = {
  name: '니달리',
  type: 'AP',
  position: 'Jungle'
};

function printChampion(champ) {
  const { name, type, position } = champ;
  const text = `${name}는 ${type}이며 ${position} 포지션의 챔피언입니다 `;
  console.log(text);
}
printChampion(leesin);
printChampion(nidalee);
```

우리는 아래 코드를 통해 객체에서 값을 추출하여 새로운 상수로 선언해 줄 수 있습니다. 또한 이 문법은 `React` 에서 자주 사용하니 꼭 숙지하고 있어야 하는 문법입니다.

```javascript
const { name, type, position } = champ;
```

또한 아래 코드와 같이 함수를 선언하는 과정에서 파라미터에서 비구조화 할당을 할 수 있습니다.

```javascript
const leesin = {
  name: '리신',
  type: 'AD',
  position: 'Jungle'
};
const nidalee = {
  name: '니달리',
  type: 'AP',
  position: 'Jungle'
};

function printChampion({ name, type, position }) {
  const text = `${name}는 ${type}이며 ${position} 포지션의 챔피언입니다 `;
  console.log(text);
}
printChampion(leesin);
printChampion(nidalee);
```

<br>

### 객체 내부에 함수 선언

```javascript
const kindred = {
  name: '킨드레드',
  type: 'AD',
  position: 'Jungle',
  motion: '킨드레드가 춤을 춥니다',
  jump: function jump() {
    console.log('킨드레드가 벽을 넘었습니다');
  },
  dance: function dance() {
    console.log(`${this.motion}`);
  }
};
kindred.jump();
kindred.dance();
```

결과값이 아래와 같이 출력될 것입니다.

```
킨드레드가 벽을 넘었습니다
킨드레드가 춤을 춥니다
```

함수가 객체 내에 선언된다면 `this` 는 자신이 속해있는 객체를 가리키게 됩니다. 그래서 `this` 를 이용하여 `kindred` 의 선언되어있는 `jump` 와 `dance` 함수에 접근할 수 있게 되는 것입니다.

> 해당 글은 velopert님의 gitbook을 참고하여 작성되었습니다. 항상 좋은 강의 감사드립니다!
> https://learnjs.vlpt.us/basics/06-object.html
