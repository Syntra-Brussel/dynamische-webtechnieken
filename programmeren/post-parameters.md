---
layout: template
title: POST parameters
url: /programmeren/post-parameters
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_superglobals_post.asp
---
Gebruik de waardes uit het verzenden van een formulier.

<code>script.php</code>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;form action="script.php" method="post"&gt;
  &lt;ul&gt;
    &lt;li&gt;
      getal 1: &lt;input type="number" value="&lt;?php echo $_POST['getal_1']; ?&gt;" name="getal_1" /&gt;
    &lt;/li&gt;
    &lt;li&gt;
      getal 2: &lt;input type="number" value="&lt;?php echo $_POST['getal_2']; ?&gt;" name="getal_2" /&gt;
    &lt;/li&gt;
  &lt;/ul&gt;
  &lt;input type="submit" value="Verstuur" /&gt;
&lt;/form&gt;

&lt;?php
if ($_POST) {
  ?&gt;
  &lt;hr /&gt;
  &lt;p&gt;
    Totaal: 
    &lt;?php
    $totaal = $_POST['getal_1'] + $_POST['getal_2'];
    echo $totaal;
    ?&gt;
  &lt;/p&gt;
  &lt;?php
}
?&gt;
</pre>

### Resultaat voor het versturen van het formulier
<div class="shadow result">
    <form>
    <ul>
    <li>Getal 1: <input type="number" /></li>
    <li>Getal 2: <input type="number" /></li>
    </ul>
    <input type="submit" value="Verstuur" />
    </form>
</div>

### Resultaat na het versturen van het formulier met 100 (getal 1) en 200 (getal 2)
<div class="shadow result">
    <form>
    <ul>
    <li>Getal 1: <input type="number" value="100" /></li>
    <li>Getal 2: <input type="number" value="200" /></li>
    </ul>
    <input type="submit" value="Verstuur" />
    </form>
    <hr />
    <p>Totaal: 300</p>
</div>