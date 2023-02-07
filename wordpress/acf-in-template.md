---
layout: template
title: Advanced Custom Fields in een template
url: /wordpress/acf-in-template
collection: wordpress
links:
  - url: https://www.advancedcustomfields.com/resources/the_field/
  - url: https://wordpress.org/plugins/classic-editor/
---

Vanaf dat je de ACF plugin hebt geïnstalleerd en je de velden aan je (custom) post hebt toegevoegd moet je de waardes uit de velden uiteraard nog gaan opnemen in je template.

## <code>the_field()</code>

De functie <code>the_field()</code> is ideaal om enkelvoudige waardes te tonen. Een tekst, een getal, ... . 

Wanneer je bijvoorbeeld een custom post type "Video" hebt met daar een specifiek veld "regiseur" en "duurtijd" dan zou de code er als volgt kunnen uitzien.

### single-video.php
<pre>
&lt;h1&gt;&lt;?php the_title() ?&gt;&lt;/h1&gt;
&lt;ul&gt;
    &lt;li>Regisseur: &lt;?php the_field('regisseur'); ?&gt;&lt;/li&gt;
    &lt;li>duurtijd: &lt;?php the_field('duurtijd'); ?&gt;&lt;/li&gt;
&lt;/ul&gt;
</pre> 


## <code>get_field()</code>

De functie <code>get_field()</code> geeft de ruwe waarde van het veld terug. Bij een enkelvoudige waarde is gewoon de waarde.

Bij meervoudige waardes geeft hij de verschillende elementen van de waarde terug.

Het veld type <strong>url</strong> heeft als waarde bijvoorbeeld een <strong>URL</strong> en een <strong>linktekst</strong>.

De <code>get_field()</code> retourneerd een array met die twee elementen en die kan je dan uiteraard ook gaan gebruiken in de template.

### single-video.php

<pre>
&lt;h1&gt;&lt;?php the_title() ?&gt;&lt;/h1&gt;
&lt;ul&gt;
    &lt;li&gt;Regisseur: &lt;?php the_field('regisseur'); ?&gt;&lt;/li&gt;
    &lt;li&gt;duurtijd: &lt;?php the_field('duurtijd'); ?&gt;&lt;/li&gt;
    &lt;?php 
    $link_info = get_field('link'); 
    ?&gt;
    &lt;li&gt;Link: 
        &lt;a href="&lt;?php echo $link_info['url']; ?&gt;"&gt;
        &lt;?php echo $link_info['title']; ?&gt;
        &lt;/a&gt;
    &lt;/li&gt;
&lt;/ul&gt;    
</pre>

De array structuur kan je trouwens op deze manier te zien krijgen:

<pre>
&lt;?php
print_r($link_info);
?&gt;
</pre>