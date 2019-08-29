---
description: >-
  It was always complicated to flatten an array in JS. Not anymore! ES2019
  introduced a new method that flattens arrays with Array.flat()
---

# Flatten Array

{% embed url="https://medium.com/dailyjs/flatten-array-using-array-flat-in-javascript-ee4d0b2423e5" %}



It was always complicated to flatten an array in \#JavaScript. Not anymore! ES2019 introduced a new method that flattens arrays. And there’s a “depth” parameter, so you can pass in ANY levels of nesting. AMAZING 🤩

```text
console.log(flattened);
// ['📦', '📦', '📦']
```

Here’s the syntax for this method:

```text
array.flat(<depth>);
```

By default, `flat()` will only flatten one layer deep. In other words, `depth` is `1`.

The great thing is that this method also works beyond 1 level deep. You simply have to set the appropriate `depth` parameter to flatten deeper nested arrays.

```text
// depth = 1
twoLevelsDeep.flat()
// [1, [2, 2], 1]// depth = 2
twoLevelsDeep.flat()
// [1, 2, 2, 1]
```

Let’s say, you want to go infinitely deep. Not a problem, we can do that too. Just pass `Infinity`.

```text
veryDeep.flat(Infinity);
// [1, 2, 2, 3, 4, 5, 6, 1]
```

One other cool thing that `flat()` can do is remove empty slots in an array.

```text
missingNumbers.flat();
// [1, 3, 5];
```

`flat` is a super new feature introduced in ES2019, so forget Internet Explorer or Edge. But no surprise there 😅

Since support is not great. Here are some alternative solutions.

### ES6 Solution

Here is a ES6 solution. This only work for one level nested array.

```text
const flattened = [].concat(...oneLevelDeep);
// [1, 2, 3,]
```

### Older Browser Solution

Here’s one for older browser and pre ES6. Again, this only works for one level nested array.

```text
const flattened = [].concat.apply([], oneLevelDeep);
// [1, 2, 3,]
```

For arrays with deeper nesting, you can use recursion. Here’s the solution from [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat#Alternative):

```text
function flattenDeep(arr1) {
 return arr1.reduce((acc, val) => Array.isArray(val) ? acc.concat(flattenDeep(val)) : acc.concat(val), []);
}
flattenDeep(arr1);// [1, 2, 3, 1, 2, 3, 4, 2, 3, 4]
```

💬 Got any interesting use cases of Array.flat\(\)?

* [_@hocine\_abdellatif_](https://www.instagram.com/hocine_abdellatif/)_:_ A little far use case but probably worth mentioning, in machine learning if you have for example an array of generations, each generation is an array of students, if you want to have every student from every generation,this method will be very practical.
* [_@devjacks_](https://twitter.com/devjacks/status/1155273208595021825?s=20)_:_ I wrote a code test with a problem like this a few weeks ago. This would have made my life so much easier! 😂

```text
const haystack =[1, 4, [5,6,7, [8, 18, [34,177,[98,[210,[213]]]]]]];
const needle = 213;
```

