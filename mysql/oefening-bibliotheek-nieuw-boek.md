---
layout: template
title: 'OEFENING: Nieuw boek'
url: /mysql/oefening-bibliotheek-nieuw-boek
collection: mysql
---

<div class="highlight">
    <h3>Instructies</h3>
    <ul>
        <li>werk in het script <code>mysql/nieuw_boek.php</code></li>
        <li>Je kan starten vanaf <a target="_blank" href="nieuw_boek.html">nieuw_boek.html</a>.</li>
    </ul>
</div>

Via een formulier kan een boek toegevoegd worden.

### Bij de start:
<div class="shadow result">
  <h1 style="color: #000">Nieuw boek</h1>
  <form>
      <table>
          <tr>
              <td>Titel *</td>
              <td><input required type="text" name="titel" value="Het ABC van het DEF" /></td>
          </tr>
          <tr>
              <td>Auteur *</td>
              <td><input required type="text" name="auteur" value="Bert Jansen" /></td>
          </tr>
          <tr>
              <td>Uitgeverij *</td>
              <td><input required type="text" name="uitgeverij" value="Syntra Brussel" /></td>
          </tr>                
          <tr>
              <td>Genre * </td>
              <td><input required type="text" name="genre" value="Absurd" /></td>
          </tr>    
          <tr>
              <td>Aantal pagina's *</td>
              <td><input required type="number" name="aantal_paginas" value="101" /></td>
          </tr>         
          <tr>
              <td>Jaar van uitgave *</td>
              <td><input required type="number" name="jaar_van_uitgave" value="2022" /></td>
          </tr>                                              
          <tr>
              <td>Korte inhoud</td>
              <td><textarea name="korte_inhoud">Een boek die u weg wijs maakt in het het ABC van de DEF.</textarea></td>
          </tr>                                                                                          
      </table>
      <input type="submit" value="Toevoegen" />
  </form> 
</div>

### Na het invoeren:
<div class="shadow result">
  <h1 style="color: #000">Nieuw boek</h1>

  <p>Boek <strong>'Het ABC van het DEF'</strong> van <strong>Bert Jansen</strong> werd toegevoegd.</p>
 
</div>