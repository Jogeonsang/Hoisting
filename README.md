# Hoisting
Javascript에 Hoisting을 알아보자

Hoisting은 어쩌면 우리가 무의식적으로 사용하고있을 수 있다.
Hoisting에 특징을 알아보자

모든 변수 선언은 호이스트된다.
호이스트란, 변수의 정의가 그 범위에 따라 선언과 할당으로 분리되는 것을 의미한다. 
쉽게 말하면 변수가 함수내에서 정의되었을 경우 선언이 함수의 최상위로, 함수 바깥에서 정의되었을 경우는 전역 컨텍스트의 최상위로 변경됩니다.

말로하는것보다 코드로 이해하는게 더 빠르니 코드를 봅시다.

``` javascript
const hoisting = () => {
  console.log("First-Name:", name);
  var name = "Marcus";
  console.log("Last-Name:", name);
}

hoisting();
// First Name : undefined
// Last Name : Marcus
// First Name이 undefined인 이유는 지역변수 name이 호이스트 되었기 때문이다.

```
위 hoisting이라는 함수는 자바스크립트로 이해하면 다음과 같이 표현할 수 있다.
``` javascript
const hoisting = () => {
     var name; // name 변수는 호이스트 되었습니다. 할당은 이후에 발생하기 때문에, 이 시점에 name의 값은 undefined 입니다.
     console.log("First name : " + name); // First Name : undefined
     name = "Marcus"; // name에 값이 할당 되었습니다.
     console.log("Last Name : " + name); // Last Name : Ford
}
```
