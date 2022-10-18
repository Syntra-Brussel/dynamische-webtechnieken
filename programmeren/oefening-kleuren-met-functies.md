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
        <li>Herschrijf de PHP code van <a href="/dynamische-webtechnieken/programmeren/oefening-kleuren">deze oefening</a> met een functies.</li>
    </ul>
</div>

Je kan kiezen uit rood, blauw, geel, groen en grijs.

### Resultaat voor het versturen van het formulier
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
    &lt;html&gt;
        &lt;head&gt;
            &lt;title&gt;Kleuren</title&gt;
        &lt;/head&gt;
        &lt;body style="&lt;?php echo kleuren(); ?&gt;"&gt;
        &lt;form action="kleuren.php" method="POST"&gt;
            &lt;ul&gt;
                &lt;li&gt;Voorgrond keur 
                    &lt;select name="voorgrond_kleur"&gt;
                        &lt;option&gt;&lt;/option&gt;
                        &lt;?php echo opties(); ?&gt;
                    &lt;/select>
                &lt;/li>
                &lt;li>Achtergrond keur 
                    <select name="achtergrond_kleur">
                        &lt:option&gt;&lt;/option&gt;
                        &lt;?php echo opties(); ?&gt;
                    &lt;/select&gt;
                &lt;/li&gt;
            &lt;/ul&gt;
            &lt;input type="submit" value="Toon" /&gt;
        &lt;/form&gt;

        
        &lt;h1&gt;Lorem ipsum dolor sit amet&lt;/h1&gt;
        &lt;p&gt;
        Mauris vitae interdum est. Sed at fringilla massa. Vestibulum a rutrum velit, quis mattis mi. Donec dui ex, pulvinar vitae ante ac, pharetra suscipit est. Nullam laoreet suscipit tellus ac vestibulum. Nunc finibus posuere metus eu elementum. Ut ut rutrum nibh, vitae luctus enim. Sed nisl sapien, dapibus nec nisl nec, sollicitudin tincidunt nisl. Nullam pellentesque lobortis posuere. Duis cursus a risus a elementum. Donec vitae risus sed leo gravida lobortis sit amet eget erat.
        &lt;/p&gt;

        &lt;/body&gt;
    &lt;/html&gt;
</pre>