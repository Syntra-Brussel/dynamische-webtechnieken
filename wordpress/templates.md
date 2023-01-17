---
layout: template
title: Templates
url: /wordpress/templates
collection: wordpress
links:
 - url: https://developer.wordpress.org/themes/basics/template-hierarchy/
---
Een Wordpress website pagina is een combinatie verschillende templates in mekaar.

Dat heeft als voordeel dat de website eenvoudiger te onderhouden en beter leesbaar is.

## pagina templates

De "buitenste" template noemen we de pagina template.

We onderscheiden verschillende pagina types. Ze hebben elk hun overeenkomstige template in de thema folder.

* pagina -> <code>page.php</code>
* bericht details -> <code>single.php</code>
* overzicht van berichten -> <code>archive.php</code>
* zoek pagina -> <code>search.php</code>
* 404 pagina -> <code>404.php</code>

## pagina hiërarchie

Wordpress heeft een heel systeem om te bepalen welke pagina template voor een bepaald pagina type het meest geschikt is.

Wanneer geen specifieke template wordt gevonden wordt <code>index.php</code> gebruikt. Dit is dus de enige <strong>verplichte pagina template</strong>.

<a href="https://developer.wordpress.org/files/2014/10/Screenshot-2019-01-23-00.20.04.png" target="_blank"><img src="images/pagina_template_hierarchie.png" /></a>
(klik om te openen in een nieuw venster)

### Nog specifiekere pagina hiërarchie

<strong>per ID</strong>

De <code>page.php</code>, <code>category.php</code>, <code>tag.php</code> kunnen nog uitgebreid worden met de slug of de id om zo per pagina, bericht, categorie of tag een specifieke pagina template te voorzien.

Een pagina template specifiek voor de pagina met ID 4 kan je een pagina template voorzien met de naam <code>page-4.php</code>.

<strong>per bericht type</strong>

Stel dat je een <strong>custom post type 'dienst'</strong> hebt kan je voor het overzicht van de diensten een specifieke archief pagina voorzien met de template <code>archive-dienst.php</code>.

Een pagina template specifiek voor een dienst detail pagina kan je voorzien met de naam <code>single-dienst.php</code>.

## header & footer
In de thema folder vinden we ook volgende templates terug:
* <code>header.php</code>: bevat alle HTML tot aan het <main> element
* <code>footer.php</code>: bevat alle HTML onder het <main> element

Via de <code>get_header()</code> en <code>get_footer()</code> functies worden de <code>header.php</code> en <code>footer.php</code> ingeladen.

## template parts
Afhankelijk van het pagina type worden specifieke template deeltjes apart ingeladen die zich bevinden in de <code>template-parts</code> folder.

Dat gebeurt via de <code>get_template_part()</code> functie. 

In de pagina template <code>single.php</code> kom je op regel 18 <code>get_template_part( 'template-parts/content/content-single' );</code> tegen. Dat wil dus zeggen dat de template <code>content-single.php</code> in de folder <code>template-parts/content</code> wordt ingeladen.