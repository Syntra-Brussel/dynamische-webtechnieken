---
layout: template
title: Lussen - Herhalingen
url: /programmeren/lussen
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_looping_for.asp
---
## for-loop

De lus die geschikt is om een taak een welbepaald aantal keer uit te voeren.

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;ul&gt;
  &lt;?php 
    for ($teller = 1; $teller <= 10; $teller++) {
      ?&gt;
      &lt;li&gt;item &lt;?php echo $teller; ?&gt;&lt;/li&gt;
      &lt;?php 
    }
    ?&gt;
  }
  ?&gt;
  &lt;/ul&gt;
&lt;/p&gt;
</pre>


<div class="shadow result">
<ul>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
    <li>item 4</li>
    <li>item 5</li>
    <li>item 6</li>
    <li>item 7</li>
    <li>item 8</li>
    <li>item 9</li>
    <li>item 10</li>
</ul>
</div>
