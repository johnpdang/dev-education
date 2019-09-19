# Slick slider

{% embed url="http://kenwheeler.github.io/slick/" %}

### Features

* Fully responsive. Scales with its container.
* Separate settings per breakpoint
* Uses CSS3 when available. Fully functional when not.
* Swipe enabled. Or disabled, if you prefer.
* Desktop mouse dragging
* Infinite looping.
* Fully accessible with arrow key navigation
* Add, remove, filter & unfilter slides
* Autoplay, dots, arrows, callbacks, etc...

### Single Item

Previous

#### 6

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 1

Next

* 1
* 2
* 3
* 4
* 5
* 6

```text

$('.single-item').slick();
```

### Multiple Items

Previous

#### 7

#### 8

#### 9

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 7

#### 8

#### 9

#### 1

#### 2

#### 3

Next

* 1
* 2
* 3

```text

$('.multiple-items').slick({
  infinite: true,
  slidesToShow: 3,
  slidesToScroll: 3
});
```

### Responsive Display

Previous

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 7

#### 8

Next

* 1
* 2

```text

$('.responsive').slick({
  dots: true,
  infinite: false,
  speed: 300,
  slidesToShow: 4,
  slidesToScroll: 4,
  responsive: [
    {
      breakpoint: 1024,
      settings: {
        slidesToShow: 3,
        slidesToScroll: 3,
        infinite: true,
        dots: true
      }
    },
    {
      breakpoint: 600,
      settings: {
        slidesToShow: 2,
        slidesToScroll: 2
      }
    },
    {
      breakpoint: 480,
      settings: {
        slidesToShow: 1,
        slidesToScroll: 1
      }
    }
    // You can unslick at a given breakpoint now by adding:
    // settings: "unslick"
    // instead of a settings object
  ]
});
```

### Variable Width

Previous

225

125

200

175

150

300

225

125

200

175Next

* 1
* 2
* 3
* 4
* 5
* 6

```text

$('.variable-width').slick({
  dots: true,
  infinite: true,
  speed: 300,
  slidesToShow: 1,
  centerMode: true,
  variableWidth: true
});
```

### Adaptive Height

Previous

#### 4

Woo!

#### 1

#### 2

Look ma!

#### 3

Check  
this out!

#### 4

Woo!

#### 1

Next

* 1
* 2
* 3
* 4

```text

$('.one-time').slick({
  dots: true,
  infinite: true,
  speed: 300,
  slidesToShow: 1,
  adaptiveHeight: true
});
```

### Data Attribute Settings

In slick 1.5 you can now add settings using the data-slick attribute. You still need to call $\(element\).slick\(\) to initialize slick on the element.Previous

#### 3

#### 4

#### 5

#### 6

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 1

#### 2

#### 3

#### 4

Next

```text

<div data-slick='{"slidesToShow": 4, "slidesToScroll": 4}'>
  <div><h3>1</h3></div>
  <div><h3>2</h3></div>
  <div><h3>3</h3></div>
  <div><h3>4</h3></div>
  <div><h3>5</h3></div>
  <div><h3>6</h3></div>
</div>
```

### Center Mode

Previous

#### 3

#### 4

#### 5

#### 6

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 1

#### 2

#### 3

#### 4

Next

```text

$('.center').slick({
  centerMode: true,
  centerPadding: '60px',
  slidesToShow: 3,
  responsive: [
    {
      breakpoint: 768,
      settings: {
        arrows: false,
        centerMode: true,
        centerPadding: '40px',
        slidesToShow: 3
      }
    },
    {
      breakpoint: 480,
      settings: {
        arrows: false,
        centerMode: true,
        centerPadding: '40px',
        slidesToShow: 1
      }
    }
  ]
});
```

### Lazy Loading

