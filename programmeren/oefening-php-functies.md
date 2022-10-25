---
layout: template
title: 'OEFENING: Kleuren'
url: /programmeren/oefening-kleuren
collection: programmeren
---
<div class="highlight">
    <h3>Instructies</h3>
    <ul>
        <li>werk in het script <code>programmeren/kleuren_met_functie.php</code></li>
        <li>Zorg ervoor dat de de array <code>$kleuren_opties</code> kan uitgebreid worden met extra kleuren.</li>
    </ul>
    <h3>Tips</h3>
    <ul>
        <li>Gebruik de functie <a target="_blank" href="https://www.php.net/manual/en/function.rand.php"><code>rand($min, $max)</code></a> om een radon getal te bepalen tussen een ondergrens en een bovengrens.</li>
        <li>Gebruik de functie <a target="_blank" href="https://www.php.net/manual/en/function.explode.php"><code>explode($separator, $string)</code></a> om de woorden van een zin in een aray te plaatsen.</li>
        <li>Gebruik de functie <a target="_blank" href="https://www.php.net/manual/en/function.str-split.php"><code>str_split($string)</code></a> om elk karakter van een string in een aray te plaatsen.</li>
    </ul>
</div>

Je kan kiezen uit blauw, groen, en rood.

### php_functies.php
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;?php
$zin = "Een zin in kleur.";

$kleuren_opties = ['blue', 'green', 'red'];

function zinInRandomKleur($zin, $kleuren_opties) {
    //...
}

function woordenInRandomKleur($zin, $kleuren_opties) {
    //...
}

function lettersInRandomKleur($zin, $kleuren_opties) {
    //...
}
?&gt;

&lt;h1&gt;&lt;?php echo $zin; ?&gt;&lt;/h1&gt;
&lt;ul&gt;
&lt;li&gt;&lt;?php echo zinInRandomKleur($zin, $kleuren_opties); ?&gt;&lt;/li&gt;
&lt;li&gt;&lt;?php echo woordenInRandomKleur($zin, $kleuren_opties); ?&gt;&lt;/li&gt;
&lt;li&gt;&lt;?php echo lettersInRandomKleur($zin, $kleuren_opties); ?&gt;&lt;/li&gt;
&lt;ul&gt;
</pre>

### Een mogelijk resultaat.
<div class="shadow result">
<h1 style="color: black">Een zin in kleur.</h1>
<ul>
    <li><span style="color: blue">Een zin in kleur</span>.</li>
    <li><span style="color: blue">Een</span> <span style="color: green">zin</span> <span style="color: blue">in</span> <span style="color: red">kleur.</span></li>
    <li><span style="color: red">E</span><span style="color: green">e</span><span style="color: blue">n</span> <span style="color: green">z</span><span style="color: red">i</span><span style="color: blue">n</span> <span style="color: blue">i</span><span style="color: red">n</span> <span style="color: blue">k</span><span style="color: red">l</span><span style="color: green">e</span><span style="color: blue">u</span><span style="color: green">r</span><span style="color: blue">.</span></li>
</ul>
</div>