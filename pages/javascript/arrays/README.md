# Arrays

{% embed url="https://codeburst.io/javascript-essentials-arrays-2d275b9598c5" %}

Essentials is a series that covers the most used and important methods for X topic. It’s a series for developers who know another language or someone who wants a quick start. In this post we cover Arrays.

## Table of Contents <a id="7f6e"></a>

— [**JavaScript Essentials: Arrays**](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Prerequisites](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— [**Array Basics**](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Array Creation](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Adding / Removing Basics](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— [**Common Methods**](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Modify Every Element in the Array](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Copy Without Mutating](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Find the Element\(s\)/Index](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Is this Element in the Array?](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [No Duplicates](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Does Every Item in the Array fulfill these Requirements?](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Do Some of the Items in the Array fulfill these Requirements?](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Populate an Array of Emptiness](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Wtf Sort?](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [How to Reverse a String?](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Flatten an Array](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Convert this Array into an Object](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Loopy Loops](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Multi-Dimensional Array Manipulation](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Get the Diagonal \( multi-dimension array \)](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— [**References**](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— [**More Links**](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)  
— — [Practice](https://codeburst.io/javascript-essentials-arrays-2d275b9598c5)

### Prerequisites <a id="74a0"></a>

It’s suggested that you know about Arrow Functions and Ternary expressions before reading. Everything else is just syntax really the focus is on the Array methods.[JavaScript: Arrow Functions for BeginnersLast week I published this post on the keyword this for beginners. One of the topics that wasn’t covered in that…codeburst.io](https://codeburst.io/javascript-arrow-functions-for-beginners-926947fc0cdc?source=post_page-----2d275b9598c5----------------------)[JavaScript: What is the ternary operator?Learn how to shorten your if statements into one line of code with the ternary operator and four practical examples.codeburst.io](https://codeburst.io/javascript-what-is-the-ternary-operator-c819af8a7f6c?source=post_page-----2d275b9598c5----------------------)

## Array Basics <a id="8764"></a>

You should know what Arrays are, but just in case here’s a quick overview. Arrays are like boxes that contain stuff inside them, you can remove items, add items or manipulate them. They’re like `lists` in Python or Arrays in most languages.

### Array Creation <a id="ee76"></a>

Here are a few ways to create Arrays.

![](https://miro.medium.com/max/60/1*alCLEgVdXkPDUIbIDYvmIA.png?q=20)![](https://miro.medium.com/max/2388/1*alCLEgVdXkPDUIbIDYvmIA.png)Array Creation

### Adding / Removing Basics <a id="93a8"></a>

![](https://miro.medium.com/max/60/1*DnIh6yKu3y_sJFgaO7oR_g.png?q=20)![](https://miro.medium.com/max/2692/1*DnIh6yKu3y_sJFgaO7oR_g.png)push pop shift splice

## Common Methods <a id="f0c0"></a>

An overview of common scenarios and the method to use for each scenario. You’ll notice most methods that take a callback function have the same parameters: `( element, index, array )`

Below are code blocks with a scenario/task described in a comment up top then some code below.

### Modify Every Element in the Array <a id="cb07"></a>

![](https://miro.medium.com/max/60/1*wqIDgU6hIxP8fG9tCuZjfQ.png?q=20)![](https://miro.medium.com/max/2252/1*wqIDgU6hIxP8fG9tCuZjfQ.png)Array.map

### Copy Without Mutating <a id="31a0"></a>

![](https://miro.medium.com/max/58/1*1BFvkG_cAjbosIvhuBOhJA.png?q=20)![](https://miro.medium.com/max/2452/1*1BFvkG_cAjbosIvhuBOhJA.png)slice, spread

### Find the Element\(s\)/Index <a id="63c9"></a>

![](https://miro.medium.com/max/60/1*NRyR-xpjtswywrdEEL54HA.png?q=20)![](https://miro.medium.com/max/2284/1*NRyR-xpjtswywrdEEL54HA.png)find, findIndex,

### Is this Element in the Array? <a id="4ad5"></a>

![](https://miro.medium.com/max/60/1*zta5YldScIwzt5z5Yx6sTw.png?q=20)![](https://miro.medium.com/max/2660/1*zta5YldScIwzt5z5Yx6sTw.png)includes

### No Duplicates <a id="3674"></a>

![](https://miro.medium.com/max/60/1*QpCsywLLVMg6kNTE-Yr_Mw.png?q=20)![](https://miro.medium.com/max/2524/1*QpCsywLLVMg6kNTE-Yr_Mw.png)unique sets

### Does Every Item in the Array fulfill these Requirements? <a id="827f"></a>

![](https://miro.medium.com/max/60/1*TkFaRF6PW02jbj6MkkKlFg.png?q=20)![](https://miro.medium.com/max/2556/1*TkFaRF6PW02jbj6MkkKlFg.png)Array.every

### Do Some of the Items in the Array fulfill these Requirements? <a id="0fe9"></a>

![](https://miro.medium.com/max/60/1*aUyKfs5Qe-DrCmY6D_6aiA.png?q=20)![](https://miro.medium.com/max/2388/1*aUyKfs5Qe-DrCmY6D_6aiA.png)Array.some

### Populate an Array of Emptiness <a id="bb75"></a>

![](https://miro.medium.com/max/60/1*dS5FUjoRpf4bqgyilUcgsg.png?q=20)![](https://miro.medium.com/max/2020/1*dS5FUjoRpf4bqgyilUcgsg.png)Array.fill

### Wtf Sort? <a id="c699"></a>

![](https://miro.medium.com/max/58/1*tYNjNzlLhUpsMd0CbLO1TQ.png?q=20)![](https://miro.medium.com/max/2420/1*tYNjNzlLhUpsMd0CbLO1TQ.png)Array.sort

### How to Reverse a String? <a id="1db6"></a>

![](https://miro.medium.com/max/60/1*PkB_boiSfT0PCp2FdhXAQg.png?q=20)![](https://miro.medium.com/max/2252/1*PkB_boiSfT0PCp2FdhXAQg.png)split, reverse, join

### Flatten an Array <a id="a070"></a>

![](https://miro.medium.com/max/60/1*T0HuwYTk9GDPtQeeszgw4A.png?q=20)![](https://miro.medium.com/max/2284/1*T0HuwYTk9GDPtQeeszgw4A.png)Experimental Array.flat

### Convert this Array into an Object <a id="41d6"></a>

![](https://miro.medium.com/max/60/1*5NiBAHCOZZjUqN1nMvLEsQ.png?q=20)![](https://miro.medium.com/max/3132/1*5NiBAHCOZZjUqN1nMvLEsQ.png)Array.reduce

### Loopy Loops <a id="98b8"></a>

![](https://miro.medium.com/max/50/1*BK2Kip6J5GT7_8Fqd2DWLA.png?q=20)![](https://miro.medium.com/max/1980/1*BK2Kip6J5GT7_8Fqd2DWLA.png)for in, for of, forEach, Array.entries

### Multi-Dimensional Array Manipulation <a id="4249"></a>

![](https://miro.medium.com/max/38/1*bY1irqhoXShNGQ4chwqmgg.png?q=20)![](https://miro.medium.com/max/1780/1*bY1irqhoXShNGQ4chwqmgg.png)Multi-Dimension Array Manipulation

### Get the Diagonal \( multi-dimension array \) <a id="29c4"></a>

![](https://miro.medium.com/max/58/1*__n6siUHXYjQxj1q47xGGA.png?q=20)![](https://miro.medium.com/max/2660/1*__n6siUHXYjQxj1q47xGGA.png)multi-dimension array, diagonal, reduce

## References <a id="2b0e"></a>

[ArrayThe JavaScript Array object is a global object that is used in the construction of arrays; which are high-level…developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array?source=post_page-----2d275b9598c5----------------------)[SetThe Set object lets you store unique values of any type, whether primitive values or object references.developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set?source=post_page-----2d275b9598c5----------------------)

## More Links <a id="9c34"></a>

More resources and cool things to check out.[JavaScript Array ExplorerEdit descriptionsdras.github.io](https://sdras.github.io/array-explorer/?source=post_page-----2d275b9598c5----------------------)[JavaScript EssentialsJavaScript Essentials started out as just a quick showcase of common methods and techniques to do certain things but it…medium.com](https://medium.com/@codedraken/javascript-essentials-cc600606bab0?source=post_page-----2d275b9598c5----------------------)

### Practice <a id="5455"></a>

Challenges on CodeWars \( easier ones are listed first up top \)[Sum of positiveCodewars is where developers achieve code mastery through challenge. Train on kata in the dojo and reach your highest…www.codewars.com](https://www.codewars.com/kata/sum-of-positive?source=post_page-----2d275b9598c5----------------------)[Remove the minimumCodewars is where developers achieve code mastery through challenge. Train on kata in the dojo and reach your highest…www.codewars.com](https://www.codewars.com/kata/remove-the-minimum?source=post_page-----2d275b9598c5----------------------)[Array.diffCodewars is where developers achieve code mastery through challenge. Train on kata in the dojo and reach your highest…www.codewars.com](https://www.codewars.com/kata/array-dot-diff?source=post_page-----2d275b9598c5----------------------)

Thanks for reading! Leave any feedback in the comments and let me know if there’s a better way to structure these posts \( updated to use Carbon instead of Medium code blocks \)[![](https://miro.medium.com/max/60/1*i3hPOj27LTt0ZPn5TQuhZg.png?q=20)](http://bit.ly/codeburst)  


