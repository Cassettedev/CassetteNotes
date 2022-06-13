[[Home]]
[[Cassette]]
[[Wiki]]
[[Blog]]

[[Humanities]]
[[STEM]]
[[Health]]
[[Docs]]

### Basics
```js
console.log() 
```
takes the respective input and outputs it to the console.

### Assigning variables
There are many ways to assign variables in Javascript. One of the main ways is with `let`.
```js
let variable = 
```
`let` is block-scoped, meaning it can only be used within the "block" of code that it resides in, the "block" being anything that is surrounded by curly braces ```{}```. If declared outside of a "block", it will be accsesable to everything. **You can think of the entire file as one "block" of code.** 
`let` can be declared once and re-defined, but not re-declared. To explain:
This will work
```js
let greeting = "say Hi";
greeting = "say Hello instead";
```
But this will not
```js
let greeting = "say Hi";
let greetng = "Say Hello instead";
```
And if each variable is defined in different scopes, there will be no problem
```js
let greeting = "say Hi";
if (true) {
let greeting = "say Hello instead";
    console.log(greeting); // "say Hello instead"
}    
console.log(greeting); // "say Hi"
```

Another way to assign variables is to assign them with `var`. `var` is the original way of declaring variables, but is not often used.
```js
var variable =
```
When declared inside a function, it is scoped only to that function. When it is declared outside a function, the scope becomes global.
`var` can be re-defined and re-declared, like so:
```js    
var greeter = "hey hi";
var greeter = "say Hello instead";
```
As well as
```js
var greeter = "hey hi";
greeter = "say Hello instead";
```
Both of these will work fine. This can be a problem if you are not careful. For example:
```js
var greeter = "hey hi";
var times = 4;

if (times > 3) {
	var greeter = "say Hello instead"; 
}
console.log(greeter) // "say Hello instead"
```
You can imagine that the `console.log(greeter)` may be several lines down in the program, and it may not have the intended effect.