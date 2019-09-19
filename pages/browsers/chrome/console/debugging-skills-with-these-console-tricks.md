# Debugging Skills With These Console Tricks

{% embed url="https://medium.com/better-programming/boost-your-javascript-debugging-skills-with-these-console-tricks-ab984c70298a" %}

The cookie-cutter way of debugging JavaScript code is to simply output the results via the `console.log` method. While it works, it’s not the most optimal way of doing things. If there are better ways out there, why not explore them?![](https://miro.medium.com/max/60/1*qt_h2Zv7RpGy10diUIFYdQ.png?q=20)![](https://miro.medium.com/max/60/1*qt_h2Zv7RpGy10diUIFYdQ.png?q=20)“Hello from the console”

The `console` object provides access to the browser's debugging console. You can use the `console` object only if run your JavaScript code on the browser, i.e client-side code, not server-side code. How it works varies from browser to browser, but there is a de facto set of features that are typically provided. The best part of the debugging statements is they work with all libraries and frameworks since they’re baked inside the core language.

The most basic use case for the`console.log` is to show the output of the code. Take the following code:

It logs the name passed to the `sayHello` function.Outputting the name passed to the function

What if we want to know how many times we have to call the `sayHello` function? There’s an easy way for that. It’s called `console.count()`.

## `console.count`

`count()` outputs the number of times it has been called with that label. If there are no arguments, `count()` behaves as though it was called with the default label.

The above code logs the following:![](https://miro.medium.com/max/60/1*gKFq-qNc4H2vpe3pxeAj0g.png?q=20)![](https://miro.medium.com/max/60/1*gKFq-qNc4H2vpe3pxeAj0g.png?q=20)Counting the times we called the sayHello function

This gives us a count of how many times we called the function, but what if we want to count the times we call the function with the same name? The way to do that is to simply pass the `name` argument to the `count` method.

And voilà! The function keeps track of how many times we call the function with each name.Counting how many times we say each name

## console.warn

The following method outputs a warning message to the console. It’s useful when working with developer tools or APIs. `console.warn` is ideal for letting users know something might not be correct, such as omitting an argument or letting developers know the API/package version is deprecated.

The above code checks whether the name argument is passed to the function or not. If there’s no name passed, it logs a warning message prompting it to consider something.Show the user a warning message when no name is passed.

## console.table

If we’re working with arrays or objects, `console.table` is useful when it comes to displaying the data. Each element in the array will be a row in the table. Take the following example where we have an array of fruits. If we pass the fruits array to the `console.table` method, we should see a table printed to the console.

And if we take a glance at the console, we should see a table describing our array.Displaying our array in a tabular form

You can imagine how useful this becomes once we’re working with huger arrays with hundreds, if not thousands of values. To drive the point home here’s an example where we have more values inside the array.

And if we call `console.table` with the array, we should see the following table.![](https://miro.medium.com/max/60/1*YxnP_WIRvgM5-vhtHjcrFA.png?q=20)![](https://miro.medium.com/max/60/1*YxnP_WIRvgM5-vhtHjcrFA.png?q=20)Displaying all fruits in a table

Working with arrays is straightforward. What if we have objects instead?

Notice now we have an object instead of an array. The object holds two keys: the `name` and the`type` of the pet.

Instead of logging out the values like before, the table displays values and keys and values. What if we have one more object and try to table it?

As expected, the two separate objects shown in two different tables.Two objects

If we want to pair them in a single table, wrap the objects inside an array.

Now we’re grouping the objects in a single table.Grouping objects by wrapping them inside an array

When working with sets or linked-data, use nested groups to help organize your output by visually associating related messages. To create a new nested block, call `console.group()`.

The following code displays nested block-level console statements — useful when working relation-based data.

The `console.groupCollapsed()` method is similar, but the new block is collapsed and requires clicking a disclosure button to read it.

Use all the tools we’re given by the language. If it makes sense to use it, use it. A brief mention: We skipped the `debugger` for now since it deserves a full chapter by itself.

If you’re feeling curious about the `debugger`, [here’s the article](https://medium.com/@indreklasn/how-to-find-bugs-in-your-code-with-the-debugger-a7f739ea98).

If you’re new to JavaScript and want to learn the language, I recommend starting with reading books combined with building things. Start with the “[_A Smarter Way to Learn JavaScript_](https://amzn.to/2LOkzjj)” book and [here’s a list of fun apps to build](https://medium.com/better-programming/the-secret-to-being-a-top-developer-is-building-things-heres-a-list-of-fun-apps-to-build-aac61ac0736c).

Thanks for reading. Stay awesome.

