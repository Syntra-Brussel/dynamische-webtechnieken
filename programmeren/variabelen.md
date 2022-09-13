---
layout: template
title: Variabelen
url: /programmeren/variablen
collection: programmeren
links:
  - url: https://www.w3schools.com/php/php_variables.asp
  - url: https://www.w3schools.com/php/php_operators.asp
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

<table class="table">
    <tbody>
        <tr>
            <th style="width:15%">Operator</th>
            <th style="width:20%">Naam</th>
            <th style="width:20%">Voorbeeld</th>
            <th style="width:35%">Resultaat</th>
        </tr>
        <tr>
            <td>+</td>
            <td>Optelling</td>
            <td>$x + $y</td>
            <td>Optelling van $x en $y</td>
        </tr>
        <tr>
            <td>-</td>
            <td>Aftrekking</td>
            <td>$x - $y</td>
            <td>Verschil tussen $x en $y</td>
        </tr>
        <tr>
            <td>*</td>
            <td>Vermenigvuldiging</td>
            <td>$x * $y</td>
            <td>Vermenigvuldiging van $x en $y</td>
        </tr>
        <tr>
            <td>/</td>
            <td>Deling</td>
            <td>$x / $y</td>
            <td>Deling van $x en $y</td>
        </tr>
        <tr>
            <td>%</td>
            <td>Modulus</td>
            <td>$x % $y</td>
            <td>Overblijfsel van $x gedeeld door $y</td>
        </tr>
        <tr>
            <td>**</td>
            <td>Exponent</td>
            <td>$x ** $y</td>
            <td>Resultaat van $x to tot de $y'de macht</td>
        </tr>
    </tbody>
</table>

<div class="highlight">
<h3>Best practice</h3>
    <h4>plus 1</h4>
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;?php $teller++; ?&gt;
</pre>
    <div class='strike'>
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;?php $teller = $teller + 1; ?&gt;
</pre>
    </div>
    <h4>min 1</h4>
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;?php $teller--; ?&gt;
</pre>
    <div class='strike'>
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;?php $teller = $teller - 1; ?&gt;
</pre>
    </div>
</div>
## Werken met tekst

Met het . kan je de inhoud van verschillende variabelen aan mekaar 'lijmen'.

<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  Mijn naam is &lt;strong&gt;
  &lt;?php 
  $voornaam = 'Bert'; 
  $achternaam = 'Jansen'; 
  echo $voornaam . ' ' . $achternaam; 
  ?&gt;
  &lt;/strong&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>Mijn naam is <strong>Bert Jansen</strong></p>
</div>

<div class="highlight">
<h3>Best practice</h3>

<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;?php echo $voornaam . ' ' . $achternaam; ?&gt;
</pre>

<div class='strike'>
<pre data-enlighter-theme="beyond" data-enlighter-language="php" data-enlighter-linenumbers="false">
&lt;?php echo '$voornaam $achternaam'; ?&gt;
</pre>
</div>
</div>

## Werken URL parameters

De URL parameter kan ook gebruikt in een script.

<code>script.php?getal_1=100&getal_2=200</code>
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;p&gt;
  &lt;?php echo $_GET['getal_1"]; ?&gt; + 
  &lt;?php echo $_GET['getal_2"]; ?&gt; = 
  &lt;?php echo $_GET['getal_1"] + $_GET['getal_2"]; ?&gt;
&lt;/p&gt;
</pre>

<div class="shadow result">
<p>100 + 200 = 300</p>
</div>