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



