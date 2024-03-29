---
layout: template
title: Shortcode
url: /wordpress/shortcode
collection: wordpress
links:
  - url: https://wordpress.org/plugins/contact-form-7/
  - url: https://wordpress.org/plugins/contact-form-entries/
  - url: https://developer.wordpress.org/reference/functions/do_shortcode/
---

## Inleiding

Het Wordpress eco systeem bukt van de plugins om de mogelijkheden van je Wordpress website uit te breiden. 

Er zijn plugin beschikbaar om <strong>slideshows, formulieren, foto galerijen, ...</strong> in te voegen op je pagina.

Na het installeren en configureren van de inhoud kan je via een <em>shortcode</em> stukje specifieke code van een plugin gaan invoegen. 

De shortcode is eigenlijk uitgevonden voor niet-developers. Zodat ook zij 'eenvoudig' bepaalde stukjes code kunnen gaan invoegen via de Wordpress Editor.

Een developer kan die stukjes code ook gaan invoegen via de <code>do_shortcode()</code> functie in PHP.

## Voorbereiding

We gaan <em>shortcodes</em> gebruiken aan de hand van een contact formulier via de <strong>contact form 7</strong> plugin.

Een <strong>contactformulier</strong> is ziets dat op elke websites voor komt maar toch al iets complexer in mekaar steekt en waarvoor dus een plugin beschikbaar is. 

Via de link onderaan kan je de plugin installeren in de <code>wp-content/plugins</code> folder.

## Contactformulier tonen

### De Shortcode

Het tonen van het formulier binnen de website kan door het gebruik van de <strong>shortcode</strong>. Het is een notatie om, in dit geval, het formulier te bouwen. 

Voor het contactformulier dat via de plugin is gemaakt ziet die er (ongeveer) zo uit:
<pre>
[contact-form-7 id="55" title="Contact form 1"]
</pre>

### Shortcode gebruiken
- je kan die <em>shortcode</em> plakken in een Wordpress editor (binnen de inhoud van een bericht of binnen een widget)
- je kan de  <em>shortcode</em> ook via een PHP template inladen

Wanneer de ID van de contact pagina "10" is zou je dus het specifiek op die pagina het contactformulier kunnen invoegen:

#### <code>page-10.php</code>

<pre>
&lt;?php
get_header();
?&gt;

&lt;?php get_template_part( 'template-parts/content/contact' ); ?&gt;

&lt;?php
get_footer();
?&gt;
</pre>

#### <code>template-parts/content/contact.php</code>

<pre>
&lt;div class="formulier"&gt;
&lt;?php echo do_shortcode('[contact-form-7 id="55" title="Contact form 1"]'); ?&gt;
&lt;/div&gt;
</pre>

## Contactformulier configureren
De plugin heeft geen grafische interface maar het voorbeeld wijst zichzelf wel uit. En via de knoppen bovenaan kan je nieuwe velden toevoegen.

<pre>
<label> Your name
    [text* your-name autocomplete:name] </label>

<label> Your email
    [email* your-email autocomplete:email] </label>

<label> Subject
    [text* your-subject] </label>

<label> Your message (optional)
    [textarea your-message] </label>

[submit "Send"]
</pre>

Je kan hier:
- labels vertalen
- Extra velden toeveogen (via de knoppen bovenaan of via de editor)

Het *-tje staat voor een verplicht veld

### GDPR

Iedereen heeft ongetwijfeld al van de GDPR wetgeving gehoord? Die maakt dat je als gebruiker uitdrukkelijk toestemming moet geven om informatie op een website te verwerken.

Om die reden is het ook verplicht om gebruikers uitdrukkelijk de toestemming te vragen voor het werken met de peroonsgegevens. 

In het formulier is het daarom belangrijk een extra checkbox toe te voegen voor die toestemming.

<pre>
[acceptance akkoord]Ja, ik ga akkoord met het <a href="#">privacybeleid</a>[/acceptance]
</pre>

## Inzendingen
Een inzending via een contactformulier wordt in Wordpress niet standaard bewaard. Via de <strong>plugin "Contact form entries"</strong> kan je dat toch verwezelijken.
