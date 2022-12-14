---
layout: template
title: Tabellen aanmaken
url: /mysql/tabellen-aanmaken
collection: mysql
links:
---

Om een nieuwe tabel aan te maken, selecteer je de gewenste database en navigeer je via de menubalk naar het tabblad ‘Structure’ (structuur).

<img src="images/tabellen-aanmaken-1.png" />

Je geeft een naam op en het aantal eigenschappen dat je wenst op te slagen (vergeet de primaire sleutel niet).

Als je bijvoorbeeld een database voor gebruikers van je website wilt maken, kun je de volgende titels voor de kolommen van de tabel gebruiken:

<table class="table"><thead><tr><th>Kolom</th><th>Beschrijving</th></tr></thead><tbody><tr><td>id</td><td>Een uniek identificatienummer voor elke gebruiker</td></tr><tr><td>forename</td><td>Voornaam van de gebruiker</td></tr><tr><td>surname</td><td>Achternaam van de gebruiker</td></tr><tr><td>email</td><td>Emailadres van de gebruiker</td></tr><tr><td>password</td><td>Wachtwoord van de gebruiker</td></tr><tr><td>created_at</td><td>Tijdstip waarop de vermelding is aangemaakt</td></tr><tr><td>updated_at</td><td>Tijdstip waarop de vermelding is gewijzigd</td></tr></tbody></table>

Voor je gebruikersdatabase maak je dus een tabel users met zeven kolommen. Je bevestigt de invoer met ‘Go’.

<img src="images/tabellen-aanmaken-2.png" />

Voer een tabelnaam en het gewenste aantal kolommen in

Geef vervolgens alle eigenschappen en hun type.

<img src="images/tabellen-aanmaken-3.png" />

Eerst het aantal opgegeven eigenschappen maar wel “leeg”
 
<table class="table"><thead><tr><th>Optie</th><th>Omschrijving</th></tr></thead><tbody><tr><td>Name</td><td>Elke kolom van een databasetabel krijgt een titel. Deze kan, met enkele beperkingen, vrij worden gekozen. Latijnse letters (hoofdletters en kleine letters, maar zonder trema’s), cijfers, dollartekens en underscores zijn geen probleem. De underscore kan in plaats van de spatie (niet toegestaan) worden gebruikt (onjuist: user id; juist: user_id). Kolomtitels mogen niet alleen uit cijfers bestaan. Bovendien bevat de databasetaal SQL enkele sleutelwoorden die voor bepaalde taken zijn gereserveerd. Een lijst daarvan vind je in de&nbsp;<a href="https://dev.mysql.com/doc/refman/5.6/en/keywords.html">MySQL-documentatie</a>. De meeste van deze beperkingen kun je omzeilen, maar dan moet je de desbetreffende kolom altijd tussen backticks (“) zetten. Dezelfde regels gelden overigens ook voor&nbsp;<a href="https://dev.mysql.com/doc/refman/5.7/en/identifiers.html">tabel- en andere namen in MySQL</a>. Het is raadzaam relevante kolomtitels in het Nederlands te gebruiken die bij het kenmerk passen.</td></tr><tr><td><strong>Type</strong></td><td>Het gegevenstype geeft aan welke soort gegevens in een kolom wordt opgeslagen. In MySQL en MariaDB kun je gegevens als gehele getallen, drijvendekommagetallen, tijdstippen en data alsook als teksttekenreeksen en binaire gegevens definiëren. Een toelichting hierop vind je in de tabel ‘Gegevenstypen’.</td></tr><tr><td>Length/Values</td><td>Bij sommige gegevenstypen (bijvoorbeeld teksttekenreeksen) kun je voor de waarden van een kolom een maximale lengte instellen. Deze opmaak is echter optioneel.</td></tr><tr><td>Default</td><td>Met de optie ‘Default’ kun je een standaardwaarde voor een kolom bepalen. Deze wordt dan automatisch ingevoegd als een gegevensset geen waarde voor de desbetreffende kolom bevat.</td></tr><tr><td>Collation</td><td>Met de optie ‘Collation’ wijs je een bepaald tekentype aan een kolom toe, die kan afwijken van de globale database-instellingen. Je kunt de codering ook op tabelniveau wijzigen voor alle kolommen.</td></tr><tr><td>Attributes</td><td>Sommige gegevenstypen kunnen door optionele kenmerken nauwkeuriger worden bepaald. Zo kun je met de kenmerken signed en unsigned bijvoorbeeld vastleggen of gehele getallen en drijvendekommagetallen ook negatieve (signed) of alleen positieve (unsigned) waarden kunnen aannemen.</td></tr><tr><td><strong>Index</strong></td><td>Via de optie ‘Index’ stel je regels in voor de indexering. Als je voor een kolom de indexinstelling PRIMARY selecteert, geldt deze kolom als primaire sleutel van de tabel. De instelling UNIQUE legt vast dat waarden binnen deze kolom slechts één keer kunnen worden opgeslagen. Zo kunnen dubbele vermeldingen worden voorkomen.</td></tr><tr><td><strong>A_I</strong></td><td>De afkorting ‘A_I’ staat voor AUTO_INCREMENT en zorgt ervoor dat het databasemanagementsysteem een waarde automatisch doornummert als er bij het aanmaken van een gegevensset geen waarde is ingevoerd. Deze optie wordt bijvoorbeeld gebruikt bij de indexering van gegevenssets.</td></tr><tr></tr><tr><td>Comments</td><td>In het veld ‘Comments’ kun je commentaren bij de kolommen van de tabel zetten.</td></tr></tbody></table>

