---
layout: template
title: Voorwaardes
url: /programmeren/voorwaardes
collection: programmeren
---
In functie van het resultaat van een bepaalde voorwaarde kan een bepaald deel van een script uitgevoerd worden. 

## if - then - else

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