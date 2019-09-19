# Aria expanded

{% embed url="https://stackoverflow.com/questions/48599822/aria-expanded-html-attribute" %}

The [`aria-expanded` attribute](https://www.w3.org/WAI/PF/aria/states_and_properties#aria-expanded) is simply a flag for the user agent. It

> Indicates whether the element, or another grouping element it controls, is currently expanded or collapsed.

...where that indication is for the element's contents, or if [`aria-controls`](https://www.w3.org/WAI/PF/aria/states_and_properties#aria-controls) is also specified, for the target element.

You set its value to indicate what you've done to the page \(e.g., you've expanded or contracted a section\). It doesn't have any particular behavior associated with it, it's for letting the user agent know what's going on so it can interpret that for its audience \(who may be vision-impaired and need some other indication that a section is/isn't expanded\).

