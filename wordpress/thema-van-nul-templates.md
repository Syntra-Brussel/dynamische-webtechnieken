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

## De pagina template <code>index.php</code>, <code>home.php</code>, <code>single.php</code>, ...

Belangrijk hier zijn de <code>get_header()</code> an <code>get_footer()</code> functies. Ze laden het script <code>header.php</code> en <code>footer.php</code> in.

Vervolgens bouw je de HTML op volgens de wensen en noden.

<pre>
&lt;?php
get_header();
?&gt;
&lt;div class="site-content"&gt;
    &lt;?php
    // Inhoud komt hier.
    ?&gt;
&lt;/div&gt;
&lt;?php
get_footer();
?&gt;
</pre>

## <code>archive-<em>post_type</em>.php</code>

<pre>
&lt;?php
get_header();
?&gt;
<div class="site-main-content">
    &lt;?php 
    // Overzicht van posts komt hier.
    ?&gt;
</div>
&lt;?php
get_footer();
?&gt;
</pre>

## <code>header.php</code> en <code>footer.php</code>

### <code>header.php</code>
<pre>
&lt;!doctype html&gt;
&lt;html &lt;?php language_attributes(); ?&gt;&gt;
&lt;head&gt;
	&lt;meta charset="UTF-8" /&gt;
	&lt;meta name="viewport" content="width=device-width, initial-scale=1" /&gt;
	&lt;?php wp_head(); ?&gt;
&lt;/head&gt;

&lt;body &lt;?php body_class(); ?&gt;>
&lt;?php 
wp_body_open();
// Header inhoud komt hier.
?&gt;
</pre>

<code>wp_head()</code>: Laadt de code in de template die binnen de <code><head></code> hoort, zoals de stylesheets and javascripts. Deze functie zorgt er ook voor dat de Wordpress admin rondom de website wordt getoond.

<code>wp_body_open()</code>: Laadt (eventuele) code in de template die specifiek bij de start van de <code><body></code> hoort.

<code>body_class()</code>: Deze functie geeft een aantal nuttige <em>classes</em> voor CSS doeleinden. Bijvoorbeeld krijg je een class terug met de post type, maar ook een class met post type en ID.

### <code>footer.php</code>
<pre>
	&lt;footer class="site-footer"&gt;
	&lt;?php 
    // Footer inhoud komt hier. 
    ?&gt;
	&lt;/footer&gt;
&lt;?php wp_footer(); ?&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre>

<code>wp_footer()</code>: Laadt de code in de template die specifiek op het eiden van de <code><body></code> hoort.

## Inladen van <em>template parts</em>.

In elke pagina template kan je delen van een template afzonderen naar de <code>template-parts</code> folder. 

Dit is interessant:
* bij hergebruik van bepaalde onderdelen
* om de templates beter leesbaar te houden

Stel dat je een fragment inhoud bijvoorbeeld nodig hebt op zowel de <code>home.php</code> template als een <code>archive.php</code> template dan kan je dit afzonderen en hergebruiken.

Voorbeeld in <code>header.php</code>:
<pre>
&lt;!doctype html&gt;
&lt;html &lt;?php language_attributes(); ?&gt;&gt;
&lt;head&gt;
	&lt;meta charset="UTF-8" /&gt;
	&lt;meta name="viewport" content="width=device-width, initial-scale=1" /&gt;
	&lt;?php wp_head(); ?&gt;
&lt;/head&gt;

&lt;body &lt;?php body_class(); ?&gt;>
&lt;?php 
wp_body_open();
get_template_part( 'template-parts/header/site-header' );
?&gt;
</pre>

In dit voorbeeld wordt het script <code>template-parts/header/site-header.php</code> ingeladen.

Voorbeeld in <code>footer.php</code>:

<pre>
	&lt;footer class="site-footer"&gt;
	&lt;?php get_template_part( 'template-parts/footer/footer-sidebar' ); ?&gt;
	&lt;/footer&gt;
&lt;?php wp_footer(); ?&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre>

### <code>template-parts/header/site-header.php</code>
 
<pre>
&lt;header class="site-header-content">
	&lt;?php if ( has_custom_logo() ) : ?&gt;
		&lt;div class="site-logo"&gt;
			&lt;?php the_custom_logo(); ?&gt;
		&lt;/div>
	&lt;?php endif; ?&gt;

	&lt;?php
	if ( has_nav_menu( 'primary' ) ) : ?&gt;
		&lt;nav class="primary-navigation"&gt;
			&lt;?php
			wp_nav_menu();
			?&gt;
		&lt;/nav&gt;
	&lt;?php
	endif;
	?&gt;
