---
layout: template
title: Array variable
url: /programmeren/array
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_arrays.asp
---
Een array variable wordt gebruikt voor een collectie van waardes. Elk element in de collectie is aparte te benaderen.

## Numerieke array

De elementen in de array zijn te benaderen via een nummer, een <em>index</em>.

Het eerste element is te benaderen met de <em>index</em> 0, het tweede met de <em>index</em> 1 enz.

#### voorbeeld 1
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  $statuten = ['Student', 'Docent', 'Bediende', 'Arbeider'];
  /*
  $statuten = [
    0 => 'Student', 
    1 => 'Docent', 
    2 => 'Bediende', 
    3 => 'Arbeider'
  ];
  */
  echo $statuten[0] . ' - ' . $statuten[1] . ' - ' . $statuten[2] . ' - ' . $statuten[3];
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>Student - Docent - Bediende - Arbeider</p>
</div>

#### voorbeeld 2
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  $statuten = ['Student', 'Docent', 'Bediende', 'Arbeider'];
  $derde = 2;
  echo 'Het derde statuut "' . $statuten[$derde] .  '".';
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>Het derde statuut is "Bediende".</p>
</div>

## Associatieve array

De elementen in de array zijn te benaderen via een sleutel, een <em>key</em>.

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  $persoonsgegevens = [
    'voornaam' => 'Bert', 
    'achternaam' => 'Jansen',
    'woonplaats' => 'Kalmhout',
  ];
  echo 'De voornaam is "' . $persoonsgegevens['voornaam'] .  '".';
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>De voornaam is "Bert".</p>
</div>

## Numerieke en associatieve array tesamen

Heel vaak heb je een combinatie van de numerieke en associatieve array omdat arrays worden gebruikt om bijvoorbeeld records uit een databank te verwerken.

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  $persoonsgegevens = [
    [
      'voornaam' => 'Bert', 
      'achternaam' => 'Jansen',
      'woonplaats' => 'Kalmhout',
    ],
    [
      'voornaam' => 'Tom', 
      'achternaam' => 'Pintens',
      'woonplaats' => 'Brussel',
    ],
  ];
  
  echo '<p>De voornaam van persoon 1 is "' . $persoonsgegevens[0]['voornaam'] .  '"</p>.';
  echo '<p>De voornaam van persoon 2 is "' . $persoonsgegevens[1]['voornaam'] .  '"</p>.';
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>De voornaam van persoon 1 is "Bert".</p>
<p>De voornaam van persoon 2 is "Tom".</p>
</div>

