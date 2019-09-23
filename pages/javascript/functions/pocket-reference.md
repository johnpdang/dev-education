# Pocket reference

{% embed url="https://medium.com/@ajmeyghani/javascript-functions-a-pocket-reference-d42597ceb496" %}

Functions are callable objects in JavaScript. It is very important to note that in JavaScript functions are objects. It might be misleading because when you use the `typeof` operator on a function, you get `function` as the output. This is one of the instances where JavaScript lies to you. The output of `typeof function () {}` should be `object` because functions are objects in JavaScript. That makes functions very powerful, because you can think of them as callable objects. You can use a function as an object, a piece of reusable code, or a function that creates objects.

### Creating Functions

There are two main ways of defining functions:

If a statement starts with the `function` keyword, then you have a function declaration:

`function myFn() {}`

But if you assign a function to a variable, you have a function expression:

`const fnRef = function myFn() {};`

Note that you need a semi-colon when creating a function expression, but you should not include one when creating a function declaration.

### Function Inputs and Outputs

You can pass values into and return values from a function. For example, you can make a function that takes two numbers and `returns` the result of adding them:

```text
function add(a, b) {
 return a + b;
}
```

If you notice, the inputs to the function are placed inside the parenthesis separated by commas. Note that `a` and `b` represent the inputs to the function. If you don't specify any return values for your function, JavaScript will return `undefined` by default:

```text
function fn() {
 const a = 1;
 // other stuff.
 // no return.
}
fn(); // `undefined` is returned.
```

Note that arguments are always passed by value to functions. The value could be a primitive or a reference value in the case of non-primitives. This means that if you assign the argument to another value or thing, it will not affect the thing outside of the function:

```text
const n = 1;
function change(x) {
 x = 5;
}
console.log(n); // 1;
change(n);
console.log(n); // 1;
```

It doesn’t matter what is passed in, the behavior is consistent, even if the input is a non-primitive \(an object\):

```text
const n = {value: 1};
function change(x) {
 x = {};
}
console.log(n); // {value: 1};
change(n);
console.log(n); // {value: 1};
```

However, if you decide to change the property of the object that the reference is pointing to, the object will be mutated:

```text
const n = {value: 1};
function mutate(x) {
 x.value = 22;
}
console.log(n); // {value: 1}
mutate(n);
console.log(n); // {value: 22}
```

As you can see, arguments passed to functions are always copied. In the case of primitives, the actual values are copied, and the case of non-primitives, the reference is copied and becomes available in the function and assigning the argument to another thing does not change the original value.

### The `arguments` Object

Every function in JavaScript has access to the magical `arguments` object inside the function body that contains the arguments passed to the function. Let's look at a basic example to demonstrate how you can access the `arguments` object.

In this example, we are going to create a function called `sum` that is going to simply return the `arguments` object when it is called:

```text
function sum() {
 return arguments;
}
```

When you call the function with `sum(1,2,3)`, you can see that `arguments` is an object with three keys and values:

So it is important to note that the `arguments` object is not an array object. This means that `arguments` does not inherit array methods and the following returns false:

```text
function sum() {
 return arguments;
}
const args = sum(1,2,3);
Object.getPrototypeOf(args) === Array.prototype; // -> false
Array.isArray(args); // -> false
```

As of ES2015, you can use the `Array.from` method to convert an iterable object like the `arguments` object to an array. Alternatively, you can call the `slice` method of `Array.prototype` in the context of the `arguments` object to return an array containing the values:

```text
function sum() {
 return arguments;
}
const args = sum(1,2,3);
const argArray = Array.prototype.slice.call(args); // -> [1,2,3]
Object.getPrototypeOf(argArray) === Array.prototype; // -> true
Array.isArray(Array.from(args)); // -> true
```

### Executing a Function

A function can be executed, this is generally known as calling a function. You can call a function by using the name of the function, followed by a set of parenthesis `()`:

```text
add();
```

Notice that we are calling the functions without any inputs. Let’s give the function to numbers as inputs:

```text
add(1, 2); // -> 3
```

In addition to the `()` operator, there are 3 other ways to call a function. That is, using:

So for our simple example, let’s call the function using all these methods and explore when you would want to use each method.

### `Function.prototype.call`

When you use `call` to execute a function, the first argument is the value of the context object. And the reset of the values are arguments to the function, separated by commas:

```text
add.call({}, 1,2); // -> 3
```

In the snippet above, we are calling the `add` function with an empty object as context, two arguments, `1` and `2`.

