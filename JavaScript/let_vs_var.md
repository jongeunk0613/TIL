# let vs var

ES6에서 새로운 변수 선언 방법인 `let`가 나온다. 기존의 `var`과의 차이를 알아보자.

## 1. Scope
`var`로 선언된 변수는 `전역 스코프` 또는 `지역 스코프`를 갖게 되고  
`let`로 선언된 변수는 `블록 스코프`를 갖게 된다. 

<br/>

```javascript
for (var i = 0; i < 5; i++) {
	console.log("Inside the loop:", i);
}

console.log("Outside the loop:", i);
```

<details>
  <summary>Output: </summary>
  
  ```javascript
  Inside the loop: 0 
  Inside the loop: 1 
  Inside the loop: 2 
  Inside the loop: 3 
  Inside the loop: 4 
  Outside the loop: 5
  ```
</details>

위의 예제에서 `var`로 선언된 `i` 변수는 전역 변수이기 때문에 `for` loop의 안밖에서 접근이 가능하다. 

<br/>

```javascript
for (let i = 0; i < 5; i++) {
	console.log("Inside the loop:", i);
}

console.log("Outside the loop:", i);
```

<details>
  <summary>Output: </summary>
  
  ```javascript
  Inside the loop: 0 
  Inside the loop: 1 
  Inside the loop: 2 
  Inside the loop: 3 
  Inside the loop: 4 
  Uncaught ReferenceError: i is not defined
  ```
</details>

이번 예제에서는 `i` 변수가 `let`으로 선언되기 때문에 블록 스코프를 갖게 되고 따라서 `for` loop 안에서만 접근이 가능하다. 밖에서 접근을 시도할 경우에는 위와 같은 에러가 발생한다. 

<br/><br/>

## 2. 전역 프로퍼티

`var`로 전역 변수를 선언할 경우 전역 오브젝트의 프로퍼티에 추가된다.  
웹 브라우저 전역 오프젝트는 `window`이고 Node의 전역 오브젝트는 `global`이다. 

```javascript
var a = 10;
console.log(window.a); // 10
```
<br/>

하지만 `let`로 전역 변수를 선언할 경우에는 전역 오브젝트의 프로퍼티에 추가되지 않는다. 

```javascript
let b = 20;
console.log(window.b); // undefined
```
<br/><br/>

## 3. 재선언

`var`는 같은 변수를 여러번 선언해도 에러가 발생하지 않는다. 

```javascript
var counter = 10;
var counter;
console.log(counter); // 10
```
<br/>

하지만 `let`은 같은 변수를 한번 이상 선언할 경우 에러가 발생한다. 
```javascript
let counter = 10;
let counter; // error
```
<br/><br/>

## 4. Temporal Dead Zone (TDZ)

`let`으로 선언한 변수들은 TDZ가 있고 `var`로 선언한 변수들은 TDZ가 없다. 
TDZ를 이해하기 위해서는 각 두 변수의 생명주기(life cycle)를 살펴봐야 한다. 
변수의 life cycle은 두 단계로 이루어져 있다: 생성(creation) 및 실행(execution)
<br/>

### var 변수

- 생성 단계: JavaScript engine이 `var` 변수에 메모리 공간을 할당하고 변수 값을 `undefined`으로 초기화한다.
- 실행 단계: 지정할 값이 있을 경우, JavaScript engine이 `var` 변수에 해당 값을 지정한다. 
```javascript
  function salute() {
    console.log(message);
  }
  
  salute();   // undefined
  
  var message = "Hello there!";
```
<details>
  <summary>Steps </summary>
	
  - `message` 변수와 `salute` 함수에 메로리 공간이 할당된다. 이때 `message` 변수의 값은 `undefined`으로 초기화된다. 
  - `salute` 함수가 실행되고 `message` 변수를 출력한다. 해당 시점에서 `message` 변수의 값은 `undefined`이기 때문에 해당 값이 출력된다.  
  - `message` 변수의 값이 `Hello there!`로 지정된다. 
	
</details>
<br/>

### let 변수

- 생성 단계: JavaScript engine이 `let` 변수에 메모리 공간을 할당하지만 변수 값을 초기화하지 않는다. 초기화하지 않은 변수에 접근하려고 시도한다면 `ReferenceError`가 발생한다.
- 실행 단계: `var` 변수가 동일하게, 지정할 값이 있을 경우 해당 값이 할당된다. 

```javascript
  /// TDZ 시작
  function salute() {
    console.log(message);
  }
  
  salute();   // Uncaught ReferenceError: message is not defined
  
  let message = "Hello there!";	// TDZ 종료
```
<details>
  <summary>Steps </summary>
	
  - `message` 변수와 `salute` 함수에 메로리 공간이 할당된다. 이때 `message` 변수의 값은 초기화되지 않는다.
  - `salute` 함수가 실행되고 `message` 변수를 출력한다. 하지만 해당 시점에서 `message` 변수의 값은 초기화되지 않았기 때문에 `ReferenceError`가 발생하고 코드 실행이 멈춘다.
	
</details>
<br/>

위의 예제처럼, 블록의 시작부터 `let` 변수 값이 할당될 때까지의 구간, 즉 해당 변수 값을 접근하지 못하는 구간을 `Temporal Dead Zone(TDZ)`이라고 부른다. 

<br/><br/>
## 요약
| |var|let|
|---|---|---|
| 스코프 | 전역 또는 지역 | 블록 |
| 재선언 | 가능 | 불가능 |
| 프로퍼티에 | 추가됨 | 추가되지 않음 |
| TDZ | 있음 | 없음 |

<br/><br/>
## References
- [Difference between var and let](https://www.javascripttutorial.net/es6/difference-between-var-and-let/)
- [JavaScript let: Declaring Block-Scoped Variables](https://www.javascripttutorial.net/es6/javascript-let/)
