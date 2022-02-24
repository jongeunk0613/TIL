# React
`React`는 유저 인터페이스를 만들기 위한 `JavaScript 라이브러`리다.  
<br/>

> ### library vs framework
> - `Library`는 하나의 기능을 제공하거나 하나의 측면을 해결하기 위한 것이다. 개발자가 주도권을 가지고 library의 코드를 불러와서 사용한다. 
> - `Framework`는 여러 기능을 제공하고 여러면의 측면을 해결해준다. 또한, framework가 주도권을 가지고 있어 어느 부분에 어떤 코드를 작성할지 지정한다. 따라서 framework가 개발자의 코드를 불러와서 사용한다. 

<br/>

`Angular`와 비교해보면, `Angular`는 UI 외에 의존성 주입(dependency injection), CSS 캡슐화, 등등에 대한 처리를 제공한다.  
하지만 `React`는 화면의 뷰/UI 부분만을 당담한다. 

<br/><br/>

## React vs ReactDOM vs React Native
`React`는 사용자 인터페이스를 나타내는 가상의 오브젝트(Virtual DOM)을 만든다.  
`ReactDOM`은 Virtual DOM을 바탕으로 실제 DOM을 업데이트하는 라이브러리다. 이런 의미에서 `ReactDOM`은 `React`와 `DOM` 사이에 풀(glue)와 같은 역할을 한다. 
<br/>

`ReactDOM`이 별도의 라이브러리로 제공되는 이유는 바로 `React Native` 때문이다.  
`ReactDOM`는 개발자가 만든 UI가 브라우저에서 볼 수 있도록 한다 &rarr; Firefox, Chrome, Safari, Edge, etc  
`React Native`는 개발자가 만든 UI가 네이티브 앱에서 볼 수 있도록 한다 &rarr; Android, iOS



### References
- [React tutorial - React intro](https://react-tutorial.app/app.html?id=333)
