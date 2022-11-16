---
layout: template
title: SELECT via PHP
url: /mysql/php-select
collection: mysql
links:
  - url: https://www.w3schools.com/php/php_mysql_select.asp
---

Het schrijven van een SELECT commando hebben we reeds uitgebreid besproken en geoefend. Het doel van het gebruik van die SELECT commando's is uiteraard om de inhoud die er mee wordt opgehaald te gaan tonen. 

Hier komt het gebruik van arrays op nieuw aan terug. Het is namelijk de manier waarop de inhoud vanuit mySQL wordt opgehaald. 

## SELECT in PHP

<pre>
&lt;?php
$servernaam = "...";
$gebruikersnaam = "...";
$paswoord = "...";
$databasenaam = "...";

// Verbinding maken
$verbinding = mysqli_connect($servernaam, $gebruikersnaam, $paswoord, $databasenaam);
// Verbinding controleren
if (!$verbinding) {
  die("Fout bij het verbinden: " . mysqli_connect_error());
}

$sql_commando = "SELECT veld_naam_1, veld_naam_2, ... FROM tabel_naam";
$resultaat = mysqli_query($verbinding, $sql_commando);

if (mysqli_num_rows($resultaat) > 0) {
  // elke rij verwerken
  while($rij = mysqli_fetch_assoc($resultaat)) {
    echo $rij["veld_naam_1"]. " " . $rij["veld_naam_2"]. "<br>";
  }
} else {
  echo "Geen resultaten.";
}

mysqli_close($conn);
?&gt;
</pre>

## Een concreet voorbeeld

Een overzicht van de uitleningen (met leden en boek informatie) van voor 15/11/2022.

<pre>
SELECT uitleningen.uitleendatum, uitleningen.inleverdatum, leden.voornaam, leden.familienaam, boeken.titel, boeken.auteur FROM `uitleningen`, leden, boeken WHERE uitleningen.ledennummer=leden.ledennummer AND uitleningen.boeknummer=boeken.boeknummer AND uitleningen.inleverdatum < '2022-11-15';
</pre>

<pre>
&lt;?php
$servernaam = "localhost";
$gebruikersnaam = "root";
$paswoord = "";
$databasenaam = "bibliotheek";
// Verbinding maken
$verbinding = mysqli_connect($servernaam, $gebruikersnaam, $paswoord, $databasenaam);

// Verbinding controleren
if ($verbinding) {
  $sql_commando = "SELECT uitleningen.uitleendatum, uitleningen.inleverdatum, leden.voornaam, leden.familienaam, boeken.titel, boeken.auteur FROM `uitleningen`, leden, boeken WHERE uitleningen.ledennummer=leden.ledennummer AND uitleningen.boeknummer=boeken.boeknummer AND uitleningen.inleverdatum < '2022-11-15';";

  // Voer het SQL commando uit in de achterground.
  $resultaat = mysqli_query($verbinding, $sql_commando);

  // Toon het aantal rijen.
  echo '<p>Aantal rijen: ' . mysqli_num_rows($resultaat) . '</p>';

  // Zolang er een rij beschikbaar is in $resultaat, haal $rij op als assoc array.
  while ($rij = mysqli_fetch_assoc($resultaat)) {
    /*
    // Toon de inhoud van de array $rij.
    echo "<pre>";
    print_r($rij);
    echo "</pre>";
    */
    ?&gt;
    <ul>
      <li>uitleendatum: <?php echo $rij['uitleendatum']; ?></li>
      <li>Voornaam: <?php echo $rij['voornaam']; ?></li>
      <li>Familienaam: <?php echo $rij['familienaam']; ?></li>
      <li>Titel: <?php echo $rij['titel']; ?></li>
      <li>Auteur: <?php echo $rij['auteur']; ?></li>
    </ul>
    &lt;?php
  }
}
else {
  die("Fout bij het verbinden: " . mysqli_connect_error());
}
?&gt;
</pre>