---
layout: template
title: 'Thema van nul: templates'
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

Als we dat eens toepassen voor een pagina kan de <code>page.php</code> er zo uit zien:

<pre>
&lt;?php
get_header();
?&gt;
&lt;div class="site-content"&gt;
    &lt;h1&gt;&lt;?php the_title(); ?&gt;&lt;/h1&gt;

    &lt;p&gt;&lt;?php the_excerpt(); ?&gt;&lt;/p&gt;

    &lt;p&gt;&lt;?php the_content(); ?&gt;&lt;/p&gt;

    &lt;a href="&lt;?php the_link(); ?&gt;"&gt;Verder lezen&lt;/a&gt;
&lt;/div&gt;
&lt;?php
get_footer();
?&gt;
</pre>