&lt;/header&gt;
</pre>

<code>has_custom_logo()</code>: Wordpress functie om te controleren of er website logo is opgeladen. Het is resultaat is TRUE of FALSE.

<code>the_custom_logo()</code>: Wordpress functie om te het website logo te tonen.

<code>has_nav_menu()</code>: Wordpress functie om te controleren of er een navigatie is gedefinieerd. Het is resultaat is TRUE of FALSE.

<code>wp_nav_menu()</code>: Wordpress functie om de navitie te tonen (standaard: 'primary', in een <code>&lt;ul&gt;&lt;li&gt;</code>-structuur)

### <code>template-parts/footer/footer-sidebar.php</code>

<pre>
&lt;?php
if ( is_active_sidebar( 'footer-sidebar' ) ) :
    dynamic_sidebar( 'footer-sidebar' );
endif;
?&gt;
</pre>

<code>is_active_sidebar()</code>: controleer of een sidebar is geregistreerd

<code>dynamic_sidebar()</code>: toon de inhoud van een sidebar

### <code>template-parts/content/content.php</code>
<pre>
&lt;?php 
the_title( '&lt;h1&gt;', '&lt;/h1&gt;' ); 

uw_thema_naam_post_thumbnail(FALSE); 

the_content();
?&gt;
</pre>

<code>the_title()</code>: de Wordpress functie om de post titel te tonen.

<code>uw_thema_naam_post_thumbnail()</code>: Een 'eigen' functie om het <em>featured image</em> te tonen. Zie verder door.

<code>the_content()</code>: de Wordpress functie om de post inhoud te tonen.

### <code>template-parts/content/archive-<em>post_type</em></code>

<pre>
&lt;?php
// Parameters voor de Post query.
$args = array('post_type' =&gt; 'dienst');
// Execute query
$cpt_query = new WP_Query($args);
// Wanneer de query post(s) oplevert.
if ($cpt_query-&gt;have_posts()) {
    ?&gt;
    &lt;div class="archive-posts"&gt;
    &lt;?php
    // Loop over de verschillende posts.
    while ( $cpt_query-&gt;have_posts() ) {
        // Laad de post in, op de achtergrond.
        $cpt_query-&gt;the_post();
        ?&gt;
        &lt;article&gt;
            &lt;header&gt;

                &lt;a href="&lt;?php the_permalink(); ?&gt;"&gt;&lt;h2&gt;&lt;?php the_title(); ?&gt;&lt;/h2&gt;&lt;/a&gt;
            
                &lt;?php uw_thema_naam_post_thumbnail( TRUE ); ?&gt;				
            
            &lt;/header&gt;

            &lt;?php the_excerpt(); ?&gt;

            &lt;a href="<?php the_permalink(); ?&gt;"&gt;Verder lezen&lt;/a&gt;

        &lt;/article&gt;
        &lt;?php
    }
    ?&gt;
    &lt;/div&gt;
    &lt;?php
}
?&gt;
</pre>

<code>the_excerpt()</code>: Toon de samenvatting van de post.
<code>uw_thema_naam_post_thumbnail()</code>: Een 'eigen' functie om het <em>featured image</em> te tonen. Zie verder door.

## Functies op maat die je in je templates kan gaan (her)gebruiken. 

Je kan stukjes code, die op verschillende plaatsen worden gebruikt, onder brengen in een aparte functie. Die kan je plaatsen in de <code>functions.php</code>.

Een eigen functie naam start je best met bijvoorbeeld de thema naam. Zo weet je in je code dat het om een eigen functie gaat en niet om een functie uit de Wordpress core.

### Functie om <em>featured image</em> van een post te tonen

Onderstaande functie toont het <em>featured image</em> van de post wanneer het beeld bestaat. Met een extra parameter <code>$post_link</code> kan je optioneel een link plaatsen rond het beeld. 

<pre>
&lt;?php
function uw_thema_naam_post_thumbnail($post_link = TRUE) {
    if ( ! has_post_thumbnail() ) {
        return;
    } 

    if ($post_link == TRUE) { 
        ?&gt;
        &lt;a href="&lt;?php the_permalink(); ?&gt;"&gt;
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
