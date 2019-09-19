---
description: A Complete Guide to Flexbox
---

# Flexbox

{% embed url="https://css-tricks.com/snippets/css/a-guide-to-flexbox/" %}

Our comprehensive guide to CSS flexbox layout. This complete guide explains everything about flexbox, focusing on all the different possible properties for the parent element \(the flex container\) and the child elements \(the flex items\). It also includes history, demos, patterns, and a browser support chart.Monthly Sponsor

#### [Background](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-background)

#### [Basics & Terminology](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-basics)

![the flex container is the outer element which holds the flex items](https://css-tricks.com/wp-content/uploads/2018/10/01-container.svg)

### Properties for the Parent \(flex container\)

**display**

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```text
.container {
  display: flex; /* or inline-flex */
}
```

Note that CSS columns have no effect on a flex container.

**flex-direction**

![the four possible values of flex-direction being shown: top to bottom, bottom to top, right to left, and left to right](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)  
This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is \(aside from optional wrapping\) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```text
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

* `row` \(default\): left to right in `ltr`; right to left in `rtl`
* `row-reverse`: right to left in `ltr`; left to right in `rtl`
* `column`: same as `row` but top to bottom
* `column-reverse`: same as `row-reverse` but bottom to top

**flex-wrap**

![two rows of boxes, the first wrapping down onto the second](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

```text
.container{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

* `nowrap` \(default\): all flex items will be on one line
* `wrap`: flex items will wrap onto multiple lines, from top to bottom.
* `wrap-reverse`: flex items will wrap onto multiple lines from bottom to top.

There are some [visual demos of `flex-wrap` here](https://css-tricks.com/almanac/properties/f/flex-wrap/).

**flex-flow \(Applies to: parent flex container element\)**

This is a shorthand for the `flex-direction` and `flex-wrap`properties, which together define the flex container's main and cross axes. The default value is `row nowrap`.

```text
flex-flow: <‘flex-direction’> || <‘flex-wrap’>
```

**justify-content**

![flex items within a flex container demonstrating the different spacing options](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)  
This defines the alignment along the main axis. It helps distribute extra free space left over when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

```text
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

* `flex-start` \(default\): items are packed toward the start line
* `flex-end`: items are packed toward the end line
* `center`: items are centered along the line
* `space-between`: items are evenly distributed in the line; first item is on the start line, last item on the end line
* `space-around`: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren't equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
* `space-evenly`: items are distributed so that the spacing between any two items \(and the space to the edges\) is equal.

**align-items**

![demonstration of differnet alignment options, like all boxes stuck to the top of a flex parent, the bottom, stretched out, or along a baseline](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)  
This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the `justify-content` version for the cross-axis \(perpendicular to the main-axis\).

```text
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

* `stretch` \(default\): stretch to fill the container \(still respect min-width/max-width\)
* `flex-start`: cross-start margin edge of the items is placed on the cross-start line
* `flex-end`: cross-end margin edge of the items is placed on the cross-end line
* `center`: items are centered in the cross-axis
* `baseline`: items are aligned such as their baselines align

**align-content**

![examples of the align-content property where a group of items cluster at the top or bottom, or stretch out to fill the space, or have spacing.](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)  
This aligns a flex container's lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

**Note:** this property has no effect when there is only one line of flex items.

```text
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

* `flex-start`: lines packed to the start of the container
* `flex-end`: lines packed to the end of the container
* `center`: lines packed to the center of the container
* `space-between`: lines evenly distributed; the first line is at the start of the container while the last one is at the end
* `space-around`: lines evenly distributed with equal space around each line
* `stretch` \(default\): lines stretch to take up the remaining space

![flex items are the direct child elements of the flex parent](https://css-tricks.com/wp-content/uploads/2018/10/02-items.svg)

### Properties for the Children \(flex items\)

**order**

![Diagram showing flexbox order. A container with the items being 1 1 1 2 3, -1 1 2 5, and 2 2 99.](https://css-tricks.com/wp-content/uploads/2018/10/order.svg)  
By default, flex items are laid out in the source order. However, the `order` property controls the order in which they appear in the flex container.

```text
.item {
  order: <integer>; /* default is 0 */
}
```

**flex-grow**

![two rows of items, the first has all equally sized items with equal flex-grow numbers, the second with the center item at twice the width because it&apos;s value is 2 instead of 1.](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)  
This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have `flex-grow` set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others \(or it will try to, at least\).

```text
.item {
  flex-grow: <number>; /* default 0 */
}
```

Negative numbers are invalid.

**flex-shrink**

This defines the ability for a flex item to shrink if necessary.

```text
.item {
  flex-shrink: <number>; /* default 1 */
}
```

Negative numbers are invalid.

**flex-basis**

This defines the default size of an element before the remaining space is distributed. It can be a length \(e.g. 20%, 5rem, etc.\) or a keyword. The `auto` keyword means "look at my width or height property" \(which was temporarily done by the `main-size` keyword until deprecated\). The `content` keyword means "size it based on the item's content" - this keyword isn't well supported yet, so it's hard to test and harder to know what its brethren `max-content`, `min-content`, and `fit-content` do.

```text
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

If set to `0`, the extra space around content isn't factored in. If set to `auto`, the extra space is distributed based on its `flex-grow`value. [See this graphic.](http://www.w3.org/TR/css3-flexbox/images/rel-vs-abs-flex.svg)

**flex**

This is the shorthand for `flex-grow,` `flex-shrink` and `flex-basis` combined. The second and third parameters \(`flex-shrink` and `flex-basis`\) are optional. Default is `0 1 auto`.

```text
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

**It is recommended that you use this shorthand property** rather than set the individual properties. The short hand sets the other values intelligently.

**align-self**

![One item with a align-self value is positioned along the bottom of a flex parent instead of the top where all the rest of the items are.](https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg)  
This allows the default alignment \(or the one specified by `align-items`\) to be overridden for individual flex items.

Please see the `align-items` explanation to understand the available values.

```text
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

Note that `float`, `clear` and `vertical-align` have no effect on a flex item.

#### Examples <a id="flexbox-examples"></a>

Let's start with a very very simple example, solving an almost daily problem: perfect centering. It couldn't be any simpler if you use flexbox.

```text
.parent {
  display: flex;
  height: 300px; /* Or whatever */
}

.child {
  width: 100px;  /* Or whatever */
  height: 100px; /* Or whatever */
  margin: auto;  /* Magic! */
}
```

This relies on the fact a margin set to \`auto\` in a flex container absorb extra space. So setting a vertical margin of `auto` will make the item perfectly centered in both axis.

Now let's use some more properties. Consider a list of 6 items, all with a fixed dimensions in a matter of aesthetics but they could be auto-sized. We want them to be evenly and nicely distributed on the horizontal axis so that when we resize the browser, everything is fine \(without media queries!\).

```text
.flex-container {
  /* We first create a flex layout context */
  display: flex;
  
  /* Then we define the flow direction 
     and if we allow the items to wrap 
   * Remember this is the same as:
   * flex-direction: row;
   * flex-wrap: wrap;
   */
  flex-flow: row wrap;
  
  /* Then we define how is distributed the remaining space */
  justify-content: space-around;
}
```

Done. Everything else is just some styling concern. Below is a pen featuring this example. Be sure to go to CodePen and try resizing your windows to see what happens.

Let's try something else. Imagine we have a right-aligned navigation on the very top of our website, but we want it to be centered on medium-sized screens and single-columned on small devices. Easy enough.

```text
/* Large */
.navigation {
  display: flex;
  flex-flow: row wrap;
  /* This aligns items to the end line on main-axis */
  justify-content: flex-end;
}

/* Medium screens */
@media all and (max-width: 800px) {
  .navigation {
    /* When on medium sized screens, we center it by evenly distributing empty space around items */
    justify-content: space-around;
  }
}

/* Small screens */
@media all and (max-width: 500px) {
  .navigation {
    /* On small screens, we are no longer using row direction but column */
    flex-direction: column;
  }
}
```

Let's try something even better by playing with flex items flexibility! What about a mobile-first 3-columns layout with full-width header and footer. And independent from source order.

```text
.wrapper {
  display: flex;
  flex-flow: row wrap;
}

/* We tell all items to be 100% width, via flex-basis */
.wrapper > * {
  flex: 1 100%;
}

/* We rely on source order for mobile-first approach
 * in this case:
 * 1. header
 * 2. article
 * 3. aside 1
 * 4. aside 2
 * 5. footer
 */

/* Medium screens */
@media all and (min-width: 600px) {
  /* We tell both sidebars to share a row */
  .aside { flex: 1 auto; }
}

/* Large screens */
@media all and (min-width: 800px) {
  /* We invert order of first sidebar and main
   * And tell the main element to take twice as much width as the other two sidebars 
   */
  .main { flex: 2 0px; }
  .aside-1 { order: 1; }
  .main    { order: 2; }
  .aside-2 { order: 3; }
  .footer  { order: 4; }
}
```

#### [Prefixing Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-sass)

#### [Related Properties](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-related)

#### [Other Resources](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-resources)

#### [Bugs](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-bugs)

#### Browser Support <a id="browser-support"></a>

Broken up by "version" of flexbox:

* \(new\) means the recent syntax from the specification \(e.g. `display: flex;`\)
* \(tweener\) means an odd unofficial syntax from 2011 \(e.g. `display: flexbox;`\)
* \(old\) means the old syntax from 2009 \(e.g. `display: box;`\)

| Chrome | Safari | Firefox | Opera | IE | Edge | Android | iOS |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 20- \(old\) 21+ \(new\) | 3.1+ \(old\) 6.1+ \(new\) | 2-21 \(old\) 22+ \(new\) | 12.1+ \(new\) | 10 \(tweener\) 11+ \(new\) | 17+ \(new\) | 2.1+ \(old\) 4.4+ \(new\) | 3.2+ \(old\) 7.1+ \(new\) |

Blackberry browser 10+ supports the new syntax.

For more informations about how to mix syntaxes in order to get the best browser support, please refer to [this article \(CSS-Tricks\)](https://css-tricks.com/using-flexbox/) or [this article \(DevOpera\)](http://dev.opera.com/articles/view/advanced-cross-browser-flexbox/#fallbacks).

