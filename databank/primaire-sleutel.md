---
layout: template
title: Primaire sleutel
url: /databank/primaire-sleutel
collection: databank
links:
---

In elke tabel moet er een <strong>primaire sleutel</strong> of <strong>unieke waarde</strong> aanwezig zijn. Dit is een <strong>kolom of veld</strong> dat uniek is voor alle records. Enkele voorbeelden:

* In een tabel “Auto’s” zal bijvoorbeeld de kolom nummerplaat uniek zijn. Het is namelijk onmogelijk dat er twee auto’s dezelfde nummerplaat hebben.

<img src="/images/primaire-sleutel-1.jpg" />

* In een tabel “Leden” van een wandelclub krijgt iedere gebruiker een ledennummer. Deze is uniek en kan gebruikt worden als primaire sleutel.

<img src="/images/primaire-sleutel-2.jpg" />

* Wanneer er geen voor de hand liggende unieke waarde is, kan je er zelf één maken. Heb je bijvoorbeeld een tabel “Boeken”, bestaat de kans immers dat er twee boeken dezelfde titel hebben. In dat geval kan je een extra kolom “Boeknummer” toevoegen waar een uniek nummer komt in te staan per boek.
In ons voorbeeld krijgen we de volgende primaire sleutels:

* Voor de tabel “Boeken”: Boeknummer
* Voor de tabel “Leden”: Ledennummer
* Voor de tabel “Uitleningen”: Uitleennummer