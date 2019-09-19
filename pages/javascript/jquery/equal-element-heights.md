---
description: function for setting equal heights to elements
---

# Equal element heights

```text
(function ($) {
    $(document).ready(function(e) {
        // used for window resize functions
        function debouncer( func , timeout ) {
           var timeoutID , timeout = timeout || 20;
           return function () {
              var scope = this , args = arguments;
              clearTimeout( timeoutID );
              timeoutID = setTimeout( function () {
                  func.apply( scope , Array.prototype.slice.call( args ) );
              } , timeout );
           };
        }
​
        // Set Divs to Equal Heights
    	$equalHeights = function(){
    	  $('.equalHeightContainer').each(function(index, element) {
    		var parent = element;
          	// Get an array of all element heights
    		var elementHeights = $(parent).find('.equalHeightsMeasure').map(function() {
    			if($(this).closest('.equalHeightContainer').is(parent)){
    				return $(this).outerHeight();
    			}
    		}).get();
​
    		// Math.max takes a variable number of arguments
    		// `apply` is equivalent to passing each height as an argument
    		var maxHeight = Math.max.apply(null, elementHeights);
​
    		// Set each height to the max height
    		$(parent).find('.equalHeightsSet').height(maxHeight);
          });
    	};
    	$equalHeights();
​
        // Run functions effected by changing window size
    	$( window ).resize( debouncer( function ( e ) {
    		$equalHeights();
    	} ) );
    });
}(jQuery));
```

