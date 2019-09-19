# Selectors in JS

{% embed url="https://dev.to/neutrino2211/using-css-selectors-in-javascript-3hlm" %}

## Using CSS Selectors In Javascript

[\#css](https://dev.to/t/css) [\#javascript](https://dev.to/t/javascript) [\#html](https://dev.to/t/html) [\#webdev](https://dev.to/t/webdev)

In CSS, selectors are patterns used to select the element\(s\) you want to style, but as you can tell from the title above, selectors are also useful in javascript and below are some examples on how to use them.

#### Basics

**Using a selector in javascript**

* Use the `.querySelector` method

```text
const div = document.querySelector("div") // => First occurence of a div element in the document

const p = div.querySelector("p") // => First occurence of a p element in the div

```

* To get all matching elements, use the `document.querySelectorAll` method

```text
document.querySelectorAll("div") // NodeList of all div elements
```

**By IDs**

To get an element by its ID, use a `#` before the element ID

```text
document.querySelector("#id") // => document.getElementById('id')
```

**By classes**

To get elements by class, use a `.` before the class name

```text
document.querySelectorAll(".myElementClass")
```

**By tag name**

To get elements by tag name, just input the tag name

```text
document.querySelectorAll("body") // => document.getElementsByTagName('body')
```

**Replicating .getElementById and getElementsByTagName**

* Replicating `.getElementById`

```text
document.querySelector("#myDivId") // => document.getElementById('myDivId')
```

* Replicating `.getElementsByTagName`

```text
document.querySelectorAll("a") // => document.getElementsByTagName('a')
```

**All elements**

To get all elements use `*`

```text
document.querySelectorAll("*") // => NodeList[...]
```

**Using multiple selectors**

To use multiple selectors, we seperate each of them with a `,`.

```text
<html>
    <body>
        <p>Hello i am a paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelectorAll("p, a") // => NodeList[p,a,a]
```

#### More with elements

In the above examples, we made basic queries, but other things can be done like getting elements by order or parent.

**Getting element children**

There are two variants of this, one gets an element's child no matter how deep it is down the tree, and the other gets an element's direct child.

```text
<html>
    <body>
        <p>Hello i am a paragraph</p>
        <div>
            <a href="https://awesomeplace.com">Hey I am a link</a>
            <p>
                Hello i am a paragraph and here's
                <a href="https://anotherplace.com">a link</a>
            </p>
        </div>
    </body>
</html>
```

With the above HTML as an example, we will look at these two variants.

* Direct child

```text
document.querySelector("div > a") // => <a href="https://awesomeplace.com">Hey I am a link</a>
```

* All children

```text
document.querySelectorAll("div a") // => NodeList[a,a]
```

**Getting elements by order**

There are two ways to do this also. Consider the following HTML.

```text
<html>
    <body>
        <div>
            <a href="https://awesomeplace.com">Hey I am a link</a>
            <pre>I should intervene but i wont</pre>
            <p>Hello i am another paragraph</p>
        </div>
        <p>Hello i am a paragraph</p>
    </body>
</html>
```

* Placed after

```text
document.querySelector("div + p") // => <p>Hello i am a paragraph</p>
```

* Preceded by

With `~`, it does not matter the element immediately behind matches.

```text
document.querySelector("a ~ p") // => <p>Hello i am another paragraph</p>
```

and we can see that the `pre` element did not affect the result because it does not matter if the `pre` was there in the first place. But the following selector will fail because it checks the element immediately above it.

```text
document.querySelector("a + p") // => null
```

#### Getting elements by attribute

An attribute selector starts with `[` and ends with `]` and is used as such

```text
<html>
    <body>
        <p style="color:blue;">Hello i am styled</p>
        <p>Hello i have no style</p>
    </body>
</html>
```

```text
document.querySelector("p[style]") // => <p style="color:blue;">Hello i am styled</p>
```

**Check attribute value**

To check an attribute value we use the `=` symbol.

```text
<html>
    <body>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelector('a[href="https://awesomeplace.com"]') // => <a href="https://awesomeplace.com">Hey I am a link</a>
```

**More with attribute values**

* Check if attribute starts with...

```text
document.querySelector('a[href^="https://awesome"]') // => <a href="https://awesomeplace.com">Hey I am a link</a>
```

* Check if attribute ends with...

```text
document.querySelectorAll('a[href$=".com"]') // => NodeList[a,a]
```

* Check if the attribute contains a substring

```text
document.querySelectorAll('a[href*="place"]') // => NodeList[a,a]
```

#### Advanced selectors

* :focus

This selects the element that currently has focus

* :visited

This is used with `a` tags and selects links that have been visited

* :link

This is also used with `a` tags but in this case, selects links that have not been visited

* :enabled

This selects elements that are enabled\(_not disabled_\)

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <p>I am another paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
        <button disabled="true"> I have been disabled </button>
    </body>
</html>
```

```text
document.querySelectorAll(":enabled") // => NodeList[p,p,a,a]
```

* :disabled

This selects elements that have been disabled

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <p>I am another paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
        <button disabled="true"> I have been disabled </button>
    </body>
</html>
```

```text
document.querySelector(":disabled") // => <button disabled="true"> I have been disabled </button>
```

* :first-child

This selects the element that is the first child of its parent

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <p>I am another paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelector("p:first-child") // => <p>I am a paragraph</p>
```

* :last-child

This selects the element that is the last child of its parent

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <p>I am another paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelector("p:last-child") // => <a href="anotherplace.com">I am another link</a>
```

* _el_:first-of-type

This selects the element that is the first child of its parent and is the same type as _el_

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <p>I am another paragraph</p>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelector("a:first-of-type") // => <a href="https://awesomeplace.com">Hey I am a link</a>
```

* _el_:last-of-type

This selects the element that is the last child of its parent and is the same type as _el_

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <p>I am another paragraph</p>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelector("p:last-of-type") // => <p>I am another paragraph</p>
```

* :not\(_selector_\)

This selects elements that don't match the selector

```text
<html>
    <body>
        <p>I am a paragraph</p>
        <a href="https://awesomeplace.com">Hey I am a link</a>
        <a href="https://anotherplace.com">I am another link</a>
    </body>
</html>
```

```text
document.querySelector(":not(a)") // => <p>I am a paragraph</p>
```

* :nth-child\(_n_\)

This selects the element that is the _n_ th child of its parent.

```text
<html>
    <body>
        <div>
            <p>I am a paragraph</p>
            <a href="https://awesomeplace.com">Hey I am a link</a>
            <a href="https://anotherplace.com">I am another link</a>
        </div>
    </body>
</html>
```

```text
document.querySelector("div:nth-child(2)") // => <a href="https://awesomeplace.com">Hey I am a link</a>
```

* :nth-last-child\(_n_\)

This selects the element that is the _n_ th to the last child of its parent.

```text
<html>
    <body>
        <div>
            <p>I am a paragraph</p>
            <a href="https://awesomeplace.com">Hey I am a link</a>
            <a href="https://anotherplace.com">I am another link</a>
        </div>
    </body>
</html>
```

```text
document.querySelector("div:nth-last-child(1)") // => <a href="https://anotherplace.com">I am another link</a>
```

#### Mix and match

These selectors can be mixed together to perform some complex checks. e.g

* A disabled button of class 'btn'

```text
<html>
    <body>
        <div>
            <p>I am a paragraph</p>
            <a href="https://awesomeplace.com">Hey I am a link</a>
            <a href="https://anotherplace.com">I am another link</a>
        </div>
        <button disabled="true">I am disabled</button>
        <button disabled="true" class="btn">I am also disabled</button>
    </body>
</html>
```

```text
document.querySelector('button.btn:disabled') // => <button disabled="true" class="btn">I am also disabled</button>
```

* All disabled buttons in a `form`

```text
<html>
    <body>
        <form method="POST">
            <input type="text" name="firstname" placeholder="firstname"/>
            <input type="text" name="lastname" placeholder="lastname"/>
            <button disabled="true">Clear inputs</button>
            <button type="submit">Submit</button>
        </form>
        <button disabled="true">I am disabled</button>
        <button disabled="true" class="btn">I am also disabled</button>
    </body>
</html>
```

```text
document.querySelector('form > button:disabled') // => <button disabled="true">Clear inputs</button>
```

* All disabled buttons in a `form` and all buttons outside it

```text
<html>
    <body>
        <form method="POST">
            <input type="text" name="firstname" placeholder="firstname"/>
            <input type="text" name="lastname" placeholder="lastname"/>
            <button disabled="true">Clear inputs</button>
            <button type="submit">Submit</button>
        </form>
        <button>I am not disabled</button>
        <button class="btn">I am also not disabled</button>
    </body>
</html>
```

```text
document.querySelectorAll('form > button:disabled, form ~ button') // => NodeList[button, button, button]
```

* All links to external pages

```text
<html>
    <body>
        <div>
            <p>I am a paragraph</p>
            <a href="https://awesomeplace.com">Hey I am a link</a>
            <a href="https://anotherplace.com">I am another link</a>
        </div>
        <a href="/otherpage.html">I will to the other pages</a>
    </body>
</html>
```

```text
document.querySelectorAll('a[href^="https://"]') // => NodeList[a,a]
```

And to get links that are not to external pages, use

```text
document.querySelector('a:not([href^="https://"])') // => <a href="/otherpage.html">I will to the other pages</a>
```

### Conclusion

These are just some of the ways you can use selectors in javascript and if you want to know more, here is a [link](https://www.w3schools.com/csSref/css_selectors.asp) to a CSS selector reference on w3c.

