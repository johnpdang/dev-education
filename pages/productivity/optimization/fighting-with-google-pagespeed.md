# Fighting with Google PageSpeed

{% embed url="https://dev.to/snowleo208/three-things-i-learn-after-fighting-with-google-pagespeed-3jk9" %}

Recently, I have a chance to maintain a landing page, which has a new design, but with loading performance issue and conversion drops a lot compared to the old page.

What I learn is these:

1. Optimize images \(compress / lazy load\)
2. Optimize CSS/JS loading \([critical path rendering](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/)\)
3. Code splitting

### 1. Optimize images

Image is the easiest thing to fix and is the primary factor of loading speed. It is important to use image compression like [TinyJPG](https://tinyjpg.com/) to compress images, minimize the page size and set image to progressive one.

To make image become progressive image, you can try this if you have Imagemagick on your computer:

```text
for i in ./*.jpg; do convert -strip -interlace Plane $i $i; done
```

Moreover, it is necessary to use **lazy load** to prevent loading unneeded image, which is out of screen.

### 2. Optimize CSS/JS loading

#### CSS

Pagespeed has a rule called ["Optimize CSS Delivery"](https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery), that means anything which does not included in first render \(i.e. out of screen\), it is blocking render speed.

To defer loading of out-of-screen CSS, we can use [snippet by Google](https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery) and put it at the end of body tag:

```text
<noscript id="deferred-styles">
      <link rel="stylesheet" type="text/css" href="<your-css-file>.css"/>
    </noscript>
    <script>
      var loadDeferredStyles = function() {
        var addStylesNode = document.getElementById("deferred-styles");
        var replacement = document.createElement("div");
        replacement.innerHTML = addStylesNode.textContent;
        document.body.appendChild(replacement)
        addStylesNode.parentElement.removeChild(addStylesNode);
      };
      var raf = window.requestAnimationFrame || window.mozRequestAnimationFrame ||
          window.webkitRequestAnimationFrame || window.msRequestAnimationFrame;
      if (raf) raf(function() { window.setTimeout(loadDeferredStyles, 0); });
      else window.addEventListener('load', loadDeferredStyles);
</script>
```

Moreover, we need to put critical CSS \(i.e. in viewport\) inline and inside `<head>`. For example:

```text
<head>
    <style>
      .blue{color:blue;}
    </style>
</head>
```

#### JavaScript

For JS, you can try to put `defer`, `async` or asynchronously inject script into webpage like this:

```text
const script = document.createElement('script');
script.src = "//example.com/widget.js";
document.getElementsByTagName('head')[0].appendChild(script);
```

For out-of-screen function, you can set the property to "defer" and **put it at the end of body**, which means it will load after whole page is rendered. For example:

```text

<!--preload js for important func-->
<link rel="preload" href="script.js" as="script"> 

<!--load after rendered-->
<script src="script.js" defer></script>

<!--will load asynchronously-->
<script src="script.js" async></script>

```

There are some tools which can help you to automatically add inline CSS, like [gulp-inline-source](https://www.npmjs.com/package/gulp-inline-source) for gulp or [critters](https://github.com/GoogleChromeLabs/critters) for webpack.

### 3. Code Splitting

If the script is not critical and harm your functionality in screen \(like fixed menu\), you can split them into few files and load them when needed. For webpack or React, you can use the "Code Splitting" function in [webpack](https://webpack.js.org/guides/code-splitting/).

For React, it is even easier to use the new [lazy](https://reactjs.org/blog/2018/10/23/react-v-16-6.html) or [react-loadable](https://github.com/jamiebuilds/react-loadable).

Remember to delete or trim unnecessary codes inside your page and serve minimized version to users!

#### Result

[![alt=&quot;Final Result in PageSpeed&quot;](https://res.cloudinary.com/practicaldev/image/fetch/s--2MP6HnGo--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/j4iefssblocnoun2spxg.jpg)](https://res.cloudinary.com/practicaldev/image/fetch/s--2MP6HnGo--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/j4iefssblocnoun2spxg.jpg)

That page finally get nearly 80 on mobile and nearly perfect in desktop version. It is not very perfect, as mobile's score is definitely have room of improvement.

Do you have any thoughts on this? Welcome to let me know your insights! :\)

