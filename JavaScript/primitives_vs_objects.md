# Primitives vs Objects

## Composition
`Primitives` are not composed of any other data types.  
`Objects` may be composed of other objects.  
In fact, nearly all objects in JavaScript are a subclass of the `object` class. 
<br/>

## Immutability
`Primitive` values are immutable (i.e. they cannot be changed). 
`Objects` are not immutable by default.  

Using a string method on a primitive string data type does not mutate the original string.  
```JS
let foo = 'bar'
console.log(foo); // 'bar'

foo.toUpperCase();
console.log(bar); // 'bar'
```
<br/>

A new value can be reassigned, but still that does not mutate the original string value.  
```JS
let foo = 'bar'
foo = foo.toUpperCase();
console.log(foo);   // 'BAR'
```
<br/>

In contrast,in an object, the original object properties can be mutated.  
```JS
const obj = { name: 'John', age: 24 };
console.log(obj);   // {name: 'John', age: 24}

obj.name = 'Jane';
console.log(obj);   // {name: 'Jane', age: 24}
```
<br/>

## Pass by Value vs Pass by Reference
When an object is passed to a function, it is passed by reference.  
The function will have a reference to the same obejct, and any modification made would actually be reflected in the original object.  
```JS
const person = { name: 'John', age: 24 };

function incrementAge(person) {
  person.age += 1;
  return person;
}

console.log(person.age);  // 24

incrementAge(person);

console.log(person.age)   // 25
```
<br/>

When a primitive is passed to a function, it is passed by value.  
A copy of the primitive itself is passed.  
```JS
const age = 24;

function incrementAge(age) {
  age += 1;
  return age;
}

console.log(age);   // 24

incrementAge(age);

console.log(age);   // 24
```
<br/>

## Compare by Value vs Compare by Reference
Objects are compared by reference.  
This means that, while an object will always equal itself, two objects with same properties (even a deep or shallow copy of the object) won't be equal.  
```JS
const obj1 = { color: 'blue' };
const obj2 = { color: 'blue' };
const obj3 = { ...obj1 };

console.log(obj1 === obj2);   // false
console.log(obj3 === obj1);   // false
```
<br/>

Primitives are compared by value.  
This means that, primitives always equal to the same primitive value.  
```JS
const color1 = 'blue';
const color2 = 'blue';

console.log(color1 === color2);   // true
```
<br/>

## Copy by Value vs Copy by Reference
When you assign a variable that stores a primitive value to another, the value stored in the varibale is created and copied into the new variable &rarr; copy by value.  
```JS
let color1 = 'blue';
let color2 = color1; 

color1 = 'pink';

console.log(color2);    // 'blue'
console.log(color1);    // 'pink'
```
<br/>

When assigning an object, the new variable merely copies the reference to the original object &rarr; copy by reference.  
Therefore, modifying the object using either variable, actually ends up modifying the original object.  
```JS
const obj1 = { color: 'blue' };
const obj2 = obj1;

obj1.color = 'pink';
obj2.color = 'green';

console.log(obj1);    // {color: 'green'}
console.log(obj2);    // {color: 'green'}

console.log(obj1 === obj2);   // true
```



### References
- [What are the differences between primitives and objects in JavaScript?](https://www.designcise.com/web/tutorial/what-are-the-differences-between-primitives-and-objects-in-javascript)
