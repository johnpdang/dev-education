# jQuery to vanilla JavaScript

{% embed url="https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/" %}



jQuery is still a useful and pragmatic library, but chances are increasingly that you’re not dependent on using it in your projects to accomplish basic tasks like selecting elements, styling them, animating them, and fetching data—things that jQuery was great at. With broad browser support of ES6 \([over 96%](https://caniuse.com/#feat=es6) at the time of writing\), now is probably a good time to move away from jQuery.

I recently removed jQuery from this blog and found myself googling for some of the patterns over and over again. To spare you the time, I’ve compiled this practical reference guide with some of the most common jQuery patterns and their equivalents in JavaScript. We’ll cover how to move over to vanilla JavaScript from these concepts and functions:

[Selecting elements](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#selecting-elements)[Events](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#working-with-events)[.css\(\)](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#styling-elements)[Document ready](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#document-ready)[Classes](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#working-with-classes)[.ajax\(\)](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#network-requests-with-get-or-ajax)[Creating elements](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#creating-elements)[HTML & text](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#updating-the-dom)

### Selecting elements[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#selecting-elements](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#selecting-elements) <a id="selecting-elements"></a>

Selecting one or several DOM elements to do something with is one of the most basic elements of jQuery. The equivalent to `$()` or `jQuery()` in JavaScript is [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)or [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll), which, just like with jQuery, you can call with a CSS selector.

```text
// jQuery, select all instances of .box
$(".box");

// Instead, select the first instance of .box
document.querySelector(".box");

// …or select all instances of .box  
document.querySelectorAll(".box");
```

#### Running a function on all elements in a selection[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#running-a-function-on-all-elements-in-a-selection](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#running-a-function-on-all-elements-in-a-selection) <a id="running-a-function-on-all-elements-in-a-selection"></a>

`querySelectorAll()` returns, just like jQuery does, an array of elements that you can work with. But whereas you can run a function with jQuery on the entire selection simply by calling it on the jQuery object, you’ll have to loop over the array of elements with JavaScript:

```text
// with jQuery
// Hide all instances of .box
$(".box").hide();

// Without jQuery
// Loop over the array of elements to hide all instances of .box
document.querySelectorAll(".box").forEach(box => { box.style.display = "none" }
```

#### Finding one element within another[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#finding-one-element-within-another](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#finding-one-element-within-another) <a id="finding-one-element-within-another"></a>

A common jQuery pattern is to select an element within another element using `.find()`. You can achieve the same effect, scoping the selection to an element’s children, by calling `querySelector` or `querySelectorAll` on an element:

```text
// With jQuery
// Select the first instance of .box within .container
var container = $(".container");
// Later...
container.find(".box");

// Without jQuery
// Select the first instance of .box within .container
var container = document.querySelector(".container");
// Later...
container.querySelector(".box");
```

#### Traversing the tree with `parent()`, `next()`, and `prev()`[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#traversing-the-tree-with-parent-next-and-prev](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#traversing-the-tree-with-parent-next-and-prev) <a id="traversing-the-tree-with-parent-next-and-prev"></a>

If you wish to traverse the DOM to select a subling or a parent element relative to another element, you can access them through `nextElementSibling`, `previousElementSibling`and `parentElement` on that element:

```text
// with jQuery
// Return the next, previous, and parent element of .box
$(".box").next();
$(".box").prev();
$(".box").parent();

// Without jQuery
// Return the next, previous, and parent element of .box
var box = document.querySelector(".box");
box.nextElementSibling;
box.previousElementSibling;
box.parentElement;
```

### Working with events[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#working-with-events](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#working-with-events) <a id="working-with-events"></a>

There’s a myriad of ways to listen to events in jQuery, but whether you’re using `.on()`, `.bind()`, `.live` or `.click()`, you’ll make do with the JavaScript equivalent `.addEventListener`:

```text
// With jQuery
$(".button").click(function(e) { /* handle click event */ });
$(".button").mouseenter(function(e) {  /* handle click event */ });
$(document).keyup(function(e) {  /* handle key up event */  });

// Without jQuery
document.querySelector(".button").addEventListener("click", (e) => { /* ... */ });
document.querySelector(".button").addEventListener("mouseenter", (e) => { /* ... */ });
document.addEventListener("keyup", (e) => { /* ... */ });
```

#### Event listening for dynamically added elements[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#event-listening-for-dynamically-added-elements](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#event-listening-for-dynamically-added-elements) <a id="event-listening-for-dynamically-added-elements"></a>

jQuery’s `.on()` method enables you to work with “live” event handlers, where you listen to events on objects that get dynamically added to the DOM. To accomplish something similar without jQuery you can attach the event handler on an element as you add it to the DOM:

```text
// With jQuery
// Handle click events .search-result elements, 
// even when they're added to the DOM programmatically
$(".search-container").on("click", ".search-result", handleClick);

// Without jQuery
// Create and add an element to the DOM
var searchElement = document.createElement("div");
document.querySelector(".search-container").appendChild(searchElement);
// Add an event listener to the element
searchElement.addEventListener("click", handleClick);
```

#### Triggering and creating events[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#triggering-and-creating-events](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#triggering-and-creating-events) <a id="triggering-and-creating-events"></a>

The equivalent to manually triggering events with `trigger()` can be achieved by calling [`dispatchEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent). The `dispatchEvent()` method can be invoked on any element, and takes an `Event` as the first argument:

```text
// With jQuery
// Trigger myEvent on document and .box
$(document).trigger("myEvent");
$(".box").trigger("myEvent");

// Without jQuery
// Create and dispatch myEvent
document.dispatchEvent(new Event("myEvent"));
document.querySelector(".box").dispatchEvent(new Event("myEvent"));
```

### Styling elements[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#styling-elements](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#styling-elements) <a id="styling-elements"></a>

If you’re calling `.css()` on an element to change its inline CSS with jQuery, you’d use [`.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) in JavaScript and assign values to its different properties to achieve the same effect:

```text
// With jQuery
// Select .box and change text color to #000
$(".box").css("color", "#000");

// Without jQuery
// Select the first .box and change its text color to #000
document.querySelector(".box").style.color = "#000";
```

With jQuery, you can pass an object with key-value pairs to style many properties at once. In JavaScript you can set the values one at a time, or set the entire style string:

```text
// With jQuery
// Pass multiple styles
$(".box").css({
  "color": "#000",
  "background-color": "red"
});

// Without jQuery
// Set color to #000 and background to red
var box = document.querySelector(".box");
box.style.color = "#000";
box.style.backgroundColor = "red";

// Set all styles at once (and override any existing styles)
box.style.cssText = "color: #000; background-color: red";
```

#### `hide()` and `show()`[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#hide-and-show](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#hide-and-show) <a id="hide-and-show"></a>

The `.hide()` and `.show()` convenience methods are equivalent to accessing the `.style`property and setting `display` to `none` and `block`:

```text
// With jQuery
// Hide and show and element
$(".box").hide();
$(".box").show();

// Without jQuery
// Hide and show an element by changing "display" to block and none
document.querySelector(".box").style.display = "none";
document.querySelector(".box").style.display = "block";
```

### Document ready[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#document-ready](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#document-ready) <a id="document-ready"></a>

If you need to wait for the DOM to fully load before e.g. attaching events to objects in the DOM, you’d typically use `$(document).ready()` or the common short-hand `$()` in jQuery. We can easily construct a similar function to replace it with by listening to `DOMContentLoaded`:

```text
// With jQuery
$(document).ready(function() { 
  /* Do things after DOM has fully loaded */
});

// Without jQuery
// Define a convenience method and use it
var ready = (callback) => {
  if (document.readyState != "loading") callback();
  else document.addEventListener("DOMContentLoaded", callback);
}

ready(() => { 
  /* Do things after DOM has fully loaded */ 
});
```

### Working with classes[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#working-with-classes](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#working-with-classes) <a id="working-with-classes"></a>

You can easily access and work with classes through the [`classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) property to toggle, replace, add, and remove classes:

```text
// With jQuery
// Add, remove, and the toggle the "focus" class
$(".box").addClass("focus");
$(".box").removeClass("focus");
$(".box").toggleClass("focus");

// Without jQuery
// Add, remove, and the toggle the "focus" class
var box = document.querySelector(".box");
box.classList.add("focus");
box.classList.remove("focus");
box.classList.toggle("focus");
```

If you want to remove or add multiple classes you can just pass multiple arguments to `.add()` and `.remove()`:

```text
// Add "focus" and "highlighted" classes, and then remove them
var box = document.querySelector(".box");
box.classList.add("focus", "highlighted");
box.classList.remove("focus", "highlighted");
```

If you’re toggling two classes that are mutually exclusive, you can access the `classList`property and call `.replace()` to replace one class with another:

```text
// Remove the "focus" class and add "blurred"
document.querySelector(".box").classList.replace("focus", "blurred");
```

#### Checking if an element has a class[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#checking-if-an-element-has-a-class](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#checking-if-an-element-has-a-class) <a id="checking-if-an-element-has-a-class"></a>

If you only want to run a function depending on if an element has a certain class, you can replace jQuery’s `.hasClass()` with `.classList.contains()`:

```text
// With jQuery
// Check if .box has a class of "focus", and do something
if ($(".box").hasClass("focus")) {
  // Do something...
}

// Without jQuery
// Check if .box has a class of "focus", and do something
if (document.querySelector(".box").classList.contains("focus")) {
  // Do something...
}
```

### Network requests with .get\(\) or .ajax\(\)[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#network-requests-with-get-or-ajax](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#network-requests-with-get-or-ajax) <a id="network-requests-with-get-or-ajax"></a>

[`feth()`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) lets you create network requests in a similar fashion to jQuery’s `ajax()` and `get()`methods. `fetch()` takes a URL as an argument, and returns a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that you can use to handle the response:

```text
// With jQuery
$.ajax({
    url: "data.json"
  }).done(function(data) {
    // ...
  }).fail(function() {
    // Handle error
  });

// Without jQuery
fetch("data.json")
  .then(data => {
    // Handle data
  }).catch(error => {
    // Handle error
  });
```

### Creating elements[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#creating-elements](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#creating-elements) <a id="creating-elements"></a>

If you want to dynamically create an element in JavaScript to add to the DOM you can call [`createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) on `document` and pass it a tag name to indicate what element you want to create:

```text
// Create a div & span
$("<div/>");
$("<span/>");

// Create a div and a span
document.createElement("div");
document.createElement("span");
```

If you want to add some content to those elements, you can simply set the `textContent`property, or create a text node with [`createTextNode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode) and append it to the element:

```text
var element = document.createElement("div");
element.textContent = "Text"
// or create a textNode and append it
var text = document.createTextNode("Text");
element.appendChild(text);
```

### Updating the DOM[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#updating-the-dom](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#updating-the-dom) <a id="updating-the-dom"></a>

If you’re looking to change the text of an element or to add new elements to the DOM chances are that you’ve come across `innerHTML()`, but using it may expose you to cross-site scripting \(XSS\) attacks. [Although you can work around it and sanitize the HTML](https://gomakethings.com/preventing-cross-site-scripting-attacks-when-using-innerhtml-in-vanilla-javascript/), there are some safer alternatives.

If you’re only looking to read or update the text of an element, you can use the [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) property of an object to return the current text, or update it:

```text
// With jQuery
// Update the text of a .button
$(".button").text("New text");
// Read the text of a .button
$(".button").text(); // Returns "New text"

// Without jQuery
// Update the text of a .button
document.querySelector(".button").textContent = "New text";
// Read the text of a .button
document.querySelector(".button").textContent; // Returns "New text"
```

If you’re constructing a new element, you can then add that element to another element by using the method on the parent `appendChild()`:

```text
// Create div element and append it to .container
$(".container").append($("<div/>"));

// Create a div and append it to .container
var element = document.createElement("div");
document.querySelector(".container").appendChild(element);
```

Put together, here’s how to create a div, update its text and class, and add it to the DOM:

```text
// Create a div
var element = document.createElement("div");

// Update its class
element.classList.add("box");

// Set its text
element.textContent = "Text inside box";

// Append the element to .container
document.querySelector(".container").appendChild(element);
```

### In summary[\#https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/\#in-summary](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/?utm_medium=email&utm_source=topic+optin&utm_campaign=awareness&utm_content=20190828+web+nl&mkt_tok=eyJpIjoiWmpRM1l6QTJNekV3TURFMyIsInQiOiJRb1c5N0ZPQ2huWmVpV2xpaGJTNEdsWUtoajdZMlZHY1hTeURpSXhnZTV2a3l6cFZIdjlmZFlkb1llQ0hCc0hFRU1maXFuSzdLMEJvZjFla2hLeUhqVUd5cTZ6MWJGQ0JBT2pENXVGcmFza1pHVVwvZEJHOHRPZkh2REdhUTYyajYifQ%3D%3D#in-summary) <a id="in-summary"></a>

This is by no means a comprehensive guide to any of the native JavaScript methods utilized here, but I hope it’s been helpful a guide if you’re looking to move away from jQuery. In summary, here are the methods that we’ve covered:

* Selecting elements with [`querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) and [`querySelectorAll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
* Listening for events with [`addEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
* Updating CSS and styles through [`style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) property
* Working with classes through the [`classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) property
* AJAX requests with [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
* Triggering events with [`dispatchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent)
* Creating elements with [`createElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
* Updating text through the [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) property
* Adding elements to the DOM with [`appendChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)

