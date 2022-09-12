---
layout: template
title: Webserver opzetten
url: /introductie/lokaal-vs-publiek
collection: introductie
---
## Publieke webserver
Wanneer we een website op het wereldwijde web willen aanbieden moet onze website op een publieke toegankelijk zijn, via een domeinnaam. 

Aanbieders zijn bijvoorbeeld Combell, one.com, ... . 

De aanbieders bieden daarvoor:
* ruimte op een harde schijf (vaak op een Linux machine) toegankelijk via het (S)FTP of SSH protocol.
* gekoppeld aan een eigen domeinnaam (al dan niet bij hen geregistreerd en beheerd)
* op hun server draait vaak Apache of nginx als webserver (voor PHP)
* op hun server draait vaak MySQL als databaseserver

De aanboden harde schijf ruimte, de bandbreedte (upload naar en download van de webserver), de beschikbare database ruimte en de eventuele andere opties.

## Lokale webserver

Wanneer we een website aan het ontwikkelen zijn is het veel interessanter om een webserver op te zetten op een computer. Een verbinding met het internet is dan niet nodig. Hij is dan ook nog helemaal afgeschermd van het publiek tot hij volledig af en veilig is.