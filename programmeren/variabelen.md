---
layout: template
title: Variabelen
url: /programmeren/variablen
collection: programmeren
---
In een variabele kan een bepaalde waarde geplaatst worden om daarmee te 'werken' in het PHP script. Het resultaat kan dan worden gebruikt om daarmee verder te werken of te tonen als uitvoer.

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;html&gt;
  &lt;head&gt;&lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;
    100 + 200 = 
    &lt;?php 
      $getal_1 = 100; 
      $getal_2 = 200; 
      $totaal = $getal_1 + $getal_2; 
      echo $totaal; 
      ?&gt;
    &lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>

<div class="shadow result">
<p>100 + 200 = 300</p>
</div>