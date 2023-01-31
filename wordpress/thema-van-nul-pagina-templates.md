---
layout: template
title: 'Thema van nul: pagina templates'
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