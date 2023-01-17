---
layout: template
title: Templates
url: /wordpress/templates
collection: wordpress
links:
 - url: https://developer.wordpress.org/themes/basics/template-hierarchy/
---
We onderzoeken de templates die aan de opbouw van ons twentytwentyone thema.

## pagina templates
We onderscheiden verschillende pagina types. Ze hebben ook elk hun overeenkomstige template in de thema folder.
* pagina -> <code>page.php</code>
* bericht details -> <code>single.php</code>
* overzicht van berichten -> <code>archive.php</code>
* zoek pagina -> <code>search.php</code>
* 404 pagina -> <code>404.php</code>

Wanneer geen specifiekere template wordt gevonden wordt <code>index.php</code> gebruikt.

## pagina hierachie

Wordpress heeft een heel systeem om te bepalen welke pagina template voor een bepaald type pagina het meest geschikt is.

<img src="images/pagina_template_hierarchie.png" />

## header & footer
In de thema folder vinden we ook volgende templates terug:
* <code>header.php</code>: bevat alle HTML tot aan het <main> element
* <code>footer.php</code>: bevat alle HTML onder het <main> element

Via de <code>get_header()</code> en <code>get_footer()</code> functies worden de <code>header.php</code> en <code>footer.php</code> ingeladen.

## template parts
Afhankelijk van de type pagina worden specifieke template deeltjes apart ingeladen.
Dat gebeurt via de <code>get_template_part()</code> functie.