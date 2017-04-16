
# Javascript Style Guide

## Function Syntax

_Why_: for readability, make sure to put single spaces between parentheses and brackets
```js
// suggested
function fooBar (argumentX) {
    // do some logic
}

// avoid
function foobar(argumentX){
    // do some logic
}
```

## Conditional Statement Syntax

_Why_: for readability, follow same rules as Function Syntax. Always use brackets. Ternary operators are acceptable.
```js
//suggested
if (condition === true) {
    //do some logic
}

for (i = 0; i < something.length; i++) {
    //loop logic here
}

var ternary = condition === true ? 'this is true' : 'that is false';

//avoid
if (condition===true) //logic here

for(i=0;i<somthing.length;i++)
    //do the logic
```

## String literals

_Why_: avoid using combinations of single and double quotes. Single quotes should be used at all times.

```js
// suggested
var str = 'Hello World';
var sample = 'that\'s cool';
  
// avoid
var mal = "something's wrong.";
var combo = "what's up, " + your.name + ' for today?'
```

## Variable declaration

### ES5
_Why_: follow best practices and always declare variables using `var`. Variable declarations should always be made before logic. 

```js
// suggested
function foo() {
    var bar;
    // logic, etc
    bar = 2;
}

function parent() {
    var i = 0, // also acceptible to occupy one line, if variable declarations are short enough
        j = 1,
        k = 2;
    return i + j + k;
}

// avoid

function foo(bar) {
    if (bar) {
      var x = 0;
    }
}
```

variables that are intented to be declared as global should be attached to the window object

```js
// suggested
window.newVar = 2;

// avoid
newVar = 2;
```

### ES6+
_Why_: follow best practices and always declare variables using `let` or `const`. `const` variables are immutable.

```js
// suggested
const foo = 3;
let bar;
bar = 2;
let sum = foo + bar;

// avoid

const bad = 3;
bad++;


```

## Spacing

_Why_: to normalize and homogenize formatting and indents
```js
// suggested - 4 spaces, no tabs
var indent = 4;
function anon () {
    // logic indented 4 spaces
}
```

## Promises
_Why_: for consistency and readability. Also, try to avoid [anti-patterns](https://github.com/petkaantonov/bluebird/wiki/Promise-anti-patterns)!
```js
// suggested - new lines for promise methods
var promiseFactory = function () {
    // method that returns a promise
};
promiseFactory()
.then(function resolved () {
    // callback code for resolved promise
})
.catch(function rejected () {
    // callback code for error handling
});

// avoid
promiseFactory().then(function () {
    // logic
});
```

## Object property declaration
_Why_: to avoid messy merges and normalize code alphabetical preference
```js
// sugested - properties should be in alphabetical order and camelcase
var obj = {
    aProperty: true,
    bProperty: false,
    cProperty: 3
};

// avoid
var obj = {
    bProp: false,
    aProp: false
};
```
### ES6+
_Why_: take advantage of ES6 destructuring
```js
// suggested
let foo = 1;
let bar = '2';
let obj = { foo, bar };

// avoid
let foo = 1;
let bar = '2';
let obj = {
    foo: foo, 
    bar: bar
};
