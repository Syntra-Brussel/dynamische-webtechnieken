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
        <li>Herschrijf de PHP code van <a href="/dynamische-webtechnieken/programmeren/oefening-kleuren">deze oefening</a> met een functies en lussen.</li>
    </ul>
</div>

Je kan kiezen uit blau<, groen, en rood.

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
<h1>Een zin in kleur.</h1>
<ul>
    <li><span style="color: blue">Een zin in kleur</span>.</li>
    <li><span style="color: blue">Een</span> <span style="color: green">zin</span> <span style="color: blue">in</span> <span style="color: red">kleur.</span></li>
    <li><span style="color: red">E</span><span style="color: green">e</span><span style="color: blue">n</span> <span style="color: green">z</span><span style="color: red">i</span><span style="color: blue">n</span> <span style="color: blue">i</span><span style="color: red">n</span> <span style="color: blue">k</span><span style="color: red">l</span><span style="color: green">e</span><span style="color: blue">u</span><span style="color: green">r</span><span style="color: blue">.</span></li>
</ul>
</div>