De verschillende types en hun mogelijke waardes:

<table class="table"><thead><tr><th>Type</th><th>Omschrijving</th><th>Waardenbereik</th><th>Geheugenvereiste</th></tr></thead><tbody><tr><td>TINYINT</td><td>Een zeer klein geheel getal</td><td>Zonder teken: 0 tot 255 Met teken: -128 tot +127</td><td>1 Byte</td></tr><tr><td>SMALLINT</td><td>Een klein geheel getal</td><td>Zonder teken: 0 tot 65.535 Met teken: -32.768 tot +32.767</td><td>2 Byte</td></tr><tr><td>MEDIUMINT</td><td>Een middelgroot geheel getal</td><td>Zonder teken: 0 tot 16.777.215 Met teken: -8.388.608 tot +8.388.607</td><td>3 Byte</td></tr><tr><td>INT/INTEGER</td><td>Een geheel getal van normale grootte</td><td>Zonder teken: 0 tot 4.294.967.295 Met teken: -2.147.483.648 tot +2.147.483.647</td><td>4 Byte</td></tr><tr><td>BIGINT</td><td>Een groot geheel getal</td><td>Zonder teken: 0 tot 18.446.744.073 Met teken: -9.223.372.036.854.775.808 tot +9.223.372.036.854.775.807</td><td>8 Byte</td></tr><tr><td>FLOAT</td><td>Een drijvend kommagetal met enkele precisie&nbsp;</td><td>Zonder teken: 0 tot 3,4e+38 Met teken: -3,4e+38 tot 3,4e+38</td><td>4 Byte</td></tr><tr><td>DOUBLE</td><td>Een drijvend kommagetal met dubbele precisie</td><td>Zonder teken: 0 tot 3,4e+38 Met teken: -3,4e+38 tot 3,4e+38</td><td>8 Byte</td></tr><tr><td>DATE</td><td>Datumweergave in ‘YYYY-MM-DD’</td><td>‘1000-01-01’ tot ‘9999-12-31’</td><td>3 Byte</td></tr><tr><td>TIME</td><td>Tijdweergave in ‘HH:MM:SS:ssssss</td><td>‘-838:59:59.999999’ tot ‘838:59:59.999999’</td><td>3 Byte</td></tr><tr><td>DATETIME</td><td>Datumweergave in ‘YYY-MM-DD HH:MM:SS.ssssss’</td><td>Komt overeen met DATE en TIME (tot 23:59:59.999999 uur)</td><td>8 Byte</td></tr><tr><td>TIMESTAMP</td><td>Tijdstempel in ‘YYY-MM-DD HH:MM:DD’&nbsp;</td><td>‘1970-01-01 00:00:01’ (UTC) tot ‘2038-01-19 05:14:07’ (UTC)</td><td>4 Byte</td></tr><tr><td>YEAR</td><td>Tussen het jaar 1901 en 2155</td><td>1901 tot 2155 en 0000</td><td>1 Byte</td></tr><tr><td>CHAR</td><td>Tekenreeks met vaste lengte; M komt overeen met aantal tekens</td><td>Voor M: 0 tot 255 tekens</td><td>M Byte</td></tr><tr><td>VARCHAR</td><td>Tekenreeks met variabele lengte; M komt overeen met aantal tekens</td><td>Voor M: 0 tot 65.535 tekens</td><td>Max. M + 2 Byte</td></tr><tr><td>TINYTEXT</td><td>Zeer kleine tekenreeks met variabele lengte; M komt overeen met aantal tekens</td><td>Voor M: 0 tot 255 tekens</td><td>M + 1 Byte</td></tr><tr><td>TEXT</td><td>Tekenreeks met variabele lengte; M komt overeen met aantal tekens</td><td>Voor M: 0 tot 255 tekens</td><td>M + 2 Byte</td></tr><tr><td>MEDIUMTEXT</td><td>Middelgrote tekenreeks met variabele lengte; M komt overeen met aantal tekens</td><td>Voor M: 0 tot 16.777.215 tekens</td><td>M + 3 Byte</td></tr><tr><td>LONGTEXT</td><td>Lange tekenreeks met variabele lengte; M komt overeen met aantal tekens</td><td>Voor M: 0 tot 4.294.967.295 tekens (4 GB)</td><td>M + 4 Byte</td></tr><tr><td>BLOB</td><td>Een BLOB (Binary Large Object) is een binair object met gegevens van variabele lengte (bijv. afbeeldingen, audiobestanden)</td><td>Max. lengte M: 65.535 Byte</td><td>M + 2 Byte</td></tr><tr><td>TINYBLOB</td><td>Klein binair object met gegevens van variabele lengte</td><td>Max. lengte M: 255 Byte</td><td>M + 1 Byte</td></tr><tr><td>MEDIUMBLOB</td><td>Middelgroot binair object met gegevens van variabele lengte</td><td>Max. lengte M: 16.777.215 Byte</td><td>M + 3 Byte</td></tr><tr><td>LONGBLOB</td><td>Groot binair object met gegevens van variabele lengte</td><td>Max. lengte M: 4.294.967.295 Byte (4 GB)</td><td>M + 4 Byte</td></tr><tr><td>ENUM (opsomming)</td><td>Een tekenreeksobject waarvan de toelaatbare waarden bij het aanmaken van de kolom worden gedefinieerd</td><td>Max. 65,535 verschillende elementen</td><td>1 of 2 Bytes, afhankelijk van het aantal mogelijke waarden</td></tr><tr><td>SET</td><td>Een tekenreeksobject waarvan de toelaatbare waarden bij het aanmaken van de tabel worden gedefinieerd. Meerkeuze is mogelijk</td><td>Max. 64 verschillende waarden</td><td>1, 2, 3, 4 of 8 Byte, afhankelijk van het aantal mogelijke waarden</td></tr></tbody></table>

<div class="highlight">
<h3>Best practice</h3>
<ul>
<li>Zorg voor een zo correct mogelijk type en de correcte parameters. Je riskeert de juiste inhoud niet te kunnen bewaren, “teveel” ruimte te verspillen of de queries nodeloos complex of niet-performant te maken.</li>
<li>Bij het uitvoeren van de actie wordt achterliggend het SQL commando uitgevoerd. Je kan dit zien via de knop “SQL-voorbeeld” of wanneer je op “Opslaan” hebt geklikt.
</li>
</ul>
</div>

Na het aanmaken van een tabel kan je bijvoorbeeld ook kolommen toevoegen.
<img src="images/tabellen-aanmaken-4.png" />

Je kan ook bestaande kolommen wissen, wijzigen enzovoort via de knoppen achter de veldnamen.

<img src="images/tabellen-aanmaken-5.png" />