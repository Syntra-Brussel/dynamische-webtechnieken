---
layout: template
title: URL (GET) parameters
url: /programmeren/url-parameters
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_superglobals_get.asp
---
De URL parameter kan ook gebruikt in een script.

<code>script.php?getal_1=100&getal_2=200</code>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php echo $_GET['getal_1']; ?&gt; + 
  &lt;?php echo $_GET['getal_2']; ?&gt; = 
  &lt;?php echo $_GET['getal_1'] + $_GET['getal_2']; ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>100 + 200 = 300</p>
</div>