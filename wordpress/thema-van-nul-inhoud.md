---
layout: template
title: 'Thema van nul: inhoud'
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

De inhoud van een pagina, post of custom post heeft als belangrijkste inhoud:
* de titel
* de inhoud
* de samenvatting
* het hoofdbeeld
* de link (naar de detail pagina)

Je kan die verschillende onderdelen met een eigen functie tonen.

We voorzien volgende code in <code>index.php</code>:

<pre>
&lt;?php
get_header();
?&gt;
&lt;div class="site-content"&gt;

    &lt;p&gt;&lt;u&gt;De titel van pagina of bericht:&lt;/u&gt;&lt;/p&gt;

    &lt;h1&gt;&lt;?php the_title(); ?&gt;&lt;/h1&gt;

    &lt;p&gt;&lt;u&gt;Het <em>featured image</em> van pagina of bericht:&lt;/u&gt;&lt;/p&gt;

    &lt;?php the_post_thumbnail(); ?&gt;

    &lt;p&gt;&lt;u&gt;De samenvatting:&lt;/u&gt;&lt;/p&gt;

    &lt;p&gt;&lt;?php the_excerpt(); ?&gt;&lt;/p&gt;

    &lt;p&gt;&lt;u&gt;De inhoud van pagina of bericht:&lt;/u&gt;&lt;/p&gt;

    &lt;p&gt;&lt;?php the_content(); ?&gt;&lt;/p&gt;

    &lt;p&gt;&lt;u&gt;De link naar pagina of bericht:&lt;/u&gt;&lt;/p&gt;

    &lt;a href="&lt;?php the_permalink(); ?&gt;"&gt;Verder lezen&lt;/a&gt;
&lt;/div&gt;
&lt;?php
get_footer();
?&gt;
</pre>