---
layout: template
title: 'OEFENING: Rekenen'
url: /programmeren/oefening-rekenen
collection: programmeren
---
<div class="highlight">
    <h3>Instructies</h3>
    <ul>
        <li>werk in het script <code>programmeren/rekenen_met_functies.php</code></li>
        <li>Herschrijf de codes van <a href="/dynamische-webtechnieken/programmeren/oefening-rekenen">deze oefening</a> met functies.</li>
        <li>
            <ul>
            <li>Schrijf een functie aparte voor elke bewerking</li>
            <li>breng alle bewerkingen vervolgens samen in één functie <code>rekenen($bewerking, $getal_1, $getal_2)</code></li>
            </ul>
        </li>            
    </ul>
</div>

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

### Resultaat na het versturen van het formulier wanneer niet beide getallen zijn opgegeven
<div class="shadow result">
    <form>
    <ul>
    <li>Getal 1: <input type="number" value="" /></li>
    <li>Getal 2: <input type="number" value="" /></li>
    </ul>
    <input type="submit" value="Verstuur" />
    </form>
    <hr />
    <p>Voer twee getallen in voor je op 'Verstuur' klikt.</p>
</div>

### Resultaat na het versturen van het formulier met twee getallen
<div class="shadow result">
    <form>
    <ul>
    <li>Getal 1: <input type="number" value="20" /></li>
    <li>Getal 2: <input type="number" value="10" /></li>
    </ul>
    <input type="submit" value="Verstuur" />
    </form>
    <hr />
    <p>20 + 10 = 30</p>
    <p>20 - 10 = 10</p>
    <p>20 x 10 = 200</p>
    <p>20 x 10 = 2</p>
</div>