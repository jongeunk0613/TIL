# JSX

`JSX`는 JavaScript를 `확장한 문법`으로 React에서 HTML를 표현하기 위해 사용된다.  

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

function Hello(props) {
  return <h1>Hello World!</h1>;
}

ReactDOM.render(<Hello />, document.getElementById('root'));
```
위의 예제를 보면 React가 import 되고 있지만 그 어디에도 사용되지 않고 있는 것을 볼 수 있다.  
그 이유는 html element를 생성하는 React 함수 `React.createElement`와 관련있다.  

<br/><br/>

# React.createElement

React.createElement는 다음과 같이 사용할 수 있다:  
> React.createElement(component, props, ...children);

예제 1)
```javaScript
  <h1> Hello World! </h1>     //JSX
  React.createElement("h1", null, "Hello World!");
```

예제 2)
```javaScript
  <title id="home_title" className=">This is JSX and React.createElement</title>    //JSX
  React.createElement(
```


1. 
- why need to `import React from "react"?`
- because jsx is converted to React.createElement()
  => this is for only until React16, from React17 and on, it is not required
  tmi -> React17 has no new feature, it is released to make further updates more easier
 
  How to use React.createElement
  - JSX to script
  - how to convert attribute
  
- JSX is a syntactic sugar or React.createElement
- JSX is not part of the browser, therefore a tool to transform it to javascript is needed (Babel)

2. 

JSX turned into React.createElement that returns object => JSX = object
JSX can be thought of as a object in a simplified version (https://react-tutorial.app/app.html)
This object is a representation of the UI that React maintains in a virtual DOM.
JSX가 object처럼 여겨질 수 있기 때문에 object처럼 동작할 수 있음. 



