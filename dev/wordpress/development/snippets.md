# Snippets

{% code-tabs %}
{% code-tabs-item title="conditional php logic" %}
```text
if($text_eyebrow):
  $output .= '<h6 class="eyebrow">' . $text_eyebrow . '</h6>';
endif;
$output .= '
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="get svg arrow icon" %}
```text
<?php echo traina_get_svg_icon('arrow-icon'); ?>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="register nav menus" %}
```text
	// This theme uses wp_nav_menu() in three locations.
	register_nav_menus( array(
		'top'    => __( 'Top Menu', 'traina' ),
		'footer'    => __( 'Footer Menu', 'traina' ),
		'social' => __( 'Social Links Menu', 'traina' ),
	) );
```
{% endcode-tabs-item %}
{% endcode-tabs %}



