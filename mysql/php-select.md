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
  // output data of each row
  while($rij = mysqli_fetch_assoc($resultaat)) {
    echo $rij["veld_naam_1"]. " " . $rij["veld_naam_2"]. "<br>";
  }
} else {
  echo "Geen resultaten.";
}

mysqli_close($conn);
?&gt;
</pre>
