---
layout: template
title: Advanced Custom Fields
url: /wordpress/acf
collection: wordpress
links:
  - url: https://wordpress.org/plugins/advanced-custom-fields/
  - url: https://wordpress.org/plugins/classic-editor/
---

## Algemeen

Een veld wordt gebruikt om een <strong>waarde</strong> te bewaren. Dat kan tekst zijn (kort of lang), een referentie naar een opgeladen beeld, een getal, ... .

Een veld heeft uiteraard altijd een <strong>naam</strong> die de inhoud van het veld omschrijft.

De naam wordt onder andere gebruikt om de informatie correct te gaan bewaren in de database.

Een veld kan <strong>in een template gebruikt</strong> worden en er kan zo ook specifiek opmaak aan gegeven worden. Ook daarvoor zal je de naam nodig hebben.

## Velden in Wordpress zijn beperkt

Out-of-the-box is Wordpress een Blog platform. De beschikbare velden zijn dan ook wat voorzien voor een blog:

* titel (voor overzicht en detail pagina)
* samenvatting (voor overzicht pagina)
* omschrijving (voor detail pagina)
* uitgelicht beeld (voor de overzicht en detail pagina)
* categorie waarop je kan worden gegroepeerd in de overzichten
* trefwoord(en) waarop je kan filteren in de overzichten

Ook een Custom Post Type een post type is heeft dus ook alvast een mogelijkheid om deze velden te voorzien.

Een bericht kan echter nog heel wat andere eigenschappen bevatten dan bij een 'klassiek' blog bericht.

Bijvoorbeeld:
* producten: prijs, kleur, maat, ...
* project referenties: jaar, meerdere foto's, ...
* video collectie: jaar, regissieur, ...
* boeken referenties: jaar, ISBN, auteur, ...

<div class="highlight">

<h3>Gewoon onderbrengen in de omschrijving?</h3>

<p>We zouden alle informatie kunnen onderbrengen in de omschrijving maar dan kunnen we het niet tonen in het overzicht bijvoorbeeld en op de detailpagina kunnen we er <strong>moeilijk specifieke opmaak</strong> aan geven via HTML en CSS.</p>
</div>

Omdat op te lossen heeft Wordpress <em>Custom Fields</em> in het leven geroepen. Uitgebreidde op maat velden zeg maar.

Daarvoor is een plugin nodig. Er zijn verschillende plugin beschikbaar om Custom Post Types te gaan definiëren maar wij gaan gebruik maken van de plugin <strong>Advanced Custom Fields</strong>.

## Gutenberg Editor vs Classic Editor

De Gutenberg Editor heeft de manier van content beheer in Wordpress naar een gebruiksvriendelijker niveau getilt. Zoals hierboven al aangehaald is hij echter niet voor alles geschikt.

De eigen gedefinieerde velden staan nu soms wat weg gedrukt. Switchen naar de <em>Classic Editor</em>, de editor die in oudere Wordpress versies werd gebruikt, is dan een goed idee. 
 
Je kan de link naar die plugin hieronder vinden.