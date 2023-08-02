# Hoisting

<aside>
💡 Intro

</aside>

- 인터프리터가 변수와 함수의 메모리 공간을 선언 전에 미리 할당하는 것을 의미
- var로 선언한 변수의 경우 호이스팅 시 undefined로 변수를 초기화
- let/const 로 선언한 변수의 경우 호이스팅 시 변수를 초기화하지 않음

- 호이스팅을 설명할 때 주로 “변수의 선언과 초기화를 분리한 후 선언만 코드의 최상단으로 옮기는” 것으로 말하곤함
- 따라서 변수를 정의하는 코드보다 사용하는 코드가 앞서 등장할 수 있음
- 다만 선언과 초기화를 함께 수행하는 경우 선언 코드까지 실행해야 변수가 초기화된 상태가 됨에 주의

<aside>
💡 Ex

</aside>

```jsx
function description(name) {
	console.log(name);
}

description("JavaScript");

/*위 경우가 일반적인 코드 작성 순서*/

/*-----------------------------------------------------------------------------------*/
description("JavaScript");

function description(name) {
	console.log(name);
}

/*함수 호출이 함수 자체보다 앞서 존재하지만 위 코드도 동작*/
```

<aside>
💡 선언만 호이스팅 대상

</aside>

- JavaScript는 초기화를 제외한 ‘선언만' 호이스팅
- 변수를 먼저 사용하고 그 후에 선언 및 초기화가 나타나면, 사용하는 시점의 변수는 기본 초기화 상태(var 선언 시 undefined, 그 외에는 초기화X)

<aside>
💡 let과 const의 호이스팅

</aside>

- let과 const로 선언한 변수도 호이스팅 대상이지만 var와 달리 호이스팅 시 undefined로 변수를 초기화 하지는 않음
- 따라서 변수의 초기화를 수행하기 전에 읽는 코드가 먼저 나타나면 예외가 발생
