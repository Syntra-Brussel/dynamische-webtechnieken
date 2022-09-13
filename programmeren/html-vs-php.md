---
layout: template
title: HTML vs. PHP
url: /programmeren/html-vs-php
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_echo_print.asp
---

## <code>index.html</code>
<pre data-enlighter-theme="beyond" data-enlighter-language="html">
&lt;html&gt;
  &lt;head&gt;&lt;/head&gt;
  &lt;body&gt;
  &lt;p&gt;Hallo wereld!&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>

<div class="shadow result">
<p>Hallo wereld!</p>
</div>

Het <code>index.html</code> bestand wordt integraal opgehaald en via de webserver naar de webbrowser gestuurd.

## <code>index.php</code>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;html&gt;
  &lt;head&gt;&lt;/head&gt;
  &lt;body&gt;
  &lt;p&gt;&lt;?php echo 'Hallo wereld!'; ?&gt;&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>

De code tussen <code><?php</code> en <code>?></code> wordt uitgevoerd door de <strong>PHP processor</strong>. Dat levert een uitvoer (= tekst) op dat samen met de HTML elementen errond via de webserver naar de webbrowser wordt gestuurd.

<div class="shadow result">
<p>Hallo wereld!</p>
</div>

Zonder een webserver (met de PHP service) zal de PHP niet uitgevoerd worden maar gewoon als tekst worden gestuurd.

<div class="shadow result">
<p>&lt;?php echo 'Hallo wereld!'; ?&gt;</p>
</div>

<div class="highlight">
<h3>Best practice</h3>
Vermijd zoveel mogelijk HTML elementen binnen een PHP script te verwerken.
<br /><br />

<div style='color: green'>Goed:</div>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
  &lt;p&gt;&lt;?php echo 'Hallo wereld!'; ?&gt;&lt;/p&gt;
</pre>

<div style='color: red'>Te vermijden:</div>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
  &lt;?php echo '&lt;p&gt;Hallo wereld!&lt;/p&gt;'; ?&gt;
</pre>
</div>