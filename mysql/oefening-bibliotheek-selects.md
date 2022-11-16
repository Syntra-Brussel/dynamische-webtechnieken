---
layout: template
title: 'OEFENING: Bibliotheek selects'
url: /mysql/oefening-bibliotheek-selects
collection: mysql
---
<div class="highlight">
    <h3>Instructies</h3>
    <ul>
        <li>Vorm de correcte SELECTs bij de onderstaande vragen</li>
    </ul>
</div>

1) Maak een selectie van boeken in het genre ‘Thriller’ (enkel de titel en de auteur).

<div class="shadow result show-hide">
<div class="toggle"><a href="#">Toon</a></div>
<div class="show-hide-content">
<pre>
SELECT `titel`, `auteur` FROM `boeken` WHERE `genre` = 'Thriller';
</pre>
</div>
</div>

2) Maak een selectie van de leden die later zijn geboren dan 1/1/1986.

<div class="shadow result show-hide">
<div class="toggle"><a href="#">Toon</a></div>
<div class="show-hide-content">
<pre>
SELECT * FROM `leden` WHERE geboortedatum>'1986-01-01';
</pre>
</div>
</div>

3) Geef een overzicht van de uitleningen (met leden en boek informatie)


<div class="shadow result show-hide">
<div class="toggle"><a href="#">Toon</a></div>
<div class="show-hide-content">
<pre>
SELECT uitleningen.uitleendatum, leden.voornaam, leden.familienaam, boeken.titel, boeken.auteur FROM `uitleningen`, leden, boeken WHERE uitleningen.ledennummer=leden.ledennummer AND uitleningen.boeknummer=boeken.boeknummer;
</pre>
</div>
</div>

4) Geef een overzicht van de uitleningen (met leden en boek informatie) van voor 15/11/20222.


<div class="shadow result show-hide">
<div class="toggle"><a href="#">Toon</a></div>
<div class="show-hide-content">
<pre>
SELECT uitleningen.uitleendatum, uitleningen.inleverdatum, leden.voornaam, leden.familienaam, boeken.titel, boeken.auteur FROM `uitleningen`, leden, boeken WHERE uitleningen.ledennummer=leden.ledennummer AND uitleningen.boeknummer=boeken.boeknummer AND uitleningen.inleverdatum < '2022-11-15';
</pre>
</div>
</div>