---
layout: template
title: HTTP aanvraag
url: /introductie/http-aanvraag
collection: introductie
links:
  - url: https://www.w3schools.com/tags/ref_httpmethods.asp
  - url: https://www.w3schools.com/tags/ref_httpmessages.asp
---

Een vraag via de webbrowser gebeurt via het HTTP protocol.

<div class="highlight">
Het HTTP protocol staat voor <strong>Hypertext</strong> Transfer Protocol.
<br /><br />
Een webbrowser ontvangt enkel HTML informatie. Om dynamische inhoud te tonen is een <strong>webserver</strong> noodzakelijk die die HTML kan opbouwen. 
</div>

De gegevens worden doorgaans in een database bewaard. De webserver communiceert daarvoor dus met een <strong>databaseserver</strong>.

<img src="images/client_server.png" />

Aan de hand van de URL weet de webserver wat wordt opgevraagd en welke services nodig zijn om het resultaat (HTML) ge verkrijgen dat moet worden terug gestuurd.

### De (unieke) URL

<img src="images/url.png" />

<ul>
  <li><span style="color: red">het protocol:</span> http(s)</li>
  <li><span style="color: green">de domeinnaam</span> die achterliggend verwijst naar een IP adres (elke publieke server heeft een publiek IP adres) en een plekje op de server waar de bestanden staan</li>
  <li><span style="color: darkblue">de folder</span> binnen het gereserveerde plekje op de server</li>
  <li><span style="color: orange">het bestand</span> in de folder</li>
</ul>

In het beeld hierboven is het opgevraagd bestand een HTML bestand, statisch dus. Daarvoor is geen verwerking op de server nodig. Als dit een PHP bestand is weet de webserver dat de PHP service moet gestart worden.

### De URL parameters

<img src="images/url_parameter.png" />

Bij een URL aanvraag kunnen extra parameters verstuurd worden die voor PHP nuttig zijn in de verwerking van informatie.

Dat kan een unieke waarde zijn om in een database de juiste gegevens op te halen, of een parameter die aangeeft of informatie oplopend of aflopend moet worden gesorteerd.

Naast de parameters via de URL kunnen er ook nog parameters (verborgen) worden verstuurd. Dat is vooral interessant als de inhoud die moet worden verstuurd uitgebreid is (bv. bij het versturen van een formulier) of gevoelig is (bv. een paswoord).

### De aanvraag methode

Een URL aanvraag gaat ook gepaard met een methode. De belangrijkste zijn:
* <strong>GET</strong>: Opvragen van informatie (standaard via een webbrowser)
* <strong>POST</strong>: Versturen van informatie (bijvoorbeeld via de submit knop van een formulier)
* PUT: Bijwerken van (bestaande) informatie (bijvoorbeeld op basis van een URL parameter)
* DELETE: Verwijderen van (bestaande) informatie (bijvoorbeeld op basis van een URL parameter)
* ...

### Het resultaat

#### De inhoud

Het resultaat van een aanvraag is (meestal) de opgevraagde inhoud. 

Dat kan de HTML zijn, maar evengoed de inhoud van een Javascript of CSS bestand of  de inhoud van beeld of Excel bestand.

#### Het inhoud type

Naast de inhoud komt ook altijd een inhoud type mee. Op die manier kan de client het antwoord op de correcte manier weer geven. 

#### De code

Het resultaat van een aanvraag komt naast de inhoud (de HTML bijvoorbeeld, of het opgevraagde document) ook altijd met een <strong>code</strong>. Deze weerspiegelt of de server de vraag correct heeft kunnen afhandelen of dat er een probleem is opgetreden.

De meest courante codes:
* <strong>200</strong>: Alles ok
* <strong>404</strong>: Het opgevraagde bestand of script werd niet gevonden
* 403: Niet voldoende rechten (bijvoorbeeld omdat met de vraag niet de correcte authorisatie gegevens zijn mee gestuurd).
* <strong>500</strong>: Intere server fout (meestal door een PHP code die niet correct werd geschreven)

### Altijd nog een beetje statische informatie

De CSS/JS, beelden en andere documenten die bij een aanvraag van dynamische inhoud horen worden wel nog steeds statisch aangeboden. De webserver functioneert dan enkel als doorgeeflijk. De inhoud kan bijvoorbeeld wel nog afgeschermd worden wanneer de aanvrager niet de correcte authorisatie heeft.

