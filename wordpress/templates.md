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

## pagina hierachie

Wordpress heeft een heel systeem om te bepalen welke pagina template voor een bepaald type pagina het meest geschikt is.

Wanneer geen specifieke(re) template wordt gevonden wordt <code>index.php</code> gebruikt. Dit is dus de enige verplichte pagina template.

<img src="images/pagina_template_hierarchie.png" />

### Nog specifieker

<strong>per ID</strong>

De <code>page.php</code>, <code>single.php</code>, <code>category.php</code>, <code>tag.php</code> kunnen nog uitgebreid met de slug of de id om per pagina, bericht, categorie of tag een specifieke pagina template te voorzien.

Voor het bericht met id 5 kan je dus een specifieke pagina template voorzien met de naam <code>single-5.php</code>.

<strong>per bericht type</strong>

Stel dat je een custom post type 'dienst' hebt kan je voor het overzicht van de diensten een specifieke archief pagina voorzien met de naar <code>archive-dienst.php</code>.

## header & footer
In de thema folder vinden we ook volgende templates terug:
* <code>header.php</code>: bevat alle HTML tot aan het <main> element
* <code>footer.php</code>: bevat alle HTML onder het <main> element

Via de <code>get_header()</code> en <code>get_footer()</code> functies worden de <code>header.php</code> en <code>footer.php</code> ingeladen.

## template parts
Afhankelijk van de type pagina worden specifieke template deeltjes apart ingeladen.
Dat gebeurt via de <code>get_template_part()</code> functie.