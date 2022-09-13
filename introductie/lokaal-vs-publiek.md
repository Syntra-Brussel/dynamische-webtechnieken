---
layout: template
title: Webserver opzetten
url: /introductie/lokaal-vs-publiek
collection: introductie
---
## Publieke webserver
Wanneer we een website op het wereldwijde web willen aanbieden moet onze website op een publieke server toegankelijk zijn, via een domeinnaam. 

Aanbieders zijn bijvoorbeeld <a href="https://www.combell.com" target="_blank">Combell</a>, <a href="https://www.one.com" target="_blank">one.com</a>, <a href="https://www.godaddy.com/nl-be" target="_blank">godaddy.com</a>, ... . 

Wat bieden ze aan:
* ruimte op een bestandsserver (vaak op een Linux machine) toegankelijk via een (S)FTP client.
* gekoppeld aan een eigen domeinnaam (al dan niet bij hen geregistreerd en beheerd)
* op hun server draait vaak Apache of nginx als webserver 
* op hun server draait vaak PHP als service voor dynamische inhoud
* op hun server draait vaak MySQL als databaseserver

De aanboden harde schijf ruimte, de bandbreedte (upload naar en download van de webserver), de beschikbare database ruimte en de eventuele andere opties.

## Lokale webserver

Wanneer we een website aan het ontwikkelen zijn is het veel interessanter om een webserver op te zetten op een computer. 

Voordelen:
* Een <strong>internet verbinding</strong> is dan <strong>niet nodig</strong>. 
* De website is helemaal <strong>afgeschermd van het publiek</strong>. Je kan er dus rustig aan bouwen tot hij volledig af en veilig is.
* De website kan nog niet worden gevonden door Google en (fout) worden geïndexeerd.
* Je werkt <strong>veel sneller</strong> omdat je op de computer zelf werkt.
* We moeten <strong>geen FTP server</strong> gebruiken omdat we, als eigenaar van de computer, bestanden rechtstreeks op de lokale server kunnen plaatsen.