---
layout: template
title: HTML vs. PHP
url: /programmeren/html-vs-php
collection: programmeren
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

Het resultaat:
<p>Hallo wereld!</p>

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

Het resultaat:
<div class="shadow">
<p>Hallo wereld!</p>
</div>

Zonder een webserver (met de PHP service) zal de PHP niet uitgevoerd worden maar gewoon als tekst worden gestuurd.

Het resultaat:
<div class="shadow">
<p>&lt;?php echo 'Hallo wereld!'; ?&gt;</p>
</div>