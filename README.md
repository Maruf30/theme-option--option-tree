# theme-option--option-tree


<?php

add_action( 'admin_init', 'custom_theme_options', 1 );

function custom_theme_options() {

  $saved_settings = get_option( 'option_tree_settings', array() );
  

  $custom_settings = array(
    'sections'        => array(
      array(
        'id'          => 'general',
        'title'       => 'Site Settings'
      )
    ),
    'settings'        => array(
      array(
        'id'          => 'logo_text',
        'label'       => 'Logo Text',
        'desc'        => 'Use H1, H2, H3 tag',
        'type'        => 'textarea',
        'section'     => 'general'
      ), 
      array(
        'id'          => 'footer_text',
        'label'       => 'Footer Text',
        'type'        => 'textarea',
        'section'     => 'general'
      )
    )
  );

  if ( $saved_settings !== $custom_settings ) {
    update_option( 'option_tree_settings', $custom_settings ); 
  }
  
}
 ?>
