---
layout: template
title: 'OEFENING: Factuur'
url: /programmeren/oefening-factuur
collection: programmeren
---

<div class="highlight">
    <h3>Instructies</h3>
    <ul>
        <li>werk in het script <code>programmeren/factuur.php</code></li>
        <li>Start vanaf het bestaande <a target="_blank" href="factuur.html">factuur.html</a>. Maak die dynamisch door er <code><?php ... ?></code> fragmenten aan te te voegen.</li>
    </ul>
</div>

Je krijgt de array's alvast die de informatie bevatten om de factuur op te maken.

#### gegevens.php
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;?php 
$bedrijfsgegevens = [
  'logo' => 'factuur-logo.png', 
  'naam' => 'Logo BV', 
  'straat' => 'Dorpsstraat 1', 
  'plaats' => '2910 Essen', 
];

$klantgegevens = [     
  'naam' => 'Francis Van Hooren', 
  'straat' => 'Grote Markt 10', 
  'plaats' => '2000 Antwerpen', 
  'land' => 'België', 
];

$factuurgegevens = [
  'jaar' => '2016',
  'nummer' => '1',
  'datum' => '05/01/2016',
];
?&gt;
</pre>

#### factuur.php
<pre data-enlighter-theme="beyond" data-enlighter-language="php">
&lt;html&gt;
  &lt;head&gt;
  ...
  &lt;/head&gt;
  &lt;body&gt;
  ...
  &lt;/body&gt;
&lt;/html&gt;
</pre>

<div class="shadow result">
      <table width="100%">
            <tr>
                <td>
                    <div><img src="images/factuur-logo.png" /></div>
                    <div>Logo BV</div>
                    <div>Dorpstraat 10</div>
                    <div>2910 Essen</div>
                </td>
                <td>
                    <div>Francis Van Hooren</div>
                    <div>Koning Filip Laan 10</div>
                    <div>2000 Antwerpen</div>
                    <div>Belgë</div>
                </td>
            </tr>
        </table>
        
        <hr />
        
        <div><strong>FACTUUR 2016/1</strong></div>
        <div><strong><u>Datum:</u> 05/01/2016</strong></div>
     
        <hr />
        
        <table border="0" width="100%">
            <tr>
                <td><strong>Omschrijving</strong></td>
                <td><strong>Aantal</strong></td>
                <td><strong>BTW %</strong></td>
                <td><strong>Prijs</strong></td>
                <td><strong>Totaal</strong></td>
            </tr>
            <tr>
                <td valign="top">Webhosting - domeinnaam.be
                    <ul>
                    <li>1 GB webruimte</li>
                    <li>1 database van 250 MB</li>
                    <li>1 e-mail adres</li>
                    <li>onbeperkte bandbreedte</li>
                    </ul>
                    <u>Looptijd:</u> 01/01/2016 - 31/12/2017
                </td>
                <td valign="top">1</td>
                <td valign="top">21%</td>
                <td valign="top">€ 169</td>
                <td valign="top">€ 169</td>
            </tr>
            <tr>
                <td valign="top">Domeinnaam - domeinnaam.be
                    <ul>
                        <li>registiratie/verlenging domeinnaam</li>
                    </ul>
                    <u>Looptijd:</u> 01/01/2016 - 31/12/2017
                </td>
                <td valign="top">1</td>
                <td valign="top">21%</td>
                <td valign="top">€ 25</td>
                <td valign="top">€ 25</td>
            </tr>
            <tr>
                <td colspan="2"></td>
                <td>Subtotaal</td>
                <td></td>
                <td>€ 194</td>
            </tr>
            <tr>
                <td colspan="2"></td>
                <td>+BTW</td>
                <td></td>
                <td>€ 40,70</td>
            </tr>
            <tr>
                <td colspan="2"></td>
                <td>Totaal:</td>
                <td></td>
                <td>€ 234,74</td>
            </tr>
            <tr>
                <td colspan="3"></td>
                <td>vervaldag:</td>
                <td>15/01/2016</td>
            </tr>
        </table>
        <div>
            <table border="0" width="100%">
                <tr>
                    <ul><li><u>Algemene voorwaarden</u></li>
                        <li>Al onze factuuren zijn betaalbaar op de vervaldag welke op defactuur in weergegeven.</li>
                        <li>Bij gebreek aan betaling behouden wij ons het recht voor, het bedrag te laten innen op kosten van de client</li>
                        <li>In geval van betwisting zijnenkel de rechtbanken van Antwerpen bevoegd</li>
                        <li>Bij niet betalen binnen de vastgestelde termijn zal een interest Ã  rato van 15% worden aangerekend</li>
                    </ul>
                </tr>
            </table>
        </div>
</div>