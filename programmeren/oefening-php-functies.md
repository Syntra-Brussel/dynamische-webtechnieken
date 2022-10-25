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

Je kan kiezen uit rood, blauw, geel, groen en grijs.

### php_functies.php
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;?php
$zin = "Een zin in kleur.";

$kleuren_opties = ['blue', 'yellow', 'red'];

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

### Het resultaat
<div class="shadow result" style="background-color: red; color: white">
</div>