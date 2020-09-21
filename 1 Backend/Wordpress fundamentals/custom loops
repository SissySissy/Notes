# custom loops

    if ( have_post() ) : while ( have_posts() ) :  the_post();

single post template, archive template. there are different types!!

it ends with **end while** and **end if**

## example of a custom loop

notice that the loop has been modified to have the personal query!

1. we check on which page we are, if not we are setting page to one (especially for archived)
2. then we set the arguments, notice that you can customize how many post per page
3. WP_query is an object class! that's why you use the syntax `$my_query->haveposts()` to access the method have_post()

    $paged = ( get_query_var( 'paged' ) ) ? get_query_var( 'paged' ) : 1;
    
    $args = array(
    	'post_type' => 'post',
    	'post_status' => 'publish',
    	'paged' => $paged,
    	'post_per_page => 5,
    	'orderby' => 'post_date',
    	'order' => 'DESC'
    );
    
    $my_query = new WP_Query( $args );
    
    if ( $my_query->have_posts()  ) : while ( $my_query->have_posts() ) :  $my_query->the_post();
    //
    endwhile; endif;


for **post_tag** and **cat**, you can use either the **slug** or the **numeric ID**

you can also filter the posts depending on the user role:  by adding extra conditions in the if statement

    if ( current_user_can ( 'edit_others-posts' ) && $my_query->have_posts() ) :
    	while ( $my_query->have_posts() ) :
    		$my_query->the_post();

### extra notes
'post_author' needs user ID
you can use filters through array
'cat' => array ('soccer, 'world-cup-2014', 34, 54 ); 

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTc3NDA3MjQxLDEwNDY0NDE3NF19
-->