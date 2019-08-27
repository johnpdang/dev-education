# Scroll Snapping

{% embed url="https://alligator.io/css/scroll-snapping/" %}



Scroll snapping is a technique that you’ve certainly seen already. When implemented irresponsibly it can become extremely annoying and give a very bad browsing experience to the user. When done right though, it can be a great way to display things like image galleries. It used to be only achievable using JavaScript, but, thanks to the new [CSS Scroll Snap module](https://www.w3.org/TR/css-scroll-snap-1/), the effect can now be controlled using CSS.

The good news too is that browsers are still in control and can make a judgment call as to wether a snap point should be respected, given how the user is scrolling. This can help to avoid bad UX where snap points hinder a smooth navigation.

Let’s briefly go over how scroll snapping in CSS works.

**🐊 Alligator.io recommends ⤵**

[Advanced CSS and Sass: Flexbox, Grid, Animations and More!](https://click.linksynergy.com/deeplink?id=PHWysB*QB5k&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fadvanced-css-and-sass%2F)ⓘ [About this affiliate link](https://alligator.io/about-sponsored-or-affiliate/)

### The Big Picture <a id="the-big-picture"></a>

Similar to how [CSS grid](https://alligator.io/css/css-grid-layout-intro/) or [Flexbox](https://alligator.io/css/flexbox-primer/) work, scroll snapping is done by defining a parent/container element and children within the container that will snap according to rules defined on the container.

Some properties apply on the container element and some apply on the children.

### Container Element: scroll-snap-type <a id="container-element-scroll-snap-type"></a>

The most important property that applies to the container element is the `scroll-snap-type` property. It effectively makes the element into a snap container and defines the scroll snap axis \(`x`, `y`, `block`, `inline` or `both`\) as well as the scroll snap strictness \(`none`, `proximity` or `mandatory`\).

If, for example, you want a container that scrolls on the `y` axis and the snapping to happen no matter what, here’s how you’d apply `scroll-snap-type`:

```text
.container {
  scroll-snap-type: y mandatory;
}
```

Or, if you want scroll snapping in both directions and less strictness on the snapping itself:

```text
.container {
  scroll-snap-type: both proximity;
}
```

#### scroll-padding <a id="scroll-padding"></a>

Another property on the container is `scroll-padding` and it allows to set padding on the container to avoid having the snapping happen at the very edges of the container. The property expects values with the same syntax as the [`padding`property](https://alligator.io/css/padding-margin-shorthands/).

### Child Elements: scroll-snap-align <a id="child-elements-scroll-snap-align"></a>

When it comes to the elements within a scroll container, the `scroll-snap-align`is probably the most important property. It can take a value of either `none`, `start`, `end` or `center` and specifies where in the element the snapping will occur, at the start, the center or the end. Depending on the scroll axis, and assuming a left-to-right text direction, the start can either be the top or the left and then the end can either be the bottom or the right.

You’ll probably always want to set a value for the element’s `scroll-snap-align`because the initial value is `none`, meaning that no snapping will occur.

#### scroll-margin <a id="scroll-margin"></a>

Use `scroll-margin` the same with you’d use the `margin` property to set a different scroll snap area on the elements.

#### scroll-snap-stop <a id="scroll-snap-stop"></a>

The `scroll-snap-stop` property can take a value of either `normal` or `always` and specifies if an element should force a snapping point, even if the user’s scroll behavior would normally make the snapping be skipped. The initial value for that property is `normal`.

### Demos <a id="demos"></a>

Now that we’ve gone over the theory and the different properties, let’s demonstrate things with some simple demos. First, one where the scroll is on the y axis and the scroll strictness is set to `mandatory`. Here’s the markup:

```text
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

And here are the CSS rules:

```text
.container {
  scroll-snap-type: y mandatory;
  overflow-y: scroll;

  border: 2px solid var(--gs0);
  border-radius: 8px;
  height: 33vh;
}

.container div {
  scroll-snap-align: start;

  height: 33vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 4rem;
}
.container div:nth-child(1) {
  background: hotpink;
  color: white;
}
.container div:nth-child(2) {
  background: azure;
}
.container div:nth-child(3) {
  background: blanchedalmond;
}
.container div:nth-child(4) {
  background: lightcoral;
  color: white;
}
```

And the result looks like this:1234

Contrast that to instead setting a strictness of `proximity`, where snapping will only occur if scrolling stops within close range of a snap point:

```text
.container {
  /* ... */

  scroll-snap-type: y proximity;
  overflow-y: scroll;
}

/* ... */
```

1234

Finally, let’s have a look at how things can look like when scroll snapping happens on both scrolling axes. An image gallery would be a perfect use case for something like that. Here our container will also happen to be a grid container.

First, the markup:

```text
<div class="container2">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
  <div>7</div>
  <div>8</div>
  <div>9</div>
</div>
```

And now the styles:

```text
.container2 {
  display: grid;
  grid-template-columns: 100% 100% 100%;
  scroll-snap-type: both mandatory;
  overflow: scroll;

  border: 2px solid var(--gs0);
  border-radius: 8px;
  height: 33vh;
}


.container2 div {
  scroll-snap-align: start;

  height: 33vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 4rem;
}
.container2 div:nth-child(1) {
  background: hotpink;
  color: white;
}
.container2 div:nth-child(2) {
  background: azure;
}
.container2 div:nth-child(3) {
  background: blanchedalmond;
}
.container2 div:nth-child(4) {
  background: lightcoral;
  color: white;
}
.container2 div:nth-child(5) {
  background: rebeccapurple;
  color: white;

}

/* ...you get the point */
```

Which results in the following:123456789

