---
layout: template
title: Voorwaardes
url: /programmeren/voorwaardes
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_if_else.asp
  - url: https://www.w3schools.com/php/php_switch.asp
---
In functie van het resultaat van een bepaalde voorwaarde kan een bepaald deel van een script uitgevoerd worden. 

## if - then - else

#### voorbeeld 1
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  $getal_1 = 100; 
  $getal_2 = 200; 
  if ($getal_1 > $getal_2) {
    $vergelijking = 'groter'; 
  }
  else {
     $vergelijking = 'kleiner'; 
  }
  echo 'getal 1 is ' . $vergelijking . ' dan getal 2'; 
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>getal 1 is kleiner dan getal 2</p>
</div>

#### voorbeeld 2

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  $getal_1 = 200; 
  $getal_2 = 100; 
  if ($getal_1 > $getal_2) {
    $vergelijking = 'groter'; 
  }
  else {
     $vergelijking = 'kleiner'; 
  }
  echo 'getal 1 is ' . $vergelijking . ' dan getal 2'; 
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>getal 1 is groter dan getal 2</p>
</div>

## switch

Interessant wanneer de er meerdere voorwaardes zijn.

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
switch ($statuut) {
  case 'Student':
    // code die wordt uitgevoerd wanneer $statuut gelijk is aan 'Student'
    break;
  case 'Docent':
    // code die wordt uitgevoerd wanneer $statuut gelijk is aan 'Docent'
    break;
  case 'Bediende':
    // code die wordt uitgevoerd wanneer $statuut gelijk is aan 'Bediende'
    break;
  case 'Arbeider':
    // code die wordt uitgevoerd wanneer $statuut gelijk is aan 'Arbeider'
    break;    
  default:
    // code die wordt uitgevoerd wanneer $statuut een andere waarde heeft
}
</pre>