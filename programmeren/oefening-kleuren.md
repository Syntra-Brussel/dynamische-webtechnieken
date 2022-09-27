---
layout: template
title: 'OEFENING: Kleuren'
url: /programmeren/oefening-kleuren
collection: programmeren
---
<div class="highlight">
    <h3>Instructies</h3>
    <ul>
        <li>werk in het script <code>programmeren/kleuren.php</code></li>
        <li>Schrijf de HTML eerst statisch. Maak die daarna dynamisch door er <code><?php ... ?></code> aan te te voegen.</li>
    </ul>
</div>

Je kan kiezen uit rood, blauw, geel, groen en grijs.

### Resultaat voor het versturen van het formulier
<div class="shadow result">
    <form>
    <ul>
    <li>Voorgrond keur <select><option></option></select></li>
    <li>Achtergrond keur <select><option></option></select></li>
    </ul>
    <input type="submit" value="Toon" />
    </form>
</div>

### Resultaat na het versturen van het formulier
<div class="shadow result" style="background-color: yellow; color: blue">
    <form>
    <ul>
    <li>Voorgrond keur <select><option>blauw</option></select></li>
    <li>Achtergrond keur <select><option>geel</option></select></li>
    </ul>
    <input type="submit" value="Toon" />
    </form>

    <h1 style="color: blue">Lorem ipsum dolor sit amet</h1>
    <p>Mauris vitae interdum est. Sed at fringilla massa. Vestibulum a rutrum velit, quis mattis mi. Donec dui ex, pulvinar vitae ante ac, pharetra suscipit est. Nullam laoreet suscipit tellus ac vestibulum. Nunc finibus posuere metus eu elementum. Ut ut rutrum nibh, vitae luctus enim. Sed nisl sapien, dapibus nec nisl nec, sollicitudin tincidunt nisl. Nullam pellentesque lobortis posuere. Duis cursus a risus a elementum. Donec vitae risus sed leo gravida lobortis sit amet eget erat.</p>
</div>

### Resultaat na het versturen van het formulier
<div class="shadow result" style="background-color: red; color: white">
    <form>
    <ul>
    <li>Voorgrond keur <select><option>wit</option></select></li>
    <li>Achtergrond keur <select><option>rood</option></select></li>
    </ul>
    <input type="submit" value="Toon" />
    </form>

    <h1 style="color: white">Lorem ipsum dolor sit amet</h1>
    <p>Mauris vitae interdum est. Sed at fringilla massa. Vestibulum a rutrum velit, quis mattis mi. Donec dui ex, pulvinar vitae ante ac, pharetra suscipit est. Nullam laoreet suscipit tellus ac vestibulum. Nunc finibus posuere metus eu elementum. Ut ut rutrum nibh, vitae luctus enim. Sed nisl sapien, dapibus nec nisl nec, sollicitudin tincidunt nisl. Nullam pellentesque lobortis posuere. Duis cursus a risus a elementum. Donec vitae risus sed leo gravida lobortis sit amet eget erat.</p>
</div>