Previous![](http://kenwheeler.github.io/slick/img/lazyfonz1.png)![](http://kenwheeler.github.io/slick/img/lazyfonz2.png)![](http://kenwheeler.github.io/slick/img/lazyfonz3.png)![](http://kenwheeler.github.io/slick/img/lazyfonz1.png)![](http://kenwheeler.github.io/slick/img/lazyfonz2.png)![](http://kenwheeler.github.io/slick/img/lazyfonz3.png)Next

```text

// To use lazy loading, set a data-lazy attribute
// on your img tags and leave off the src

<img data-lazy="img/lazyfonz1.png"/>

$('.lazy').slick({
  lazyLoad: 'ondemand',
  slidesToShow: 3,
  slidesToScroll: 1
});
```

### Autoplay

Previous

#### 4

#### 5

#### 6

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 1

#### 2

#### 3

Next

* 1
* 2
* 3
* 4
* 5
* 6

```text

$('.autoplay').slick({
  slidesToShow: 3,
  slidesToScroll: 1,
  autoplay: true,
  autoplaySpeed: 2000,
});
```

### Fade

Previous![](http://kenwheeler.github.io/slick/img/fonz1.png)![](http://kenwheeler.github.io/slick/img/fonz2.png)![](http://kenwheeler.github.io/slick/img/fonz3.png)Next

* 1
* 2
* 3

```text

$('.fade').slick({
  dots: true,
  infinite: true,
  speed: 500,
  fade: true,
  cssEase: 'linear'
});
```

### Add & Remove

#### 1

[Add Slide](javascript:void%280%29)[Remove Slide](javascript:void%280%29)

```text

$('.add-remove').slick({
  slidesToShow: 3,
  slidesToScroll: 3
});
$('.js-add-slide').on('click', function() {
  slideIndex++;
  $('.add-remove').slick('slickAdd','<div><h3>' + slideIndex + '</h3></div>');
});

$('.js-remove-slide').on('click', function() {
  $('.add-remove').slick('slickRemove',slideIndex - 1);
  if (slideIndex !== 0){
    slideIndex--;
  }
});
```

### Filtering

Previous

#### 9

#### 10

#### 11

#### 12

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 7

#### 8

#### 9

#### 10

#### 11

#### 12

#### 1

#### 2

#### 3

#### 4

Next

* 1
* 2
* 3

[Filter Slides](javascript:void%280%29)

```text

$('.filtering').slick({
  slidesToShow: 4,
  slidesToScroll: 4
});

var filtered = false;

$('.js-filter').on('click', function(){
  if (filtered === false) {
    $('.filtering').slick('slickFilter',':even');
    $(this).text('Unfilter Slides');
    filtered = true;
  } else {
    $('.filtering').slick('slickUnfilter');
    $(this).text('Filter Slides');
    filtered = false;
  }
});
```

### Destroy

If you really want to be that guy...

```text

$('.your-slider').slick('unslick');
```

### Slider Syncing

#### 1

#### 2

#### 3

#### 4

#### 5

Previous

#### 2

#### 3

#### 4

#### 5

#### 1

#### 2

#### 3

#### 4

#### 5

#### 1

#### 2

#### 3

#### 4

Next

* 1
* 2
* 3
* 4
* 5

```text

 $('.slider-for').slick({
  slidesToShow: 1,
  slidesToScroll: 1,
  arrows: false,
  fade: true,
  asNavFor: '.slider-nav'
});
$('.slider-nav').slick({
  slidesToShow: 3,
  slidesToScroll: 1,
  asNavFor: '.slider-for',
  dots: true,
  centerMode: true,
  focusOnSelect: true
});
```

### Right to Left

Previous

#### 6

#### 1

#### 2

#### 3

#### 4

#### 5

#### 6

#### 1

Next

* 1
* 2
* 3
* 4
* 5
* 6

```text

$('.single-item-rtl').slick({
  rtl: true
});
```

**Note:** the HTML tag or the parent of the slider must have the attribute "dir" set to "rtl".

**and a whole lot more...**

### Getting Started

Set up your HTML markup.

```text

<div class="your-class">
  <div>your content</div>
  <div>your content</div>
  <div>your content</div>
</div>
```

Move the /slick folder into your project

Add slick.css in your &lt;head&gt;

```text

<link rel="stylesheet" type="text/css" href="slick/slick.css"/>
// Add the new slick-theme.css if you want the default styling
<link rel="stylesheet" type="text/css" href="slick/slick-theme.css"/>
```

Add slick.js before your closing &lt;body&gt; tag, after jQuery \(requires jQuery 1.7 +\)

```text

<script type="text/javascript" src="//code.jquery.com/jquery-1.11.0.min.js"></script>
<script type="text/javascript" src="//code.jquery.com/jquery-migrate-1.2.1.min.js"></script>
<script type="text/javascript" src="slick/slick.min.js"></script>
```

Initialize your slider in your script file or an inline script tag

```text

$(document).ready(function(){
  $('.your-class').slick({
    setting-name: setting-value
  });
});
```

When complete, your HTML should look something like:

```text

<html>
  <head>
  <title>My Now Amazing Webpage</title>
  <link rel="stylesheet" type="text/css" href="slick/slick.css"/>
  <link rel="stylesheet" type="text/css" href="slick/slick-theme.css"/>
  </head>
  <body>

  <div class="your-class">
    <div>your content</div>
    <div>your content</div>
    <div>your content</div>
  </div>

  <script type="text/javascript" src="//code.jquery.com/jquery-1.11.0.min.js"></script>
  <script type="text/javascript" src="//code.jquery.com/jquery-migrate-1.2.1.min.js"></script>
  <script type="text/javascript" src="slick/slick.min.js"></script>

  <script type="text/javascript">
    $(document).ready(function(){
      $('.your-class').slick({
        setting-name: setting-value
      });
    });
  </script>

  </body>
</html>
```

NOTE: I highly recommend putting your initialization script in an external JS file.

### Settings

| accessibility | boolean | true | Enables tabbing and arrow key navigation |
| :--- | :--- | :--- | :--- |
| adaptiveHeight | boolean | false | Enables adaptive height for single slide horizontal carousels. |
| autoplay | boolean | false | Enables Autoplay |
| autoplaySpeed | int\(ms\) | 3000 | Autoplay Speed in milliseconds |
| arrows | boolean | true | Prev/Next Arrows |
| asNavFor | string | null | Set the slider to be the navigation of other slider \(Class or ID Name\) |
| appendArrows | string | $\(element\) | Change where the navigation arrows are attached \(Selector, htmlString, Array, Element, jQuery object\) |
| appendDots | string | $\(element\) | Change where the navigation dots are attached \(Selector, htmlString, Array, Element, jQuery object\) |
| prevArrow | string \(html\|jQuery selector\) \| object \(DOM node\|jQuery object\) | &lt;button type="button" class="slick-prev"&gt;Previous&lt;/button&gt; | Allows you to select a node or customize the HTML for the "Previous" arrow. |
| nextArrow | string \(html\|jQuery selector\) \| object \(DOM node\|jQuery object\) | &lt;button type="button" class="slick-next"&gt;Next&lt;/button&gt; | Allows you to select a node or customize the HTML for the "Next" arrow. |
| centerMode | boolean | false | Enables centered view with partial prev/next slides. Use with odd numbered slidesToShow counts. |
| centerPadding | string | '50px' | Side padding when in center mode \(px or %\) |
| cssEase | string | 'ease' | CSS3 Animation Easing |
| customPaging | function | n/a | Custom paging templates. See source for use example. |
| dots | boolean | false | Show dot indicators |
| dotsClass | string | 'slick-dots' | Class for slide indicator dots container |
| draggable | boolean | true | Enable mouse dragging |
| fade | boolean | false | Enable fade |
| focusOnSelect | boolean | false | Enable focus on selected element \(click\) |
| easing | string | 'linear' | Add easing for jQuery animate. Use with easing libraries or default easing methods |
| edgeFriction | integer | 0.15 | Resistance when swiping edges of non-infinite carousels |
| infinite | boolean | true | Infinite loop sliding |
| initialSlide | integer | 0 | Slide to start on |
| lazyLoad | string | 'ondemand' | Set lazy loading technique. Accepts 'ondemand' or 'progressive' |
| mobileFirst | boolean | false | Responsive settings use mobile first calculation |
| pauseOnFocus | boolean | true | Pause Autoplay On Focus |
| pauseOnHover | boolean | true | Pause Autoplay On Hover |
| pauseOnDotsHover | boolean | false | Pause Autoplay when a dot is hovered |
| respondTo | string | 'window' | Width that responsive object responds to. Can be 'window', 'slider' or 'min' \(the smaller of the two\) |
| responsive | object | none | Object containing breakpoints and settings objects \(see demo\). Enables settings sets at given screen width. Set settings to "unslick" instead of an object to disable slick at a given breakpoint. |
| rows | int | 1 | Setting this to more than 1 initializes grid mode. Use slidesPerRow to set how many slides should be in each row. |
| slide | element | '' | Element query to use as slide |
| slidesPerRow | int | 1 | With grid mode intialized via the rows option, this sets how many slides are in each grid row. dver |
| slidesToShow | int | 1 | \# of slides to show |
| slidesToScroll | int | 1 | \# of slides to scroll |
| speed | int\(ms\) | 300 | Slide/Fade animation speed |
| swipe | boolean | true | Enable swiping |
| swipeToSlide | boolean | false | Allow users to drag or swipe directly to a slide irrespective of slidesToScroll |
| touchMove | boolean | true | Enable slide motion with touch |
| touchThreshold | int | 5 | To advance slides, the user must swipe a length of \(1/touchThreshold\) \* the width of the slider |
| useCSS | boolean | true | Enable/Disable CSS Transitions |
| useTransform | boolean | true | Enable/Disable CSS Transforms |
| variableWidth | boolean | false | Variable width slides |
| vertical | boolean | false | Vertical slide mode |
| verticalSwiping | boolean | false | Vertical swipe mode |
| rtl | boolean | false | Change the slider's direction to become right-to-left |
| waitForAnimate | boolean | true | Ignores requests to advance the slide while animating |
| zIndex | number | 1000 | Set the zIndex values for slides, useful for IE9 and lower |

### Events

In slick 1.4, callback methods have been deprecated and replaced with events. Use them as shown below:

```text

// On swipe event
$('.your-element').on('swipe', function(event, slick, direction){
  console.log(direction);
  // left
});

// On edge hit
$('.your-element').on('edge', function(event, slick, direction){
  console.log('edge was hit')
});

// On before slide change
$('.your-element').on('beforeChange', function(event, slick, currentSlide, nextSlide){
  console.log(nextSlide);
});
```

| afterChange | slick, currentSlide | Fires after slide change |
| :--- | :--- | :--- |
| beforeChange | slick, currentSlide, nextSlide | Fires before slide change |
| breakpoint | event, slick, breakpoint | Fires after a breakpoint is hit. |
| destroy | event, slick | When slider is destroyed, or unslicked. |
| edge | slick, direction | Fires when an edge is overscrolled in non-infinite mode. |
| init | slick | Fires after first initialization. |
| reInit | slick | Fires after every re-initialization |
| setPosition | slick | Fires after position/size changes |
| swipe | slick, direction | Fires after swipe/drag |
| lazyLoaded | event, slick, image, imageSource | Fires after image loads lazily |
| lazyLoadError | event, slick, image, imageSource | Fires after image fails to load |

### Methods

Methods are called on slick instances through the slick method itself in version 1.4, see below:

```text

// Add a slide
$('.your-element').slick('slickAdd',"<div></div>");

// Get the current slide
var currentSlide = $('.your-element').slick('slickCurrentSlide');
```

This new syntax allows you to call any internal slick method as well:

```text

// Manually refresh positioning of slick
$('.your-element').slick('setPosition');
```

| slickCurrentSlide | none | Returns the current slide index |
| :--- | :--- | :--- |
| slickGoTo | int : slide number, boolean: dont animate | Navigates to a slide by index |
| slickNext | none | Navigates to the next slide |
| slickPrev | none | Navigates to the previous slide |
| slickPause | none | Pauses autoplay |
| slickPlay | none | Starts autoplay |
| slickAdd | html or DOM object, index, addBefore | Add a slide. If an index is provided, will add at that index, or before if addBefore is set. If no index is provided, add to the end or to the beginning if addBefore is set. Accepts HTML String \|\| Object |
| slickRemove | index, removeBefore | Remove slide by index. If removeBefore is set true, remove slide preceding index, or the first slide if no index is specified. If removeBefore is set to false, remove the slide following index, or the last slide if no index is set. |
| slickFilter | Selector or Function | Filters slides using jQuery .filter\(\) |
| slickUnfilter | index | Removes applied filtering |
| slickGetOption | option : string | Gets an individual option value. |
| slickSetOption | option : string, value : depends on option, refresh : boolean | Sets an individual value live. Set refresh to true if it's a UI update. |
| unslick | none | Deconstructs slick |
| getSlick | none | Get Slick Object |

### Wordpress

### Go Get It

[Download Now](https://github.com/kenwheeler/slick/archive/v1.8.1.zip)[View On Github](https://github.com/kenwheeler/slick/)

You can also use slick with the jsDelivr CDN!

```text

CSS

<link rel="stylesheet" type="text/css" href="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css"/>

JS

<script type="text/javascript" src="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>
```

If you like slick, and also like Sass, try my [Guff](http://kenwheeler.github.io/guff) mixin library!

