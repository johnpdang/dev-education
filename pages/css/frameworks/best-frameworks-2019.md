# Best frameworks 2019

{% embed url="https://www.creativebloq.com/features/best-css-frameworks" %}

### 01. Bootstrap  <a id="01-bootstrap-xa0"></a>

![best CSS frameworks: Bootstrap](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: Bootstrap\)

Let’s start with the most popular framework in the world. While Bootstrap is certainly not exclusively a CSS framework, its most popular features are the CSS-based ones. These include a powerful grid system, badges, buttons, card components, navbars and much more. There are also a whole load of [free Bootstrap themes](https://www.creativebloq.com/web-design/free-bootstrap-themes-21619376) to explore.

If you’re not familiar with how a framework like Bootstrap works, a few code examples will help, so you can see how easy it is to build maintainable interfaces by editing nothing but HTML.

Bootstrap’s grid system is a great place to start. The Bootstrap grid has been a valuable commodity since the framework’s first public release in 2011. And no wonder – it’s ridiculously easy to use. Once you’ve included Bootstrap’s CSS, creating a responsive flexbox-based grid that works in all browsers is as simple as this:

```text
<div class="container">
  <div class="row">
    <div class="col-sm">
      Column 1
    </div>
    <div class="col-sm">
      Column 2
    </div>
    <div class="col-sm">
      Column 3
    </div>
  </div>
</div>
```

As mentioned, Bootstrap also boasts a comprehensive collection of UI components. Some of those that have been difficult to style in the past are just plug-and-play with a framework like Bootstrap. These include a breadcrumb navigation component, a card component and a pagination component. Here’s the HTML to implement pagination:

```text
<nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

All of these components can be built without writing a single line of CSS. In many cases, you’ll likely theme the components to suit the project’s branding. Whatever the case, the mobile-friendly structure will already be in place, making it incredibly easy to reach a finished product in record time. [Bootstrap](https://getbootstrap.com/) also includes advanced features for responsive layouts, utility components and it’s built on Sass, so it’s super-flexible and customisable.

### 02. Foundation <a id="02-foundation"></a>

![best CSS frameworks: Foundation](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: Foundation\)

The Foundation framework, like Bootstrap, has become immensely popular and is known as a more sophisticated framework with some advanced but easy-to-implement CSS components. Foundation is built on Sass so, like Bootstrap, it’s customisable. In addition to that, it also boasts some powerful responsive features that mean making mobile-friendly designs is super-easy.

The responsive table component is one of our favourites:

```text
<table class="responsive-card-table unstriped">
  <!-- table rows code goes here... -->
</table>
```

Also, the vertical timeline is a layout feature you don’t see in many frameworks. This component uses the **.timeline** class for the container, which then holds multiple **.timeline-item** elements with an icon and content for each item:

```text
<div class="timeline">
  <div class="timeline-item">
    <div class="timeline-icon">
      <img src="image.svg" alt="Icon">
    </div>
    <div class="timeline-content">
      <p class="timeline-content-date">2019</h2>
      <p>Example text for timeline item.</p>
    </div>
  </div>
  <!-- More timeline items here ... -->
</div>
```

That’s just a small sampling of the many components that make [Foundation](http://foundation.zurb.com/) one of the best CSS frameworks available today.

### 03. UIkit  <a id="03-uikit-xa0"></a>

![best CSS frameworks: UIkit](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: UIkit\)

UIkit is another popular frontend framework and maybe a little under-appreciated in terms of CSS features. In addition to many features similar to those found in other popular frameworks, there are a few useful specialised components.

First of all, if you’re still not very comfortable with flexbox, you can do complex flexbox-based layouts with UIkit using plain HTML. It might seem strange at first to use flexbox syntax in your HTML classes but this saves you from having to know all the quirks about flex wrapping, columns/rows, flex grow and so forth. Here’s an example:

```text
<div class="uk-flex uk-flex-wrap uk-flex-wrap-around">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
  <div>Item 5</div>
  <div>Item 6</div>
</div>
```

UIkit includes dozens of components that offer attractive styles out-of-the-box. Many of the features are specialised utility classes, including the following:

* **.uk-align-left**, **.uk-align-right** and **.uk-align-center** for aligning or floating elements
* **.uk-column-1-2** up to **.uk-column-1-6** for multi-column, magazine-style text layouts
* **.uk-radio**, **.uk-checkbox** and similar for attractive form inputs
* Various margin and padding utility classes \(**.uk-margin-top**, **.uk-padding-small** etc.\)
* Various utility classes to relatively position an element inside a container \(**.uk-position-top**, **.uk-position-left** etc.\)

[UIkit](https://getuikit.com/) is worth a try if you want a fresh, well-maintained CSS framework with a slew of component options. It’s available in Less and Sass and even includes a stylesheet to cater for right-to-left languages.

### 04. Semantic UI  <a id="04-semantic-ui-xa0"></a>

![best CSS frameworks: Semantic UI ](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: Semantic UI\)

Semantic UI has a lot of feature overlaps with other popular frameworks but the way it works \(implied by the name\) is based on the semantic nature of the class names that are used to build components. In other words, the class names are human friendly.

Take a look, for example, at how you would build a four-column grid:

```text
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

Notice the way the class names communicate exactly what’s built. The CSS doesn’t necessarily have a unique set of styles for each of the classes listed but instead the classes work together. Thus, much like language where words make sense in context, the class names work together to build cohesive, mobile-friendly components.

Here’s another example, which builds a simple data table:

```text
<table class="ui celled table">
  <!-- ... rest of the table code here... -->
</table>
```

This is a great demonstration of how [Semantic UI](https://semantic-ui.com/) uses class names to describe the component being built. If you’re more accustomed to traditional frameworks like Bootstrap or Foundation, the learning curve on this one might be steeper. But once you get the hang of it, it’s pretty powerful and enjoyable to use.

### 05. Bulma  <a id="05-bulma-xa0"></a>

![best CSS frameworks: Bulma](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: Bulma\)

Bulma is another popular CSS framework and its primary feature is the fact that its components are largely dependent on flexbox, making it a truly modern framework. You can think of Bulma is being somewhat like a hybrid of Bootstrap and Semantic UI but without any of the complexity. It uses some of the same principles as Semantic UI with its class names, includes many of the popular components, yet manages to keep things simple – for example, form elements have little to no styles to maintain a cross-browser look. 

The following example demonstrates how a Bulma component can be built and is easy to maintain:

```text
<section class="hero is-dark">
  <div class="hero-body">
    <div class="container is-fluid">
      <h1 class="title is-size-2">Example Heading</h1>
      <h2 class="subtitle">Example text goes here</h2>
      <p>Some example paragraph text here.</p>
    </div>
  </div>
</section>
```

Notice the containing **&lt;section&gt;** element is given the hero and **is-dark** classes. This indicates you want a hero banner that uses the default dark theme \(one of seven theme colours included with Bulma, all of which can be changed via Sass variables\).

Also, notice the **is-\*** classes on the container and primary heading. The **is-fluid** class enables the container to be fluid on any size screen, centred with margins and with no **max-width**. Without this value, the **max-width** of the container changes depending on the size of the viewport. The **is-size-2** class defines the size of the heading, with sizes ranging from 1 to 7.

As you can see, [Bulma](https://bulma.io/) makes it incredibly easy to build mobile-friendly interfaces via readable class names.

### 06. Tailwind <a id="06-tailwind"></a>

![best CSS frameworks: Tailwind](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: Tailwind\)

Many modern CSS frameworks are taking advantage of a recent trend in building user interfaces: the use of single-purpose utility classes also known as Atomic CSS \(see the accompanying box\). Tailwind is one such framework. The idea behind Tailwind is that instead of starting out with pre-styled cookie-cutter components, you build everything from the ground up using utility classes.

The learning curve is definitely higher on this one, especially if Atomic CSS is new to you. But with Tailwind, specificity issues and other override problems common in large stylesheets are avoided.

As an example, Tailwind doesn’t include any kind of ‘button’ component. But you can build your own button using something like the following:

```text
<button class="bg-blue-500 text-white font-bold py-2 px-4 rounded">
  Button
</button>
```

From there, if you decide what you've created is a valid component for reuse, you can do that by means of Tailwind's component extraction feature. So a component like the button shown in the previous code block can be included like this:

```text
<button class="btn btn-blue">
  Button
</button>
<style>
  .btn {
    @apply font-bold py-2 px-4 rounded;
  }
  .btn-blue {
    @apply bg-blue-500 text-white;
  }
</style>
```

As you can see, the learning curve for [Tailwind](https://tailwindcss.com/) is pretty high. Not only do you have to get accustomed to the utility-first styles but it’s also recommended to use component extraction, done using Tailwind’s **@apply** directive – which is just one way to do extraction; see its [documentation](https://tailwindcss.com/docs/extracting-components) for more.

### 07. Picnic CSS <a id="07-picnic-css"></a>

![best CSS frameworks: Picnic CSS](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: Picnic CSS\)

If you don’t like the idea of including presentational classes in your markup, which is common in most, if not all, of the popular frameworks, then Picnic CSS might be the framework for you. Picnic is in many ways the opposite of Tailwind in that it’s not only less complex but very opinionated.

For example, some HTML elements are pre-styled with no need to add class names. These include **&lt;button&gt;**, **&lt;button disabled&gt;**, **&lt;table&gt;**, **&lt;input type="checkbox"&gt;** and **&lt;input type="radio"&gt;** \(the latter two of which also have a nice little animated check/uncheck actions\).

In addition to a number of existing default styles on many HTML elements, [Picnic](https://picnicss.com/) has some other nicely designed interactive pure-CSS components that don’t require any JavaScript. These include a modal dialog, a tab switcher, a file uploader and a tooltip. Some of these can be enhanced with scripting but they’re all functional with just CSS.

### 08. PaperCSS <a id="08-papercss"></a>

![best CSS frameworks: PaperCSS](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: PaperCSS\)

We're getting into the more speciality options in our list of the best CSS frameworks here. This won’t be your go-to CSS tool but it’s one of the quirkiest frameworks out there. PaperCSS is billed as the “less formal CSS framework". The components have a hand-drawn, cartoon-like appearance. Use cases might include a website for kids, a blog, a game or a comic strip.

[PaperCSS](https://www.getpapercss.com/) includes a flexbox grid, badges, buttons, cards and some interactive pure CSS components. The accompanying image gives you a taste of what this unique framework produces.

### 09. NES.css  <a id="09-nes-css-xa0"></a>

![best CSS frameworks: NES.css](https://vanilla.futurecdn.net/creativebloq/media/img/missing-image.svg)\(Image credit: NES.css\)

Like PaperCSS, NES.css has a unique set of styles suitable for only a narrow set of projects. It mimics the 8-bit Nintendo Entertainment System graphics, creating a retro gaming look.

In addition to common components found in other frameworks, [NES.css](https://nostalgic-css.github.io/NES.css/) also includes styles for comment balloons, reaction icons, plus unique containers with borders. Below is the code for a couple of comment balloons. The accompanying image shows how they look along with a couple of the many icons \(built via CSS shadows\) that are bundled with the framework.

```text
<div class="nes-balloon from-left">
  <p>Comment Balloon Example</p>
</div>
<div class="nes-balloon from-right">
  <p>Another comment balloon example with a little more text.</p>
</div>
```

If you like this, check out [PSone.css](https://micah5.github.io/PSone.css/).

### 10. Animate.css <a id="10-animate-css"></a>

