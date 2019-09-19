---
description: React Slider with Parallax Hover Effects
---

# Slider with Parallax Hover

{% embed url="https://tympanus.net/codrops/2019/08/20/react-slider-with-parallax-hover-effects" %}

Walk through the build of a React slider and learn how to implement a parallax hover effect.[![ReactSlider\_featured](https://codropspz-tympanus.netdna-ssl.com/codrops/wp-content/uploads/2019/08/ReactSlider_featured.jpg)](https://codepen.io/hexagoncircle/full/jgGxKR)

From our monthly sponsor: [monday.com is the last team management and design process tool you’ll ever need. Start your free trial.](https://monday.com/lp/mb/codrops/?utm_source=mb&utm_campaign=display&utm_medium=codrops_takeover&utm_banner=article)![Advertisement](https://ad.doubleclick.net/ddm/trackimp/N728909.1044586DAVIDWALSH.NAME/B21046303.251873895;dc_trk_aid=447801726;dc_trk_cid=119166421;ord=[timestamp];dc_lat=;dc_rdid=;tag_for_child_directed_treatment=;tfua=?)

Recently I experimented with building a content slider \(or carousel, if that’s your fancy\) using React. I wanted to create some unique position-based cursor effects when the user hovers over the active slide. This eventually led to the parallax effect you’ll see in the [final demo](https://codepen.io/hexagoncircle/full/jgGxKR).

This post will dive into the details of the slider’s components, the dynamic CSS variables used for the parallax hover effect, and some of the other properties that brought this project to life.

### Component Setup

This React slider consists of three components: _Slider_, _Slide_, and _SliderControl_. The _SliderControl_ houses the button template used for the previous and next arrow controls. The _Slider_ is the parent component that contains the methods for transitioning slides. Inside the _Slider_ render template, an array of slide objects is iterated over and each slide’s data set is returned within a _Slide_ child component using the [map\(\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) method:

```text
{slides.map(slide => {
  return (
    <Slide
      key={slide.index}
      slide={slide}
      current={current}
      handleSlideClick={this.handleSlideClick}
    />
  )
})}
```

Each of these rendered slides has the following properties:

* A unique `key` \(learn more about keys in React [here](https://reactjs.org/docs/lists-and-keys.html)\). This key grabs `index` from the slide’s data.
* A `slide` property equal to the slide object so the component can access that set of data.
* The `current` property grabs the _Slider’s_ `current` state value and controls the previous, current, and next classes being set on each slide.
* `handleSlideClick` points to the _Slider_ method of the same name to update the `current`value to the clicked slide’s `index`. This will animate the clicked slide into view.

### Updating slide classes

The _Slide_ element has additional classes set based on the current slide.

```text
if (current === index) classNames += ' slide--current'
else if (current - 1 === index) classNames += ' slide--previous'
else if (current + 1 === index) classNames += ' slide--next'
```

In the code above, when `current` equals a slide’s index, that slide becomes active and is given a _current_ class name. Adjacent sibling slides get _previous_ and _next_ class names. By adding these classes to their respective slides, unique hover styles can be applied.

![Animation of previous and next slides with cursor changing as elements are hovered](https://codropspz-tympanus.netdna-ssl.com/codrops/wp-content/uploads/2019/08/previous-next-slide-anim.gif)

On hover, the cursor changes based on the direction of the slide and that hovered element is pulled towards the current slide along the x-axis. As a result, the user receives some additional visual cues when they are interacting with those neighboring slides.

### Slide Parallax Hover Effect

Now for the fun part! The _Slide_ component contains methods that cast parallax magic. The `onMouseMove` event attribute is using the `handleMouseMove` method to update the x and y values as the user hovers over the slide. When the cursor is moved off of the slide, `onMouseLeave` calls `handleMouseLeave` to reset the x and y values and transition the slide elements back into place.

The x and y coordinates are calculated by finding the user’s cursor in the viewport and where it’s hovering in relation to the center of the slide element. Those coordinate values are assigned to CSS variables \(`--x` and `--y`\) that are then used in transforms to move the child elements around in the slide. In the following pen, click on the “display coordinates” checkbox and hover over the slide to see how the x and y values update to reflect your cursor’s position and movement.

### The Parallax CSS

Let’s take a look at the CSS \(Sass\) being applied to some of these slide elements:

```text
.slide:hover .slide__image-wrapper {
  --x: 0;
  --y: 0;
  --d: 50
		
  transform: 
    scale(1.025)
    translate(
      calc(var(--x) / var(--d) * 1px),
      calc(var(--y) / var(--d) * 1px)
  );
}
```

The `slide__image-wrapper` has `overflow: hidden` set so that the image can move beyond its wrapper container and hide some of itself beyond the wrapper boundaries. The wrapper container also has a faster `transition-duration` than the image. Now these elements animate at different speeds. I combined this with some fancy transform calculations and it developed some fluid, independent transitions.

### Calculate those transforms

The `translate(x, y)` values are computed using the CSS [calc\(\)](https://developer.mozilla.org/en-US/docs/Web/CSS/calc) function. On the `slide__image-wrapper`, the `--d` property \(the divisor\) is set to 50, which yields a lower coordinate value and less of a push from the slide’s center. Now check out the `slide__image` transform:

```text
.slide__image.slide--current {
  --d: 20;
	
  transform:
    translate(
      calc(var(--x) / var(--d) * 1px),
      calc(var(--y) / var(--d) * 1px)
    ); 
}
```

The divisor is changed to 20 on the `slide__image` so that the x and y values in the transform are higher and will push the image further away from the center of slide. Finally, the formula is multiplied by one pixel so that a unit gets applied to the value. Parallax achieved!

Try playing around with the `--d` values in the CSS and watch how the transitions change! [Edit on Codepen](https://codepen.io/hexagoncircle/pen/jgGxKR).

Does it seem like the slide headline and button seem to move ever so slightly in the opposite direction of the image? Indeed they do! To achieve this, I multiplied the `translate(x, y)`calculations by negative pixel values instead:

```text
.slide__content {
  --d: 60;
	
  transform: 
    translate(
      calc(var(--x) / var(--d) * -1px),
      calc(var(--y) / var(--d) * -1px)
    );
}
```

### Moving the slides

Check out the _Slider_ component render code in the final demo:

You’ll notice the `slider__wrapper` element surrounding the slides. This wrapper transitions back and forth along the x-axis as the user interacts with the slider. The values for this transform are set after the current slide’s index is multiplied by the amount of slides divided into 100.  I’ve added this in a variable on line 163 to keep the template a little cleaner:

```text
'transform': `translateX(-${current * (100 / slides.length)}%)
```

In this example, there are 4 slides. Click the _next_ arrow button or on the second slide \(which has an index of 1\) and it will pull the wrapper 25% to the left. Click on the third slide \(index of 2\), do the math \(2 x 25\), and watch it move the wrapper 50% to the left.

### Some other tidbits

These are a few other features I’d like to quickly call out:

* If a slide isn’t active, the `pointer-events` property is set to none. I chose to do this to avoid keyboard tab focusing on buttons inside inactive slides.
* The parallax effect is only being applied to the current slide by declaring transforms when the `slide--current` class is present. Inactive slides have their own animations and shouldn’t have all that fun hover magic that the active slide has.
* Images fade in when they are loaded using the `imageLoaded` method in the _Slide_ component. This helps the initial load of a slide feel smoother instead of its image just popping in. A future iteration of this project will apply lazy loading as well \(which is starting to roll out as a [native browser feature](https://scotch.io/bar-talk/native-lazy-loading-launched-on-chrome-76); very exciting!\)

How would you extend or refactor this idea? I’d love to read your thoughts and comments. Leave them below or reach out to me on [Twitter](https://twitter.com/hexagoncircle).

