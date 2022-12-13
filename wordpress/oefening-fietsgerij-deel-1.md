---
layout: template
title: 'OEFENING: Fietsgerij (1)'
url: /wordpress/oefening-fietsgerij-deel-1
collection: wordpress
---
## Voorbereiding: wordpress website "Fietsgerij" opzetten
1. Maak deze folder aan: <code>/htdocs/dynamische-webtechnieken-av-nj-2022/wordpress/fietsgerij</code>. Zo komt de folder uiteindelijk ook in GIT terecht (en dus bij mij).
2. Kopieer de inhoud uit de <code>wordpress</code> folder (in je downloads folder) naar de folder die je hebt aangemaakt in stap 1.
3. Maak een lege database "fietsgerij" uit via PHPMyAdmin (bereikbaar via het dashboard van XAMPP).
4. download <a href="fietsgerij/database.sql">deze mysql database</a>
5. importeer de database in de aangemaakte datebase in stap 3 via PHPMyAdmin > "Importeren" knop bovenaan. 
6. download <a href="fietsgerij/wp-config.zip">wp-config.zip</a>, open de zip en plaats het bestand <code>wp-config.php</code> in de folder gemaakt in stap 1.
7. download <a href="fietsgerij/uploads.zip">uploads.zip</a>, open de zip en plaats de inhoud in de folder <code>/htdocs/dynamische-webtechnieken-av-nj-2022/wordpress/fietsgerij/wp-content/uploads</code>.
8. surf nu naar http://localhost/dynamische-webtechnieken-av-nj-2022/wordpress/fietsgerij of http://127.0.01/dynamische-webtechnieken-av-nj-2022/wordpress/fietsgerij en de website zou moeten openen.

## Instructies
1. Maak een correct <em>child theme</em> met de naam "twentytwenty_child" gebaseerd op het <code>twentytwentyone</code> thema.
2. Activeer het aangemaakte <em>child theme</em>. De groene achtergrond zou alvast wit moeten worden 😊
2. Schrijf de CSS in style.css van het <em>child theme</em>.

<div class="highlight">
<h3>TIPS</h3>
<p>Gebruik de inspectietool, bekijk de huidige CSS en pas die aan via de eigen style.css</p>
</div>

## Het resultaat

### Voor
<img class="shadow" src="images/oefening_fietsgerij_deel_1_voor_1.jpg" />
<img class="shadow" src="images/oefening_fietsgerij_deel_1_voor_2.jpg" />

### Na
<img class="shadow" src="images/oefening_fietsgerij_deel_1_na_1.jpg" />
<img class="shadow" src="images/oefening_fietsgerij_deel_1_na_2.jpg" />
