### 삼항연산자 (Ternary Operator)

삼항 연산자는 아래 코드와 같이 사용할 수 있습니다. `isCat` 의 값이 true일 경우 `😸`, false일 경우 `🐶` 를 component에 대입해줍니다.

```javascript
const component = isCat ? '😸' : '🐶';
```

문법은 아래와 같습니다.

```
조건 ? true일 경우 : false일 경우
```

우리는 이러한 삼항연산자를 객체에서도 사용할 수 있습니다.

```javascript
const napol = {
  name: 'napol',
  age: '21'
};

const { name, age } = napol;
console.log(age >= 30 ? `${name}는 30살 이상입니다` : `${name}는 30살 미만입니다`);
```

위 코드를 실행시키면 아래와 같이 출력될 것입니다.

```
napol는 30살 미만입니다
```

위 코드 중 아래 코드에 해당하는 문법은 `객체 비구조화 할당` 입니다. [JS - Object](https://velog.io/@napol/JS-Object)를 통해 확인하실 수 있습니다.

```javascript
const { name, age } = napol;
```

### 삼항연산자 중첩

삼항 연산자는 중첩해서 사용할 수 있습니다. 하지만 가독성이 좋지 않기 때문에 권장하는 방식은 아니라고 할 수 있습니다.

```javascript
const x = 10;
const y = 20;

const z = x > y ? 'x > y' : x < y ? 'x < y' : '같다';
console.log(z);
```
