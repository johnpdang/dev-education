# Development

### Codex

{% embed url="https://codex.wordpress.org/" %}

### Developer.wordpress

{% embed url="https://developer.wordpress.org/themes/getting-started/" %}

{% embed url="https://developer.wordpress.org/themes/basics/template-hierarchy/" %}

### GenerateWP

{% embed url="https://generatewp.com/" %}

### Searchbar

{% embed url="https://wedevs.com/133739/add-search-bar-in-wordpress/" %}

### Snippets

{% tabs %}
{% tab title="nav" %}
{% code-tabs %}
{% code-tabs-item title="register nav menus" %}
```php
	// This theme uses wp_nav_menu() in three locations.
	register_nav_menus( array(
		'top'    => __( 'Top Menu', 'traina' ),
		'footer'    => __( 'Footer Menu', 'traina' ),
		'social' => __( 'Social Links Menu', 'traina' ),
	) );
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="php conditional logic" %}
{% code-tabs %}
{% code-tabs-item title="if h6 form description" %}
```php
<?php if ($form_desc): ?>
  <h6 class="footer__form__desc"><?php echo $form_desc; ?></h6>
<?php endif; ?>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="conditional php logic" %}
```php
if($text_eyebrow):
  $output .= '<h6 class="eyebrow">' . $text_eyebrow . '</h6>';
endif;
$output .= '

```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="title" %}
{% code-tabs %}
{% code-tabs-item title="page title \| site name" %}
```php
<title>	<?php wp_title('|',true,'right'); bloginfo('name'); ?></title>
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="traina icons" %}
{% code-tabs %}
{% code-tabs-item title="get svg arrow icon" %}
```php
<?php echo traina_get_svg_icon('arrow-icon'); ?>
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="WP REST API" %}
By default, the REST API does not support the ‘menu\_order’ order\_by filter. Luckily, we can add to the allowed filters list. Place this in your functions.php or similar file:

```php
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

```php
/wp-json/wp/v2/beer?orderby=menu_order&order=asc
```
{% endtab %}
{% endtabs %}



