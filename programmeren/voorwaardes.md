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

### voorbeeld 1
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

### voorbeeld 2

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

<pre>
switch (n) {
  case label1:
    code die wordt uitgevoerd wanneer n=label1;
    break;
  case label2:
    code die wordt uitgevoerd wanneer n=label2;
    break;
  case label3:
    code die wordt uitgevoerd wanneer n=label3;
    break;
    ...
  default:
    code die wordt uitgevoerd wanneer wanner n een andere waarde heeft;
}
</pre>