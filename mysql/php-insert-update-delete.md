---
layout: template
title: INSERT / UPDATE / DELETE via PHP
url: /mysql/php-insert-update-delete
collection: mysql
links:
  - url: https://www.w3schools.com/php/php_mysql_insert.asp
  - url: https://www.w3schools.com/php/php_mysql_update.asp
  - url: https://www.w3schools.com/php/php_mysql_delete.asp
---

Wanneer je een verbinding hebt gemaakt met een MySQL server kan je informatie gaan manipuleren. Je doet dat door het versturen van SQL commando's via de <code>mysqli_query()</code> functie. Je geeft als eerste parameter de variabele mee die van de <code>mysqli_connect()</code> komt. Als twee parameter het SQL commando als een <em>string</em>.

<pre>
&lt;?php
$servernaam = "localhost";
$gebruikersnaam = "root";
$paswoord = "";
$databasenaam = "...";

// Verbinding maken
$verbinding = mysqli_connect($servernaam, $gebruikersnaam, $paswoord, $databasenaam);
// Verbinding controleren
if (!$verbinding) {
  die("Fout bij het verbinden: " . mysqli_connect_error());
}

$sql_commando = "...";

if (mysqli_query($verbinding, $sql_commando)) {
  echo "SQL commando is uitgevoerd.";
} else {
  echo "Er liep iets mis bij het uitvoeren van het SQL commando: " . $sql_commando . "<br>" . mysqli_error($verbinding);
}

mysqli_close($conn);
?&gt;
</pre>
## INSERT

Voor het toevoegen van een rij in een tabel.

<pre>
INSERT INTO tabel_naam (kolom_naam_1, kolom_naam_2, kolom_naam_3, ...)
VALUES ('waarde_1', 'waarde_2', 'waarde_3', ...)
</pre>

## UPDATE

Voor het wijzigen van een rij in een tabel.

<pre>
UPDATE tabel_naam
SET kolom_naam_1='waarde', kolom_naam_2='value2', ...
WHERE kolom_naam='waarde' 
</pre>

## DELETE

Voor het verwijderen van en rij in een tabel.

<pre>
DELETE FROM tabel_naam
WHERE kolom_naam = 'waarde'
</pre>