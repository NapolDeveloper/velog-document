### useReducer

`useState`보다 복잡한 로직을 필요로 하는 경우 `useReducer`라는 `react hook`을 이용할 수 있습니다. 또한 상태관리 로직을 컴포넌트에서 **분리**할 수 있다는 장점이 있습니다(다른 파일에도 작성가능). 먼저 `useState`를 추가했던 방식과 동일하게 추가해 줍니다.

```javascript
import React, { Fragment, useReducer } from 'react';
```

아래 코드는 `useState`포스트에서 작성한 기능을 `useReducer`로 변경한 코드입니다. [> useState 포스트 <](https://velog.io/@napol/React-useState)

#### CounterReducer.js

```javascript
function reducer(state, action) {
  switch (action.type) {
    case 'INCREMENT':
      return state + 1;
    case 'DECREMENT':
      return state - 1;
    default:
      return state;
  }
}

export default function CounterReducer(props) {
  // useReducer(function, initial state);
  const [number, dispatch] = useReducer(reducer, 0);

  const onIncrease = () => {
    dispatch({ type: 'INCREMENT' });
  };
  const onDecrease = () => {
    dispatch({ type: 'DECREMENT' });
  };

  return (
    <Fragment>
      <Container>
        <CountText>{number}</CountText>
        <ButtonContainer>
          <ClickButton onClick={onIncrease}>+</ClickButton>
          <ClickButton onClick={onDecrease}>-</ClickButton>
        </ButtonContainer>
      </Container>
    </Fragment>
  );
}
```

위 코드에서 `number`는 현재 상태, `dispatch`는 `action`실행 함수, `reducer`는 상태 업데이트 로직 함수, 마지막으로 `0`는 초기값입니다.

1. 버튼 클릭시 `onClick` 함수를 통해 `onIncrease` or `onDecrease`함수 실행.
2. `dispatch`를 호출하여 type이 담긴 객체 형태를 전달.
3. `reducer`에 switch문을 통해 사용할 로직 검사.