### `Function.prototype.apply`

Using `apply` is similar to `call`, you pass the context object as the first argument. But you pass the arguments to the function as an array instead of passing them one by one:

```text
add.apply({}, [1,2]); // -> 3
```

In the snippet above, we pass an empty object for the context, and an array for the arguments. The first argument is `1` and the second is `2`.

### Calling Function with `new`

The purpose of the `new` keyword is to invoke a function as a constructor of objects. So you wouldn't really call the `sum` function above with the `new` keyword. When a function is called with the `new` keyword, couple of things happen behind the scenes:

* A new empty object is created
* The context object `this` is bound to the new empty object
* The new object is linked to the function’s prototype property
* `this` is automatically returned unless another non-primitive value is returned explicitly from the function

This is the mechanism provided by JavaScript to link objects with prototype objects. You can learn more about prototypes in my [other article](https://medium.com/p/d88f550ffce3), but for now just remember that these functions are known as constructor functions and by convention, their name starts with an uppercase letter. Let’s look at a simple constructor function that can be used to create `Car` objects:

```text
function Car() {
 this.color = 'black';
}
const myCar = new Car();
myCar.color; // -> 'black'
```

As you can see, in the function we use the context object `this` to assign the `color` property. And then we call the function using the `new` keyword and assign the result to the `myCar` variable. Now, `myCar` is the object created by the `Car` constructor function.

### The Context Object, `this`

The context object, `this` is a dynamic object which is set dynamically depending on the way a function is called. There are several rules to follow in order to figure out what `this` is bound to.

First, check if the function of interest is called with the `new` keyword. If so, then `this` is bound to the new object created by the function. If not, check if the function is being called with `call` or `apply`, if so, the first argument tells you what the value of `this` is bound to. If not, check if the function is called in the context of another object, `(someObj.fn())`, if so, then `this` is bound to the object. If none of these cases are met and the function is simply invoked without any context, `this` will be bound to the global object in `non-strict` mode. However, in the `strict mode`, the value of `this` will be `undefined`.

Let’s look at some examples and see how the context object is bound to.

### Call with `new`

The first example, is just a review from the previous section. That is, calling a function with the `new` keyword. When you can a function with the `new` keyword, the context object is bound to the instance object created by the function:

```text
function Car() {
 this.color = 'Black';
}
const myCar = new Car();
```

To figure out how `this` is bound, we look at the line where the function is called. In this case, the function is called with the `new` keyword, so then we know that the context is bound to the new object that is going to be returned by the function. This is the case that you always have to check first, because it over rules the other ones.

In the next example, we are going to call a function with `call` and `apply`.

### Using `call` or `apply`

Let’s see how the value of `this` gets bound when we call a function with `call` or `apply`. For this example, we are going to create a simple function called `printMessage` that is going to read the `name` property on this and return a message:

```text
function printMessage(msg) {
 return msg + ' ' + this.name;
}
const message = printMessage.call({name: 'AJ'}, 'Welcome!');
// -> 'Welcome! AJ'
```

In the example above, we look at the line where the function is called and you can see the function is called by `call` and the value of `this` is explicitly passed as the first parameter. So inside the function, `this` will be bound to `{name: 'AJ'}` and when we call the function, it will return the following result:

The `apply` case is very similar to the case above, except we would pass the arguments in an array, but the value of `this` will still be bound to the first argument passed, that is: `{name : 'AJ'}`:

```text
function printMessage(msg) {
 return msg + ' ' + this.name;
}
const message = printMessage.apply({name: 'AJ'}, ['Welcome!']);
```

The output is the same as the `call` example, and the important thing to note here is that when you call a function with `call` or `apply`, the first argument is the context object that will be used inside the function as `this`.

### Implicit Binding

The next case, to look in order, is when a function is called in the context of another object. So first let’s create an object and define a method on it and then call the method in the context of the object:

```text
const util = {
 name: 'Utility',
 getName: function () {
 return this.name;
 }
};
const name = util.getName(); // -> Utility
```

Again first we look at the line where the function is called to determine how `this` is bound to. When you look at how the function is called, you can see the function is called in the context of the `util` object, that is `util.getName()`. So the context object is implicitly bound to the `util` object.

The last case, is when a function is called without any context. Using the sample `util` object above, we can assign the `getName` function to a variable and then call the function without any context:

```text
const util = {
 name: 'Utility',
 getName: function () {
 return this.name;
 }
};
const getName = util.getName;
const name = getName();
```

In this case, when the function is called, the context object by default is set to the global object. So if you are in the browser, `this` will be bound to the `window` object, and if you are on the server, `this` will be bound to the `global` object.

It is important to note however, in `strict mode` the value of `this` will be undefined if you call a function as is:

```text
function setName(name) {
 'use strict';
 this.name = name;
}
setName();
```

When you run the function above, we will get the following error:

```text
TypeError: Cannot set property 'name' of undefined
```

The reason is that in `strict mode`, `this` will be set to `undefined` when you call the function without a context. So setting the property on something that is `undefined` is going to throw an error. This is a good thing because then you wouldn't end up setting properties inadvertently on the global object.

### Binding Context with `bind`

It’s worth mentioning that in cases where you want to explicitly bind a function to a context, you can use `bind`. The `bind` method is available to all non-arrow functions and takes the context object as its arguments and returns a new function bound to the given object:

```text
const util = {
 name: 'Utility',
 getName: function () {
 return this.name;
 }
};
const getName = util.getName.bind(util);
const name = getName(); // -> 'Utility'
```

In the snippet above we are calling `bind` on `util.getName` to explicitly bind it to the `util` object. Then it doesn't matter how you can the function, it will always be bound to the `util` object. Try to use `bind` sensibly since it creates a copy of the given function and may not want to copy a function just to set its context. Rather try to use what the language provides, and use `bind` when all other mechanisms fail to provide you with what you need.

### Functions as objects

Since functions are objects, you can use functions as plain objects:

```text
var fnRef = function fnObject () {};
fnRef.someProp = 'foo';
fnRef.hello = function () {
 return 'hello';
};
```

Note that you can then access the properties and methods of this function object:

```text
fnRef.someProp; // -> 'foo'
fnRef.hello(); // -> 'hello'
```

It’s important to note that when you ask for the type of a function JavaScript with return `function` back to you. Even though it's useful, but it's not quite accurate. A more accurate answer would be `object` since JavaScript does not have a non-primitive `function` type:

```text
function a() {}
console.log(typeof a);
```

The snippet above will output `function` to the console, even though `a` is an object that happens to be linked to the `Function.prototype` object:

```text
Object.getPrototypeOf(a); //-> [Function]
```

> For more information about Prototypes, check out my other article on [JavaScript Prototypes.](https://medium.com/p/d88f550ffce3)

### Arrow Functions

Arrow functions were introduced in ES2015 and make it easy to make non-method functions. Arrow functions, as opposed to ordinary functions, do not create a new context. That means that the `this` object is not bound to the function when an arrow function is created. Also, arrow functions cannot be used as constructors and they do not have a `prototype` property. Moreover, they do not have their own `arguments` object and because of that you would need to use a rest parameter to read multiple arguments. In the following sections we will look at how to create arrow functions, the behavior of the `this` object and more.

### Creating an Arrow Function

You can create an arrow function using a set of parenthesis for the function arguments, followed by an arrow `=>`, and a set of curly braces to define the body of the function:

```text
const fn = (a, b) => {
 const x = a + 1;
 const y = b + 2;
 return x + y;
};
const sum = fn(1, 2);
```

The arrow function above is called `fn` and takes two arguments, `a` and `b`. We do some operations in the body of the function and finally `return` the result. And then we call the function and store the result in `sum`. You can also use a shorthand form and omit the curly braces. Then, the given value of the statement is implicitly returned:

```text
const add = (a, b) => a + b;
```

The snippet above is the same as the following:

```text
const add = (a, b) => {
 return a + b;
};
```

Notice that if you are returning an object literal from an arrow function, you must use a set of parenthesis to denote the return value:

```text
const register = (name) => ({
 id: 0,
 name: name,
});
```

Shorthand arrow functions are very useful for one-line statements that you usually see in `map`, `filter`, or `reduce`:

```text
const nums = [1, 2, 3, 4];
const plusOne = nums.map(v => v + 1);
```

In the snippet above, we use an arrow function shorthand form to pass a function to `map` to add one to each member of the array and return a new array. The new array is assigned to `plusOne`. Also, notice that you can optionally remove the arguments parenthesis if you are referencing only one argument, otherwise you will need to include the parenthesis:

```text
const nums = [1, 2, 3, 4];
const sum = nums.reduce((c, v) => c + v);
```

In the snippet above we have to include a set of parenthesis around `c` and `v` since we are using more than one argument for the `map` callback.

### Arrow Functions and Arguments Object

Arrow functions do not get an `arguments` object, the `arguments` object will always refer to the outer scope `arguments`:

```text
const fn = () => console.log(arguments);
fn('hello', 'world');
```

When you call the function above, in the Node environment for example, it will print the invocation arguments of the script and not the function arguments. If you have an arrow function inside an ordinary function, the `arguments` object will refer to the arguments passed to the outer function but not the arrow function:

```text
function outer() {
 const inner = () => console.log(arguments);
 return inner;
}
const r = outer('hello', 'world');
r('inner', 'arguments');
```

In the snippet above we define an arrow function in the `outer` function and we log the `arguments` and we return the inner function. When we call the outer function with some arguments, those arguments will be logged to the console, and not the arguments passed to the inner function.

If you want to read the arguments passed to an arrow function \(or even for ordinary functions\), it’s best to use a rest parameter:

```text
const sum = (...values) => values.reduce((c, v) => c + v);
sum(1, 2, 3, 4);
```

The rest argument above is `values` which is a JavaScript array and does not require any further manipulation to be turned into an array. We simply call reduce on it and add all the numbers up and return the result.

### Arrow Functions and Context

Arrow functions do not create a new context, as opposed to ordinary functions. When you use the `this` keyword to access the context in an arrow function, it will always refer to the context in the outer scope. This is very useful when you want to maintain the context in places where you call functions that take a callback. The simplest example is when you call `setTimeout` with a callback:

```text
function hello() {
 setTimeout(() => {
 console.log(this.name);
 }, 200);
}
hello.call({name: 'tom'});
```

In the snippet above, we define a function called `hello` that logs `this.name` after 200ms. Notice that because we are using an arrow function as the callback to `setTimeout`, we can use the `this` keyword to refer to the outer lexical scope, in this case the `hello` function. Looking at how the `hello` function is invoked, we can see that the context is set to an object `{name: 'tom'}`. If you didn't use an arrow function, you would have the following to options:

```text
function hello() {
 var self = this;
 setTimeout(function() {
 console.log(self.name);
 }, 200);
}
hello.call({name: 'tom'});
```

1. Using `bind` to explicitly bind the callback passed to `setTimeout`:

```text
function hello() {
 setTimeout(function() {
 console.log(this.name);
 }.bind(this), 200);
}
hello.call({name: 'tom'});
```

However, using an arrow function is preferred since they are designed for these kind of situations. Now let’s look at another example:

```text
function Person(name) {
 this.name = name;
}
Person.prototype.talk = function() {
 setTimeout(() => {
 console.log('My name is', this.name);
 }, 100);
};
const tom = new Person('tom');
tom.talk();
```

In the example above, we are using an arrow function inside `setTimeout` and we are using `this` to refer to the outer context, which is the `Person` function. Let's look at another example involving promises:

```text
function defineTypes(options) {
 const types = {
 md: 'markdown',
 pdf: 'pdf',
 };
 return new Promise((r, j) => {
 if(!this.prmary) {
 return j(new Error('no primary context given'));
 }
 r(types[this.primary]); // <-- referencing `this`
 });
}
defineTypes.call({primary: 'pdf'}, {minCount: 1})
.then(r => console.log(r))
.catch(e => console.log(e));
```

In the snippet above we have a function called `defineTypes`. This function defines a map of types and then returns a new created promise. In the promise callback we reference `this` when resolving the given type `r(types[this.primary])`. Because we are using an arrow function for the promise, the `this` refers to the outer function context. Looking at how `defineTypes` is called, we can see that the context is explicitly defined with an object: `defineTypes.call({primary: 'pdf'})`.

### Call and Apply

As we saw before, you can call a function either using `call` or `apply` and pass an object to stand for the function context. Since, arrow functions don't create a new context, `call` or `apply` will not have any effect and you won't be able to define a context for the function. It will simply pass along the arguments passed and `this` will be set to `undefined`:

```text
const sum = (toAdd) => {
 return this.value + toAdd;
};
const r = sum.call({value: 1}, 100);
console.log(r);
```

In the snippet above we define the `sum` function that adds `this.value` with the passed in argument `toAdd`. Then we call `sum` with `call` and we pass `{value: 1}` as the first parameter, and `100` as the second. When we log the value, we will get `NaN` because we adding `undefined` to any number will result in `NaN`. The same is also true if you try to call the `sum` arrow function with `apply` with a given context:

```text
const r = sum.apply({value: 1}, [100]);
```

### Arrow Functions and Constructors

Because arrow functions don’t create a context, and they don’t have a `prototype` property, we cannot use them as constructors. For example, the code below will throw a type error:

```text
const Car = () => {
 this.name = 'car';
};

const c = new Car();
```

If you run the above code, you will get the following error:

As we saw previously, you would either use a function with context for creating objects linked with prototypes:

```text
const Car = function() {
 this.name = 'car';
};
const c = new Car();
```

You can also use a class:

```text
class Car {
 constructor() {
 this.name = 'car';
 }
}
const c = new Car();
```

### Arrow Functions and Promise Chains

Arrow functions are very convenient to use when dealing with sequential promise chains. When dealing with promise chains, you must always return a value from each sequence to ensure the async values are resolved before moving onto the next step in the sequence. Shorthand arrow functions make it very convenient to express sequential promise chains:

```text
readFile('myfile.txt', 'utf-8')
.then(content => replaceValues(content))
.then(newContent => writeFile(newContent, 'file.txt'))
.then(() => console.log('done'));
```

In the snippet above we first read a file, then we replace some values, and finally write the content to a new file. Notice how we are using shorthand arrow functions to return the results in every step to resolve values before moving onto next steps. The code above is equivalent to the following:

```text
readFile('myfile.txt', 'utf-8')
.then(content => {
 return replaceValues(content);
})
.then(newContent => {
 return writeFile(newContent, 'file.txt');
})
.then(() => {
 return console.log('done');
});
```

### Higher Order Functions

In JavaScript, since functions are objects, they can be passed to functions or returned from functions. A higher order function is a function that either returns a function or takes a function as one of its arguments. Let’s look at an example of a higher order function that returns a function:

```text
const writeTo = (path) => {
 return (content) => writeFile(path, content);
};
```

In the snippet above we have defined a function called `writeTo` that takes a file path and returns another function. The returned function takes an argument for the content of the file and calls `writeFile` to write the contents to the given file. The `writeTo` function is especially useful when dealing with promise chains. Suppose we have defined `readFile` and `writeFile` that both return promises:

```text
readFile('file.txt', 'utf-8')
.then(writeTo('newfile.txt'));
```

In the snippet above first we call `readFile` to read the content of a file. The then block takes a function in the following form:

```text
(previousResult) => { }
```

Now when we call our `writeTo` function it passes in the path value and returns another function that can be passed to the `then` block which makes it very convenient. You can also augment the `writeTo` function without worrying about where it's being called as long as you maintain the same public interface.

We will look at more higher order functions examples in the next section where we talk about closures.

### Closures

Generally speaking, a closure is a dynamic reference that is created when an inner function uses variables of an outer function. And to access the closure, you simply call the inner functions returned from the outer function. Let’s demonstrate this with a simple example. First, we need an outer function that defines a variable called `stateVal`:

```text
function makeClosure() {
 let stateVal = 0;
}
```

After that, we need to create a another function inside to reference `stateVal`:

```text
function makeClosure() {
 let stateVal = 0;
 function cl() {
 stateVal += 1;
 return stateVal;
 }
}
```

and finally, we return the inner function:

```text
function makeClosure() {
 let stateVal = 0;
 function cl() {
 stateVal += 1;
 return stateVal;
 }
 return cl;
}
```

Now that we have our closure maker function, we can call it and get access to the closure created:

```text
const inc = makeClosure();
```

Note that `inc` is a closure because it references the `stateVal` variable inside the outer function, so `stateVal` maintains its state every time `inc` is called. So if we call the `inc` function 3 times, we expect the value of `stateVal` to be incremented every time:

```text
inc(); // 1
inc(); // 2
inc(); // 3
```

At the end of the last `inc` call, the value returned is going to be `3`.

### Arrow Functions and Closures

Arrow functions behave the same as functions with context. Let’s rewrite the example above with arrow functions:

```text
const makeClosure = () => {
 let stateVal = 0;
 const cl = () => ++stateVal;
 return cl;
};

const inc = makeClosure();
console.log(inc()); // -> 1
console.log(inc()); // -> 2
console.log(inc()); // -> 3
```

As you can see the idea is the same, we just used arrow functions to create the `cl` inner closure.

Now what do you think will happen if we create another `inc` closure and call it?

```text
const makeClosure = () => {
 let stateVal = 0;
 const cl = () => stateVal++;
 return cl;
};

const inc = makeClosure();
const inc2 = makeClosure();

console.log(inc()); // -> 1
console.log(inc()); // -> 2
console.log(inc()); // -> 3
console.log(inc()); // -> 4

console.log(inc2()); // -> 1
console.log(inc2()); // -> 2
console.log(inc2()); // -> 3
console.log(inc2()); // -> 4
```

When we create a new `inc` it creates a copy of the closure and the counter starts at 0 again. But that doesn't interfere with our first existing `inc` closure. As you can imagine you can create as many as copies as you want, but you should have a very good reason to do that, because every closure that you create consumes extra amount of memory.

### Closures and Encapsulation

Closures are very useful for encapsulating functions and variables and creating namespaces that you don’t want to leak to other scopes. A common pattern is to use an immediately self invoked function to encapsulate everything in the function’s scope and return an object containing the things you want to expose:

```text
const lib = (() => {
 const VERSION = '1.1';
 const last = (arr) => arr[arr.length - 1];
 const uniq = (v, i, self) => self.indexOf(v) === i;
 return {
 last, uniq,
 };
})();

const lastVal = lib.last([1,2,3,4]);
const uniqVals = [1,1,1,2,2,3].filter(lib.uniq);
```

You can imagine that the snippet above is part of a utility library. As you can see we are defining an immediately invoked arrow function `(() => {})()` and we are hiding the implementation of our library from the outside world, that is the global scope. In addition, we are deciding what we want to expose by returning an object and including only what we want to expose. Notice that we are only exposing the `last` and the `uniq` functions. This way we can only use what the library is deciding to expose and not have access to the internals of the library from outside.

It’s worth mentioning that you may not need this kind of code in the Node environment, since you can encapsulate your code using modules. Also, for the code that runs int he browser, you won’t need to manually hide implementations if you use module bundlers that allow you to create encapsulated modules. Nevertheless, it is a useful technique to know, especially in third-party or legacy code bases, where you want to make sure that your code won’t collide with other parts of the code base.

### Closures Inside Loops

A common mistake is to create functions inside classic for or while loops, without any block scoping:

```text
const myFns = [];
const arr = ['hello', 'world'];
for(var i = 0; i < arr.length; i++) {
 myFns[i] = function() {console.log(i)}
}
myFns[0](); // -> 2
myFns[1](); // -> 2
```

In the snippet above we are using a for loop and the `var` keyword to define the iteration index. When `var` is used, the declaration is hoisted to the closest function. Therefore, there is no block scoping when `var` is used. In addition, we are defining functions inside the loop but the problem is that the function will close over the variable `i` and in the loop the value will be last value of `i`. That's why when you run the defined functions, they will all log `2` because the loop goes from 0 to 2, but obviously stops at 2. There are several ways around this. The simplest solution is to use block scoping using the `let` keyword:

```text
const myFns = [];
const arr = ['hello', 'world'];
for(let i = 0; i < arr.length; i++) {
 myFns[i] = function() {console.log(i)}
}
myFns[0](); // -> 0
myFns[1](); // -> 1
```

In this case each iteration will get their own scope and the functions will be set with the correct value of `i`. You can also use the `forEach` method of arrays to create a scope for each iteration:

```text
const myFns = [];
const arr = ['hello', 'world'];
arr.forEach((v, i) => {
 myFns[i] = function() {console.log(i)}
})
myFns[0](); // -> 0
myFns[1](); // -> 1
```

Any of the above methods are correct, but if you are stuck with an old version of JavaScript, you can create an immediately invoked function to create a context for every iteration:

```text
const myFns = [];
const arr = ['hello', 'world'];
for(var i = 0; i < arr.length; i++) {
 (function(v) {
 myFns[v] = function() {console.log(v);}
 }(i));
}
myFns[0](); // -> 0
myFns[1](); // -> 1
```

Inside the for loop we are creating a self invoked function that takes the value of `i` in every iteration and provides it as `v` to the loop and we get the expected behavior. It's worth mentioning that this behavior is not just for for loops, it also applies to while loops:

```text
const myFns = [];
const arr = ['hello', 'world'];
var i = 0;
while(i < arr.length) {
 myFns[i] = function() {console.log(i);}
 i++
}
myFns[0](); //-> 2
myFns[1](); //-> 2
```

In this case we cannot simply use `let`, because it won't create the block scope that we need for each iteration. In this case we need to use a self-invoked function to handle the value of `i`:

```text
const myFns = [];
const arr = ['hello', 'world'];
var i = 0;
while(i < arr.length) {
 ((i) => {
 myFns[i] = function() {console.log(i);}
 })(i);
 i++;
}
myFns[0](); // -> 0
myFns[1](); // -> 1
```

In the snippet above, we create a self invoked arrow function to encapsulate the value of `i` in every iteration.

