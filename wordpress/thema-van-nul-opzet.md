---
layout: template
title: Thema van nul
url: /wordpress/thema-van-nul
collection: wordpress
links:
 - url: https://developer.wordpress.org/reference/functions/get_header/
 - url: https://developer.wordpress.org/reference/functions/get_footer/
 - url: https://developer.wordpress.org/reference/functions/wp_head/
 - url: https://developer.wordpress.org/reference/functions/wp_body_open/
 - url: https://developer.wordpress.org/reference/functions/wp_footer/
 - url: https://developer.wordpress.org/reference/functions/has_post_thumbnail/
 - url: https://developer.wordpress.org/reference/functions/the_post_thumbnail/
 - url: https://developer.wordpress.org/reference/functions/the_permalink/
 - url: https://developer.wordpress.org/reference/functions/get_template_part/
 - url: https://developer.wordpress.org/reference/functions/the_excerpt/
---
Het voordeel van een thema gebaseerd op een ander thema is dat je opbouw en CSS van het parent theme gaat overnemen. Je start niet van nul. Je kan CSS en templates overnemen in je child theme om ze wat zaken specifiek te wijzigen.

Als het parent thema al goed doet wat je wenst is dat een goede oplossing. Als je echter veel wil wijzigen kan het wat complex worden.

Een thema van nul is dan zeker iets wat je kan overwegen.

Met onze kennis van HTML/CSS, PHP en de Wordpress template structuur gaan we van eens van nul een thema bouwen.

Hieronder geef ik wat belangrijke PHP functies die specifiek in de Wordpress core zitten om de Wordpress inhoud te verwerken in je templates.

## <code>style.css</code>

<pre>
/*
Theme Name:   Uw thema naam hier
Description:  Het thema voor 'uw site naam hier'
Version:      1.0.0
*/

...
</pre>

## <code>functions.php</code>

De <code>functions.php</code> wordt gebruikt voor:
* het inladen van stylesheet(s)
* het creëren van sidesbar(s) binnen Wordpress
* het creëren van menu(s) binnen Wordpress

### Stylesheet inladen
<pre>
&lt;?php
function uw_thema_naam_enqueue_styles() {
    wp_enqueue_style( 'theme-style', get_stylesheet_directory_uri() . '/style.css', array(), wp_get_theme()->get( 'Version' ) );
}

// Voer de functie uw_thema_naam_enqueue_styles uit.
add_action( 'wp_enqueue_scripts', 'uw_thema_naam_enqueue_styles');
?&gt;
</pre>

### Custom logo optie activeren in thema
<pre>
&lt;?php
function uw_thema_naam_custom_logo_setup() {
	add_theme_support( 'custom-logo', [] );
}

// Voer de functie uw_thema_naam_custom_logo_setup uit.
add_action( 'after_setup_theme', 'uw_thema_naam_custom_logo_setup' );
?&gt;
</pre>

### Primaire navigatie registreren in thema
<pre>
&lt;?php
function uw_thema_naam_primary_nav_init() {
    register_nav_menus(
        array('primary' => 'Primary menu')
    );
}

// Voer de functie uw_thema_naam_primary_nav_init uit.
add_action( 'init', 'uw_thema_naam_primary_nav_init' );
?&gt;
</pre>

### Sidebar registeren in Wordpress
<pre>
&lt;?php
function uw_thema_naam_sidebar_init() {
    register_sidebar( array(
        'name' => 'Footer',
        'id' => 'footer-sidebar',
        'description' =>  'De footer sidebar verschijnt onderaan.',
    ) );
}  

// Voer de functie uw_thema_naam_sidebar_init() uit.
add_action( 'widgets_init', 'uw_thema_naam_sidebar_init' );
?&gt;
</pre>