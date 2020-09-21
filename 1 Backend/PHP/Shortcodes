# Shortcodes

    <?php
    
      
    
    function  tel_func() {
    
    return  get_field('company_phone', 'option');
    
    }
    
    add_shortcode( 'tel', 'tel_func' );
    
      
    
    function  languages_func() {
    
    $langs = get_field('spoken_languages', 'option');
    
    ob_start();
    
    foreach($langs  as  $lang) {
    
    echo  '<span class="tag">' . $lang['language'] . '</span> ';
    
    }
    
    $content = ob_get_contents();
    
    ob_end_clean();
    
    return  $content;
    
    }
    
    add_shortcode( 'langs', 'languages_func' );
    
      
    
    function  address_func(){
    
    $address = [
    
    "name" => get_field('address_title', 'option') . "<br>" . get_field('address_name', 'option'),
    
    "streetAddress" => get_field('address', 'option'),
    
    "postalCode" => get_field('zip', 'option'),
    
    "addressLocality" => get_field('city', 'option'),
    
    ];
    
      
    
    ob_start();
    
    include(locate_template( '/_molecules/address/template.php' ));
    
    $content = ob_get_contents();
    
    ob_end_clean();
    
    return  $content;
    
    }
    
    add_shortcode( 'address', 'address_func' );
    
      
    
    function  hours_func(){
    
    ob_start();
    
    include(locate_template( '/_molecules/hours/template.php' ));
    
    $content = ob_get_contents();
    
    ob_end_clean();
    
    return  $content;
    
    }
    
    add_shortcode( 'hours', 'hours_func' );
    
      
    
    function  contact_func(){
    
    $contact = [
    
    "telephone" => get_field('company_phone', 'option'),
    
    "email" => get_field('company_email', 'option'),
    
    ];
    
      
    
    ob_start();
    
    include(locate_template( '/_molecules/contact/template.php' ));
    
    $content = ob_get_contents();
    
    ob_end_clean();
    
    return  $content;
    
    }
    
    add_shortcode( 'contact', 'contact_func' );
    
      
    
    function  tile_func(){
    
    include(locate_template( '/_molecules/tile/template.php' ));
    
    }
    
    add_shortcode( 'tile', 'tile_func' );
    
      
    
    ?>


- create that in INC named: `shortcodes.php`
- and in `function.php` add this line: 
  

	    /**
	    
	    * Add Shortcodes
	    
	    */
	    
	    require  get_stylesheet_directory() . '/inc/shortcodes.php';

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwMjgxNjIyNTUsODcwODc0NDg4XX0=
-->