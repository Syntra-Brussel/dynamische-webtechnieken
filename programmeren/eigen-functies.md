---
layout: template
title: Eigen functies
url: /programmeren/eigen-functies
collection: programmeren
---

Een functie wordt gebruikt om een set van PHP insctructies samen uit te voeren om een speciek. Het belangrijste voordeel aan het gebruik van eigen functies is om code beter leesbaar te maken.

Een functie heeft, bij voorkeur, een naam die omschrijft wat er binnen de functie wordt uigevoerd.

<code>script.php?getal_1=100&getal_2=200</code>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  function functieNaam($parameter1, $parameter2) {
    // verwerking op basis van de parameter
    // $resultaat = ...

    // Uitvoer van het resultaat
    return $resultaat;
  }
  ?&gt;
&lt;/p&gt;
</pre>

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php 
  function optelling($getal_1, $getal_2) {
    $optelling = $getal_1 + $getal_2;
    return $optelling;
  }

  $getal_1 = 100;
  $getal_2 = 200;
  echo $getal_1 . ' + ' . $getal_2 . ' = ' . optelling($getal_1, $getal_2);
  ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>100 + 200 = 300</p>
</div>
