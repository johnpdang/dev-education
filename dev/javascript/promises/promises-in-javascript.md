# Promises in JavaScript

{% embed url="https://gomakethings.com/promises-in-javascript/" %}

## Promises in JavaScript

I’m super late to the party here, but I get enough requests for an article about JavaScript Promises that I figured it’s probably time I write one.

So, what’s the fuss about?

### An introduction to JavaScript Promises [\#](https://gomakethings.com/promises-in-javascript/#an-introduction-to-javascript-promises) <a id="an-introduction-to-javascript-promises"></a>

A Promise is a JavaScript object \([everything is an object in JS](https://gomakethings.com/everything-is-an-object-in-javascript/)\) that _represents_ an asynchronous function.

```text
// Create a Promise object
var sayHello = new Promise(function (resolve, reject) {

	// In 5 seconds, resolve the Promise.
	// Pass along "Hi, universe!" to any callback methods
	setTimeout(function () {
		resolve('Hi, universe!');
	}, 5000);

});
```

In the example above, `sayHello()` is a _Promise_ that in 5 seconds, something will happen. You can attach functions that should run when the Promise resolves using the `.then()` method.

```text
// After 5 seconds, if the Promise resolves,
// this will log "Hi, universe!" into the console
sayHello.then(function (msg) {
	console.log(msg);
});
```

[Here’s a demo on CodePen.](https://codepen.io/cferdinandi/pen/ExYQBdJ)

When you create a Promise, you pass in a callback function as an argument.

Inside the function, you pass in two arguments: `resolve` and `reject`. When the Promise’s should be considered completed, run the `resolve()` method. You can pass in arguments that should get passed into the `.then()` method callback function into the `resolve()` method.

In the example above, we passed `Hi, universe!` into `resolve()`. This was passed along to the `.then()` method as the `msg` argument.

### Rejecting a Promise [\#](https://gomakethings.com/promises-in-javascript/#rejecting-a-promise) <a id="rejecting-a-promise"></a>

Similarly, run the `reject()` method if the Promise should be considered failed.

You can pass in any error messages or information about the rejection as arguments. You can run a callback when a Promise fails using the `catch()` method.

In the example above, let’s modify `sayHello()` to `reject()` before the timeout completes.

```text
// Create a Promise object
var sayHello = new Promise(function (resolve, reject) {

	reject('Unable to say hi.');

	// In 5 seconds, resolve the Promise.
	// Pass along "Hi, universe!" to any callback methods
	setTimeout(function () {
		resolve('Hi, universe!');
	}, 5000);

});
```

Now, we can add a `catch()` method to detect this failure and do something about it.

```text
// Will warn "Unable to say hi." in the console.
sayHello.then(function (msg) {
	console.log(msg);
}).catch(function (err) {
	console.warn(err);
});
```

Because `reject()` runs before `resolve()` does, the `catch()` callback method will run and show the error message that was passed in.

[Here’s another demo on CodePen.](https://codepen.io/cferdinandi/pen/mdbXZQr)

### Chaining [\#](https://gomakethings.com/promises-in-javascript/#chaining) <a id="chaining"></a>

You can chain multiple `.then()` methods together, and they’ll run in sequence.

Whatever you `return` from the current `.then()` method gets passed along to the `.then()` method after it. Let’s create a new Promise called `count`.

It will `resolve()` immediately, and pass along `1` as an argument.

```text
// Create a Promise object
var count = new Promise(function (resolve, reject) {
	resolve(1);
});
```

Now, we can chain some `.then()` methods together. In each one one, we’ll log `num`, increase it by `1`, and `return` it to the next argument in the sequence.

In the first `.then()` method, `num` is `1`. In the second, it’s `2`. In the last one, it’s `3`.

```text
// logs 1, then 2, then 3, to the console
count.then(function (num) {
	console.log(num);
	return num + 1;
}).then(function (num) {
	console.log(num);
	return num + 1;
}).then(function (num) {
	console.log(num);
	return num + 1;
});
```

[Here’s a demo of chaining with Promises.](https://codepen.io/cferdinandi/pen/MWgQMzq)

#### Chaining multiple Promises [\#](https://gomakethings.com/promises-in-javascript/#chaining-multiple-promises) <a id="chaining-multiple-promises"></a>

You can also return another Promise.

The next `.then()` method will only run after it resolves. If you have a `catch()` method, it will run for any Promises in the chain.

Let’s say you have a helper function called `getTheAnswer()` that creates a new Promise for you when it’s run.

You can pass in a boolean \(`true`/`false`\) argument about whether or not to `reveal` the answer. The Promise will `resolve()` if it’s `true`, and `reject()` if it’s not.

```text
// Return a new Promise
var getTheAnswer = function (reveal) {
	return new Promise(function (resolve, reject) {
		if (reveal) {
			resolve(42);
		} else {
			reject('You are not ready yet.');
		}
	});
};
```

We’ll use it to create a new Promise, and add `.then()` and `catch()` callback methods to log what happens.

```text
// Will log 42 to the console because the Promise should resolve
getTheAnswer(true).then(function (answer) {
	console.log(answer);
}).catch(function (err) {
	console.warn(err);
});
```

Now, let’s chain a bunch of `.then()` methods together.

In each one, we’ll return a new `getTheAnswer()` Promise. For some, we’ll pass in `true`, and other’s we won’t.

```text
// logs 42, 42, 42
// then warns "You are not ready yet"
getTheAnswer(true).then(function (answer) {
	console.log(answer);
	return getTheAnswer(true);
}).then(function (answer) {
	console.log(answer);
	return getTheAnswer(true);
}).then(function (answer) {
	console.log(answer);
	return getTheAnswer(false);
}).then(function (answer) {
	console.log(answer);
	return getTheAnswer(true);
}).then(function (answer) {
	console.log(answer);
	return getTheAnswer(true);
}).catch(function (err) {
	console.warn(err);
});
```

The `.catch()` callback at the end of the chain catches the `reject()` from the Promise in the third `.then()` method, and the rest of the chain stops running.

[Here’s a demo of chaining with multiple promises.](https://codepen.io/cferdinandi/pen/rNBJEoP)

### You can attach `then()` methods at any time [\#](https://gomakethings.com/promises-in-javascript/#you-can-attach-then-methods-at-any-time) <a id="you-can-attach-then-methods-at-any-time"></a>

One of my favorite thing about Promises is that if you cache them to a variable, you can attach `.then()` callbacks on them at any time—even _after_ the Promise has already resolved.

If the Promise _hasn’t_ resolved yet, the callback will run once it does. If it _has resolved_, the callback will run immediately.

```text
// This will resolve immediately
var question = getTheAnswer(true);

// This will run 5 seconds later
setTimeout(function () {

	// This will run as soon a the timeout completes, because the Promise has already resolved
	question.then(function (answer) {
		console.log(answer);
	});

}, 5000);
```

[Here’s a demo of attaching a callback after the Promise has resolved.](https://codepen.io/cferdinandi/pen/mdbXZoO)

### Browser Compatibility [\#](https://gomakethings.com/promises-in-javascript/#browser-compatibility) <a id="browser-compatibility"></a>

Promises were introduced in ES6.

They work in all modern browsers, including Edge, but not IE. They also work in newer mobile browsers, but not older ones. They came to iOS with Safari 8, for example.

They can polyfilled, though. I’d recommend either [the es6-polyfill from Stefan Penner](https://github.com/stefanpenner/es6-promise), or [polyfill.io](https://polyfill.io/), which includes it by default for browsers that don’t support it.

