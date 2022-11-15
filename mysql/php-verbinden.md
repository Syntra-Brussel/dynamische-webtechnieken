---
layout: template
title: Verbinden via PHP
url: /mysql/php-verbinden
collection: mysql
links:
  - url: https://www.w3schools.com/php/php_mysql_connect.asp
---

Voor je een database kan bevragen of manipuleren vanuit PHP leg je via een gebruikersnaam en een paswoord een verbinding met de server, je opent als het ware een deur bij de server met een correcte sleutel.

## Gebruikersnaam en wachterwoord
Wanneer je via een publieke mysql werkt zal je bij het aanmaken van een database ook een gebruikersnaam en wachtwoord moeten bepalen. Zorg dat die complex genoeg is. 

Op onze lokale XAMPP configuratie zijn wij de eigenaar van de server en hebben we dus ook <em>root</em> toegang. Lokaal kunnen we dus de gebruikersnaam <strong>root</strong> gebruiken <strong>zonder een paswoord</strong>.

## IP adres en hostname

Net als een webserver heeft ook een mysql een IP adres en een hostname (naam van de machine of een URL). Omdat een webserver en een mysql totaal verschillend zijn is het ook meestal zo dat mysql op een andere server draait.

Op onze lokale XAMPP configuratie draaien beide wel op dezelfde server en is het IP adres en de hostname dus dezelfde als voor onze webserver localhost gebruiken.

## Poort

Elke service op een server draait via een bepaalde poort, je kan dat vergelijken met een deur nummer. De poort die standaard voor mysql wordt gebruikt is 3306. Als de service op de standaard poort werkt moet je deze niet specifiek opgeven bij een verbinding.

## Verbinden in PHP

Standaard zijn binnen PHP functies voorzien om de verbinding met een mysql server te maken. Dat kan met de <code>mysqli_connect()</code> functie. De parameters voor de functie <em>servernaam</em>, <em>gebruikersnaam</em> en <em>paswoord</em>. Het resultaat van de functie geeft een <code>TRUE</code> of <code>FALSE</code> terug. Zo kan je dus controleren of de verbinding is gelukt.

<pre>
&lt;?php
$servername = "localhost";
$username = "root";
$password = "";

// Verbinding maken
$conn = mysqli_connect($servername, $username, $password);

// Verbinding controleren
if (!$conn) {
  die("Fout bij het verbinden: " . mysqli_connect_error());
} 
echo "Succesvol verbonden";
?&gt;
</pre>