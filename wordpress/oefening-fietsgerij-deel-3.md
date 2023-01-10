---
layout: template
title: 'OEFENING: Fietsgerij (3)'
url: /wordpress/oefening-fietsgerij-deel-3
collection: wordpress
---

## Voorbereiding
1. Installeer de "Custom Post Type UI" plugin.

## Instructies
1. Maak een "dienst" Custom Post Type. 
2. Ga naar PHPmyAdmin en klik in de <code>speeltuin</code> database door naar de <code>wp_posts</code> tabel.
3. Filter de velden met het <code>post_type</code> "post".
4. Wijzig het <code>post_type</code> van "post" naar "dienst".
5. In het bestand index.php (in de child theme folder) wijzig je volgende code.

### Van

<pre>
&lt;?php
if ( have_posts() ) {

    // Load posts loop.
    while ( have_posts() ) {
        the_post();

        get_template_part( 'template-parts/content/content', get_theme_mod( 'display_excerpt_or_full_post', 'excerpt' ) );
    }

    // Previous/next page navigation.
    twenty_twenty_one_the_posts_navigation();

} else {

    // If no content, include the "No posts found" template.
    get_template_part( 'template-parts/content/content-none' );

}
?&gt;
</pre>  

### Naar

<pre>
&lt;?php
// Define args
$args = array('post_type' => 'dienst');

// Execute query
$cpt_query = new WP_Query($args);

// Wanneer een posts van een type 'dienst' zijn.
if ($cpt_query->have_posts()) {

    // Loop over de verschillende posts.
    while ( $cpt_query->have_posts() ) {
        $cpt_query->the_post();

        get_template_part( 'template-parts/content/content', get_theme_mod( 'display_excerpt_or_full_post', 'excerpt' ) );
    }

    // Toon vorige/volgend pagina navigatie.
    twenty_twenty_one_the_posts_navigation();

} else {

    // Wanneer geen posts toon de "Geen posts gevonden" template.
    get_template_part( 'template-parts/content/content-none' );

}
?&gt;
</pre>    