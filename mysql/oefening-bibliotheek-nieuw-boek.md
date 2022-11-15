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
        <li>Je kan starten vanaf <a target="_blank" href="overzicht_boeken.html">nieuw_boek.html</a>.</li>
    </ul>
</div>

Via een formulier kan een boek toegevoegd worden.

<div class="shadow result">
  <h1 style="color: #000">Nieuw boek</h1>
  <form>
      <table>
          <tr>
              <td>Titel</td>
              <td><input type="text" name="titel" /></td>
          </tr>
          <tr>
              <td>Auteur</td>
              <td><input type="text" name="auteur" /></td>
          </tr>
          <tr>
              <td>Uitgeverij</td>
              <td><input type="text" name="uitgeverij" /></td>
          </tr>                
          <tr>
              <td>Genre</td>
              <td><input type="text" name="genre" /></td>
          </tr>    
          <tr>
              <td>Aantal pagina's</td>
              <td><input type="number" name="aantal_paginas" /></td>
          </tr>         
          <tr>
              <td>Jaar van uitgave</td>
              <td><input type="number" name="jaar_van_uitgave" /></td>
          </tr>                                              
          <tr>
              <td>Korte inhoud</td>
              <td><textarea name="korte_inhoud"></textarea></td>
          </tr>                                                                                          
      </table>
      <input type="submit" value="Toevoegen" />
  </form> 
</div>