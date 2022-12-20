---
layout: template
title: Eigen widget zone
url: /wordpress/eigen-widget-zone
collection: wordpress
---
Het thema <em>twentytwentyone</em> heeft 1 widget zone aan boord. Dat is de <em>footer</em> widget zone.

Het is uiteraard mogelijk om eigen widget zones toe te voegen.

Daarvoor moeten twee dingen gebeuren:
1. de widget registreren binnen Wordpress
2. de widget opnemen in de template

## Widget registreren binnen Wordpress

Binnen de <code>functions.php</code> voeg je openieuw een functie toe die via <code>add_action('widgets_init', '<em>functienaam</em>')</code> wordt uitgevoerd.

<pre>
<?php
function top_sidebar_init() {
    register_sidebar( array(
        'name' => 'Top',
        'id' => 'top-sidebar',
        'description' => 'Top sidebar verschijnt bovenaan, onder de header.',
        'before_widget' => '<div id="%1$s" class="xxx site-top %2$s"><div class="site-top-content">',
        'after_widget' => '</div></div>',
    ) );
 } 
 
add_action( 'widgets_init', 'top_sidebar_init' );
&gt;
</pre>

De functie <code>register_sidebar()</code> is de functie om een eigen sidebar toe te voegen binnen Wordpress. Ze wordt via beschikbaar via de "Weergave" > "Widgets".

De parameters via de functie spreken wel voor zich:
* <code>name</code>: De naam van de widget in de Wordpress admin
* <code>description</code>: De omschrijving van de widget in de Wordpress admin
* <code>before_widget</code>: De HTML die net boven de widget zone verschijnt
* <code>after_widget</code>: De HTML die net onder de widget zone verschijnt

De HTML voor en na de widget zijn bijvoorbeeld elementen om de layout te bepalen.

## Widget opnemen in de template

In het volgende hoofdstuk gaan we dieper in op de template architectuur. 

Voor nu is het belangrijk te weten dat je template bestanden die je wil gaan aanpassen vanuit het <em>twentytwentyone</em> kopieert naar <em>child theme</em>.