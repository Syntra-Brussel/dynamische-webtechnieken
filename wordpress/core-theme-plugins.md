---
layout: template
title: Core - theme - plugins
url: /wordpress/core-theme-plugins
collection: wordpress
links:
  - url: https://nl-be.wordpress.org
---
### Wordpress core

Het Wordpress CMS systeem is <strong>geschreven in PHP</strong> en heeft heel wat functies <em>out-of-the-box</em> aanwezig. De PHP code zorgt voor het bewaren en ophalen van gegevens (in de database) en voor de backend die in staat voor het beheer van de informatie. 

Zaken die door de Wordpress core worden voorzien;
* toegang tot de Wordpress admin
* toevoegen wijzigen en verwijderen van posts en pagina's
* beheer van gebruiker
* uploaden van beelden
* tags en categorieën beheren
* Video's verwerken in een tekst
* Toelaten dat gebruikers kunnen antwoorden op posts
* Installeren van extra thema's en plugins
* ...

Het is niet de bedoeling de PHP code van de Wordpress ruggengraat ta gaan wijzigen. Door aanpassingen aan de code te doen kan je een Wordpress website niet meer upgraden en dat is wel echt belangrijk.

Je past dus <strong>geen</strong> code aan in deze folders:
* /wp-admin
* /wp-includes

In de root map je énkel aanpassingen maken aan dit bestand:
* wp-config.php

### Themes
Het weergeven van de website gebeurt via een thema. <strong>Een thema is een set templates in combinatie met JS en CSS.</strong> Wordpress heeft <em>out-of-the-box</em> al enkele themas aan boord om snel van start te gaan. Zeker als je een (eenvoudige) blog wil opstarten. 

Je kan ook extra thema's aankopen met meer mogelijkheden of een specifieke opmaak.

Aan de code van een thema pas je best ook niets aan. Als je een website wil bouwen op een bestaand of aangekocht thema zoek je dus best een thema dat al in een goede richting gaat van wat je wenst en werk je zelf in een child theme.

Je past dus <strong>geen</strong> code aan in deze folders:

* /wp-content/themes/twentytwentyone (thema voorzien door Wordpress)
* /wp-content/themes/twentytwentytwo (thema voorzien door Wordpress)
* /wp-content/themes/twentytwentythree (thema voorzien door Wordpress)

#### Child themes
Omdat een thema nooit helemaal is gebouwd zoals jij (of de klant) het wenst maak je gebruik maken <em>child themes</em>. Een child thema gebruikt standaard de mogelijkheden van een ander thema en laat toe templates te overschrijven met een eigen, nieuwe versie. Een child thema laat ook het toevoegen van CSS toe. 

De template bestanden worden geschreven in het PHP formaat. <strong>Hier zal je HTML, CSS en PHP kennis dus wél van pas komen.</strong>

De child themes komen ook in de /wp-content/themes folder. Deze bestanden mag je <strong>wel</strong> aanpassen.

### Plugins

Naast de functies die Wordpress <em>out-of-the-box</em> bevat kan je via <em>Plugins</em> de functies van een website gaan uitbreiden. Plugins zijn extra stukjes programme die eenvoudig te downloaden zijn vanuit de Wordpress interface. Het is ook hier <strong>niet de bedoeling</strong> dat je de code van een gedownloadde plugin <strong>gaat wijzigen</strong>. Het is namelijk ook voor plugins belangrijk dat je ze up-to-date houdt en dat kan niet (meer) als je de code gaat wijzigen.

Vele plugins hebben naast een gratis versie met basis opties ook een betalende versie met meer uitgebreide mogelijkheid. In onze cursus werken we uitsluitend met de gratis versies van plugin.

Je past dus <strong>geen</strong> code aan in deze folders:

* /wp-content/languages (bevat vertaling informatie door core / themes / plugins toegevoegd) 
* /wp-content/plugins (bevat gedownloade plugin)