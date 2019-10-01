# String

### .padEnd\(\)

{% embed url="https://medium.com/@samanthaming/padend-string-method-in-javascript-2e170d5b8bde" %}

### 

With `padEnd`, it adds characters to the end of a string so it reaches a specified length. This is great for us to add some padding to display our strings in a tabular format. Isn’t it so much easier to read, yay 🍹

```text
// ❌
'Day: Monday' + 'Drink: 🍵'
'Day: Saturday' + 'Drink: 🍹'// ✅
'Day: Monday'.padEnd(20) + 'Drink: 🍵'
'Day: Saturday'.padEnd(20) + 'Drink: 🍹'
```

The `padEnd` accepts 2 parameters:

```text
string.padEnd( <length>, <character>)
```

**1st Parameter: Length**

This is the final length of your result string. It is required.

Let’s say you begin with a string that has 3 characters. And you set the length to be 5 characters. That means, `padEnd` will pad it with 2 characters so the total length meets your target length of 5 characters.

Here’s an example. I’m denoting the space character with `·` to show you the padded space.

**2nd Parameter: Character**

This is an optional parameter. As you see from above, the default padded character is an empty space. However, you might want to pad it with a different character. No problem! Just pass it here.

So in my example of using `padEnd` to create table formatted string. One thing to note is that it only works with Monospace Font.

> _A monospaced font, also called a fixed-pitch, fixed-width, or non-proportional font, is a font whose letters and characters each occupy the same amount of horizontal space._

![](https://miro.medium.com/max/60/1*gCUuCDqxckWCZY06P2uXhA.jpeg?q=20)![](https://miro.medium.com/max/60/1*gCUuCDqxckWCZY06P2uXhA.jpeg?q=20)By Garethlwalt — Own work, CC BY 3.0, [https://commons.wikimedia.org/w/index.php?curid=9110833](https://commons.wikimedia.org/w/index.php?curid=9110833)

Fonts such as “Roboto” or “Monaco” are Monospace Font. Meaning each character will have the same width. Whereas fonts such as “Times New Roman” are not monospace. They are proportional, so each character will have different widths. And since each character has a different width, it would be hard to create the **Table** format using `padEnd`.

The purpose of string padding is to add characters to a string, so the outcome has a specific length.

`padEnd` adds characters at the end of the string. Whereas `padStart` adds characters at the start of the string

`padEnd`

`padStart`

**Watch out! — padding with Emojis**

If you’re padding with emojis, you might run into this issue.

Notice the last “👋” is not displayed. But instead “�” is shown. Well, that’s because emojis are typically made up of 2 characters.

```text
'👋'.length === 2 // true
```

So if you’re padding with emojis, just be mindful that the emoji might be cut off if you don’t provide it enough length.

* [_@2alin_](https://twitter.com/2alin/status/1150120894758621185)_:_ Just something to add: to have a tabular style use, the font should be mono-space and HTML render will remove any extra space; which makes such application important mainly in the information displayed in the terminal.

### .padStart\(\)

`padStart` adds characters at the start of the string

### .startsWith\(\)

{% embed url="https://medium.com/dailyjs/string-startswith-method-in-javascript-b12ec998eb54" %}

### String.prototype.length

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/length" %}

The **`length`** property of a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object indicates the length of a string, in UTF-16 code units.

