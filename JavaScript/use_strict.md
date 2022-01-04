## 배경 : JavaScript's backward compatibility and ECMAScript5 (ES5)

JavaScript의 특징 중 하나는 바로 **역호환성**이다. 역호환성이란, 어떠한 기능이 한번 JavaScript 언어의 유효한 일부분으로 받아들여지면, 해당 기능을 유효하지 않은 JavaSscript로 만드는 언어의 향후 변경은 없을 것이라는 것이다.  
이 말은 **이전 기능은 변경되지 않으면서 새로운 기능이 언어에 추가된다**는 뜻이다. 한번 작성된 코드는 깨지지 않는다는 장점이 있지만 한편으론 JavaScript의 제작자들이 한 실수나 불완전한 결정이 영원히 언어에 남게 된다는 것이다. 

2009년 **ECMAScript 5(ES5)** 가 등장하기 전까지는 그랬다.  
해당 버전에는 언어에 새로운 기능들이 추가되었고 기존에 존재했던 몇 기능들이 수정되었다. 이전 코드가 계속 정상적으로 작동하도록 하기 위해 이러한 수정 사항은 기본적으로 해제되어 있다. 수정사항을 활성화하려면 `"use strict"`란 특별한 지시어로 명시해야 한다. 
  

## 사용법
### 파일
파일 상단에 지시어를 입력한다.  
파일 전체가 "최신(modern)" 방법으로 동작한다. 
```javascript
"use strict";

// 해당 코드는 최신 방법으로 동작한다
```

### 함수
함수 내용의 상단에 지시어를 입력한다.  
strict mode가 해당 함수에만 적용된다.
```javascript
function() {
  "use strict";
  
  //... 코드 내용 ...
}
```

### 브라우저 콘솔
브라우저 콘솔은 기본적으로 strict mode를 사용하지 않기 때문에 명시적으로 활성화해야 한다.  
최상단에 `"use strict"`를 입력하고 `<Shift+Enter>`를 눌러서 여러 줄의 코드를 입력한다.
```javascript
"use strict"; <Shift+Enter for a newline>
//... 코드 내용
<Enter to run>
```
Firefox와 Chrome 같은 대부분의 브라우저에서 동작한다.  
만약 그렇지 않을 경우, 아래의 방법으로 가능하다.
```javascript
(function() {
  'use strict';
  
  // ... 코드 내용 ...
})()
```



### ⚠️ 주의사항
#### ❗ `"use strict"`는 항상 최상단에 ❗ 
최상단에 위치에 있지 않으면 적용되지 않는다.
```javascript
alert("some code");
// 아래의 "use strict"는 무시된다 - 최상단에 위치해야 한다

"use strict";

// strict 모드가 활성화되지 않는다
```
`"use strict"` 전에는 주석만 자리할 수 있다.  

#### ❗ `"use strict"`를 취소할 수 있는 방법은 없다 ❗ 
JavaScript 엔진을 이전 동작 방식으로 되돌릴 수 있는 `"no use strict"`와 같은 지시어는 존재하지 않다.  
한번 strict mode가 활성화되면 되돌릴 방법은 없다. 

## References

- [The modern mode, "use strict"](https://javascript.info/strict-mode)
- [You Don't Know JS Yet: Get Started - 2nd Edition (Chapter 1: What *Is* JavaScript)](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/get-started/ch1.md)
