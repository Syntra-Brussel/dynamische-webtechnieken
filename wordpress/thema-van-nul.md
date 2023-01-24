---
layout: template
title: Thema van nul
url: /wordpress/thema-van-nul
collection: wordpress
links:
 - url: https://developer.wordpress.org/themes/basics/template-hierarchy/
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
* het inladen van de stylesheet (zie eerdere hoofdstukken)
* het creëren van sidesbar(s) (zie eerdere hoofdstukken)
* het registeren van de menu

<pre>
&lt;?php
function primary_nav_init() {
    register_nav_menus(
        array('primary' => 'Primary menu')
    );
}

add_action( 'init', 'primary_nav_init' );
&gt;>
</pre>

* functies op maat die je in je templates kan gaan (her)gebruiken. Een eigen functie naam start je best met bijvoorbeeld de thema naam. Zo weet je in je code dat dat het om eigen functie gaat en geen functie uit de Wordpress core.

Onderstaande functie toon het beeld bij een post wanneer dat er is. Omdat het een eigen functie is kunnen we bijvoorbeeld ook een link plaatsen rond het beeld. Op die manier kan je deze functie gebruiken in een post overzicht (mét link) of op een post pagina (zónder link). 

Met een extra parameter <code>$post_link</code> kan je optioneel een link plaatsen rond het beeld. 

Een toepassing van deze functie zie je verder op.

<pre>
&lt;?php
function uw_theme_naam_post_thumbnail($post_link = TRUE) {
    if ( ! has_post_thumbnail() ) {
        return;
    } 

    if ($post_link == TRUE) { ?&gt;
        &lt;a href="<?php the_permalink(); ?&gt;"&gt;
        &lt;?php the_post_thumbnail(); ?&gt;
        &lt;/a&gt;
    &lt;?php
    } 
    else {
        ?&gt;
        &lt;?php the_post_thumbnail(); ?&gt;
        &lt;?php
    }
}
?&gt;
</pre>

De functi <code>has_post_thumbnail()</code> zal TRUE geven wanneer een post een beeld heeft, FALSE wanneer dat niet zo is.

De functie <code>the_post_thumbnail()</code> toont van een post het beeld.

De functie <code>the_permalink()</code> is de Wordpress core functie die van een post de link toont van de detail pagina.

## De pagina template <code>index.php</code>, <code>home.php</code>, <code>single.php</code>, ...

In eerdere hoofstukken hebben hier al aandacht aan besteed.

Belangrijk hier zijn de <code>get_header()</code> an <code>get_footer()</code> functies. Ze laden het script <code>header.php</code> en <code>footer.php</code> in.

Vervolgens bouw je de HTML op volgens de wensen en noden.

## Inladen van <em>template parts</em>.

In elke pagina template kan je delen van een template afzonden naar de <code>template-parts</code> folder. Dit is interessant:
* bij hergebruik van bepaalde onderdelen
* om de templates beter leesbaar te houden

Stel dat je een fragment inhoud bijvoorbeeld nodig hebt op zowel de <code>home.php</code> template als een <code>archive.php</code> template dan kan je dit afzonderen en hergebruiken.

