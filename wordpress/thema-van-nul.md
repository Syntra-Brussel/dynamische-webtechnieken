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
* het creëren van sidesbar(s) (zie eerdere hoofdstukken)
* het inladen van de stylesheet
* het registeren van de menu

<pre>
&lt;?php
function uw_thema_naam_enqueue_styles() {
    // Laad de child theme CSS.
    wp_enqueue_style( 'theme-style', get_stylesheet_directory_uri() . '/style.css', array(), wp_get_theme()->get( 'Version' ) );
}

// Voer de functie uw_thema_naam_enqueue_styles uit.
add_action( 'wp_enqueue_scripts', 'uw_thema_naam_enqueue_styles');

function uw_thema_naam_primary_nav_init() {
    register_nav_menus(
        array('primary' => 'Primary menu')
    );
}

// Voer de functie uw_thema_naam_primary_nav_init uit.
add_action( 'init', 'uw_thema_naam_primary_nav_init' );
?&gt;
</pre>

* functies op maat die je in je templates kan gaan (her)gebruiken. Een eigen functie naam start je best met bijvoorbeeld de thema naam. Zo weet je in je code dat het om een eigen functie gaat en niet om een functie uit de Wordpress core.

Onderstaande functie toon het beeld bij een post wanneer dat er is. Omdat het een eigen functie is kunnen we bijvoorbeeld ook een link plaatsen rond het beeld. Op die manier kan je deze functie gebruiken in een post overzicht (mét link) of op een post pagina (zónder link). 

Met een extra parameter <code>$post_link</code> kan je optioneel een link plaatsen rond het beeld. 

Een toepassing van deze functie zie je verder op.

<pre>
&lt;?php
function uw_thema_naam_post_thumbnail($post_link = TRUE) {
    if ( ! has_post_thumbnail() ) {
        return;
    } 

    if ($post_link == TRUE) { 
        ?&gt;
        &lt;a href="<?php the_permalink(); ?&gt;"&gt;
        &lt;?php the_post_thumbnail(); ?&gt;
        &lt;/a&gt;
        &lt;?php
    } 
    else {
        the_post_thumbnail(); 
    }
}
?&gt;
</pre>

De functie <code>has_post_thumbnail()</code> zal TRUE geven wanneer een post een beeld heeft, FALSE wanneer dat niet zo is.

De functie <code>the_post_thumbnail()</code> toont van een post het beeld.

De functie <code>the_permalink()</code> is de Wordpress core functie die van een post de link toont van de detail pagina.

## Inladen van <em>template parts</em>.

In elke pagina template kan je delen van een template afzonden naar de <code>template-parts</code> folder. 

Dit is interessant:
* bij hergebruik van bepaalde onderdelen
* om de templates beter leesbaar te houden

Stel dat je een fragment inhoud bijvoorbeeld nodig hebt op zowel de <code>home.php</code> template als een <code>archive.php</code> template dan kan je dit afzonderen en hergebruiken.

<code>get_template_part( 'template-parts/header/site-header' );</code>
In dit voorbeeld wordt het script <code>template-parts/header/site-header.php</code> ingeladen.

## De pagina template <code>index.php</code>, <code>home.php</code>, <code>single.php</code>, ...

Belangrijk hier zijn de <code>get_header()</code> an <code>get_footer()</code> functies. Ze laden het script <code>header.php</code> en <code>footer.php</code> in.

Vervolgens bouw je de HTML op volgens de wensen en noden.

<pre>
&lt;?php
get_header();
?&gt;
&lt;div class="site-content"&gt;
    &lt;?php
    get_template_part( 'template-parts/content/content' );
    ?&gt;
&lt;/div&gt;
&lt;?php
get_footer();
?&gt;
</pre>

## header.php

<pre>
&lt;!doctype html&gt;
&lt;html &lt;?php language_attributes(); ?&gt;&gt;
&lt;head&gt;
	&lt;meta charset="UTF-8" /&gt;
	&lt;meta name="viewport" content="width=device-width, initial-scale=1" /&gt;
	&lt;?php wp_head(); ?&gt;
&lt;/head&gt;

&lt;body &lt;?php body_class(); ?&gt;>
&lt;div class="site"&gt;
&lt;?php 
wp_body_open();
get_template_part( 'template-parts/header/site-header' ); 
?&gt;
    &lt;div class="content"&gt;
</pre>

## footer.php
<pre>
    &lt;/div>
	&lt;footer class="site-footer"&gt;
	&lt;?php get_template_part( 'template-parts/footer/footer-sidebar' ); ?&gt;
	&lt;/footer&gt;
&lt;/div&gt;
&lt;?php wp_footer(); ?&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre>

