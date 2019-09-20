# WP REST API

By default, the REST API does not support the ‘menu\_order’ order\_by filter. Luckily, we can add to the allowed filters list. Place this in your functions.php or similar file:

```text
// This enables the orderby=menu_order for Posts
add_filter( 'rest_post_collection_params', 'filter_add_rest_orderby_params', 10, 1 );

// And this for a custom post type called 'beer'
add_filter( 'rest_beer_collection_params', 'filter_add_rest_orderby_params', 10, 1 );

/* Add menu_order to the list of permitted orderby values */
function filter_add_rest_orderby_params( $params ) {
	$params['orderby']['enum'][] = 'menu_order';
	return $params;
}
```

**FETCHING CUSTOM POST TYPES BY MENU ORDER IN ASCENDING ORDER:**

_Where the custom post type is “beer”_

```text
/wp-json/wp/v2/beer?orderby=menu_order&order=asc
```

