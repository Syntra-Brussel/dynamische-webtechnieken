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

De functie <code>the_field()</code> is ideaal om eenvoudige waardes te tonen. Een tekst, een getal, ... . 

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

### Eenvoudige waarde
De functie <code>get_field()</code> geeft de ruwe waarde van het veld terug. Bij een eenvoudige waarde is dat gewoon de waarde. De werkwijze is dat dezelfde als bij <code>the_field()</code> met dat verschil dat je wel <code>echo</code> moet gebruiken. 

### Uitgebreide waarde
Bij een uitgebreide waarde geeft hij de functie <code>get_field()</code> verschillende elementen van de waarde terug via een <code>array</code>.

Het veld type <strong>url</strong> bijvoorbeeld heeft als waarde een <strong>URL</strong> en een <strong>linktekst</strong>.

De <code>get_field()</code> functie retourneert dan een <strong>array</strong> met die twee elementen die je dan kan gaan gebruiken in de template.

### single-video.php

<pre>
&lt;h1&gt;&lt;?php the_title() ?&gt;&lt;/h1&gt;
&lt;ul&gt;
    &lt;li&gt;Regisseur: &lt;?php echo get_field('regisseur'); ?&gt;&lt;/li&gt;
    &lt;li&gt;duurtijd: &lt;?php echo get_field('duurtijd'); ?&gt;&lt;/li&gt;
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

De array elementen kan je trouwens op deze manier te zien krijgen:

<pre>
&lt;pre&gt; 
&lt;?php
print_r($link_info);
?&gt;
&lt;/pre&gt; 
</pre>