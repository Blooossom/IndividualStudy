# useMemo vs React.memo

<aside>
💡 React.memo

</aside>

- React.memo는 Higher-Order-Components(HOC)
    - HOC는 컴포넌트를 인자로 받아 새로운 컴포넌트를 다시 return해주는 함수
    
    ```jsx
    const NewComponent = higherOrderComponent(WrappedComponent);
    ```
    
- 일반 컴포넌트는 인자로 받은 props를 UI에 활용하는 반면에 HOC는 인자로 받은 컴포넌트를 새로운 별도의 컴포넌트로 만듦
- HOC는 리액트의 API가 아니라 리액트가 컴포넌트를 구성하는데 있어서의 일종의 패턴

```jsx
const MyComponent = React.memo((props) => {
	return ~}
)
```

- 만약 컴포넌트가 같은 props를 받을 때 같은 결과를 렌더링한다면 React.memo를 사용하여 불필요한 컴포넌트 렌더링을 방지할 수 있음
- 즉 컴포넌트에 같은 props가 들어온다면 리액트는 컴포넌트 렌더링 과정을 스킵하고 마지막에 렌더링된 결과를 재사용함
- React.memo는 오직 props가 변경됐는지 아닌지만 체크
- 만약 React.memo에 감싸진 함수형 컴포넌트가 함수 내부에서 useState나 useContext같은 훅을 사용하고 있다면, state나 context가 변경될 때마다 리렌더링
- 기본적으로 props가 들어온 object는 shallow compare로 비교
- 즉 props로 들어온 number, string과 같은 scarlar값은 실제 값이 동일한가를 비교하지만 object의 경우 scarlar 값과 달리 같은 값을 ‘reference’하고 있는 지를 비교

<aside>
💡 useMemo

</aside>

- useMemo는 memoize된 값을 return하는 hook
- 인자로 함수와 dependencies를 받음
- useMemo는 두번째 인자로 준 의존 인자 중에 하나라도 변경되면 값을 재계산
- 이를 통해 매 렌더 시마다 소요되는 불필요한 계산을 피할 수 있음
- 만약 dependencies인자로 아무것도 전달되미 않는다면, 매 렌더 시마다 항상 값을 새롭게 계산하여 return

<aside>
💡 공통점

</aside>

- React.memo와 useMemo 모두 props가 변하지 않으면 (이전 props와 동일하면)인자로 넘긴 함수는 재실행되지 않고, 이전의 메모이즈된 결과를 반환한다는 점에서 공통점

<aside>
💡 차이점

</aside>

1. React.memo는 HOC, useMemo는 hook
2. React.memo는 HOC이기 때문에 클래스형 컴포넌트, 함수형 컴포넌트 모두 사용가능하지만 useMemo는 hook이기 때문에 오직 함수형 컴포넌트 안에서만 사용 가능

<aside>
💡 vs useCallback

</aside>

- useCallback 역시 hook이기 때문에 함수형 컴포넌트 안에서만 사용 가능
- useMemo의 경우 함수의 연산량이 많을 때 이전 결과값을 재사용하는 목적이고, useCallback은 함수가 재생성되는 것을 방지하기 위한 목적
