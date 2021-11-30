### Spread

`spread` 문법은 객체 또는 배열과 같은 곳에서 사용할 수 있습니다. `spread` 연산은 요소를 개별적으로 전개해줍니다.

#### 배열

```javascript
const array = [1, 2, 3];
console.log(array);
console.log(...array);
```

위 코드의 실행값은 아래와 같습니다. 이 코드를 통해 `spread` 연산을 통해 배열의 각 요소를 개별적으로 전개 한다는 내용을 배울 수 있습니다.

```
[1, 2, 3]
1 2 3
```

아래 코드는 배열의 합성 예시입니다.

```javascript
const arr1 = [1, 2];
const arr2 = [3, 4];

console.log(arr1.concat(arr2));
console.log([...arr1, ...arr2]);
```

위 코드에서는 두 가지 방법을 통해 배열의 합성을 진행했습니다. `concat` 함수를 이용하는 방법, 두 번째 방법은 `spread` 문법을 이용항 방법입니다. <br>

```javascript
const animals = ['dog', 'cat', 'pig', 'cow'];
const animals2 = [...animals, 'chicken'];
const animals3 = [...animals, 'chicken', ...animals];

console.log(animals);
console.log(animals2);
console.log(animals3);
```

위 코드 예시처럼 `spread` 문법을 이용하여 배열의 합성을 진행할 수 있습니다.

#### 객체

아래 코드는 객체에서의 `spread` 예시입니다. `dog` 객체를 `smallDog` 객체에 넣어주었습니다.

```javascript
const dog = {
  name: 'happy'
};
const smallDog = {
  ...dog,
  size: 'small'
};
console.log(dog);
console.log(smallDog);
```

### Rest Parameter

`rest` 문법은 `spread` 문법과 반대로 인자값을 배열 형태로 전달해줍니다. 아래 코드에서 `print` 함수의 인자값으로 `1, 2, 3`을 전달해 주었고 출력을 해보면 `[1, 2, 3]` 과 같은 배열 형태로 전달된다는 점을 알 수 있습니다.

```javascript
function print(...rest) {
  console.log(rest);
}
print(1, 2, 3);
```

아래 코드와 같이 비구조화 할당과 함께 이용할 수도 있습니다.

```javascript
const array = [1, 2, 3, 4, 5];
const [first, ...rest] = array;

console.log(first);
console.log(rest);
```

![](https://images.velog.io/images/napol/post/2fc86c2c-2c5e-451b-9b25-865f56f58e81/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-05-04%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%2012.19.53.png)

중요한 점은 아래 코드와 같이 `rest`를 먼저 사용할 수는 없습니다.

```javascript
const array = [1, 2, 3, 4, 5];
const [...rest, last] = array;

console.log(first);
console.log(rest);
```

> 해당 글은 velopert님의 gitbook을 참고하여 작성되었습니다. 항상 좋은 강의 감사드립니다!
> https://learnjs.vlpt.us/useful/07-spread-and-rest.html
