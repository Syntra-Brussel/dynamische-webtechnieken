---
layout: template
title: Variabelen
url: /programmeren/variablen
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_variables.asp
---
In een variabele kan een bepaalde waarde geplaatst worden om daarmee te 'werken' in het PHP script. Het resultaat kan dan worden gebruikt om daarmee verder te werken of te tonen als uitvoer.

## Werken met getallen
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  100 + 200 = 
  &lt;?php 
  $getal_1 = 100; 
  $getal_2 = 200; 
  $totaal = $getal_1 + $getal_2; 
  echo $totaal; 
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>100 + 200 = 300</p>
</div>

## Werken met tekst
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  Mijn naam is &lt;strong&gt;
  &lt;?php 
  $voornaam = 'Bert'; 
  $achternaam = 'Jansen'; 
  echo $voornaam . ' ' . $achternaam; 
  ?&gt;&lt;/strong&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>Mijn naam: <strong>Bert Jansen</strong></p>
</div>

<div class="highlight">
<h3>Best practice</h3>

Goed:
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;p&gt;&lt;?php echo $voornaam . ' ' . $achternaam; ?&gt;&lt;/p&gt;
</pre>

Te vermijden:
<div class='strike'>
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;p&gt;&lt;?php echo '$voornaam $achternaam'; ?&gt;&lt;/p&gt;
</pre>
</div>