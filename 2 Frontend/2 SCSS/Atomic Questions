
# Atomic Questions


## Buttons

they use lineheight so that buttons work ok with any text size and font family..


## Arrows 
from atomic load in your css rules the element arrow.
mostly the style is absolute, and causes some issues. you can put it back into flow by setting its position as relative:  


    	span	{
				@include arrow(right, currentColor, 8px, 2px, -1px, -8px, after);

				&::after {
					position: relative;
					display: inline-block;
				}

## Hero
doesn't work!

## Gallery in gutemberg and problems in Atomic


If styles don't work in gutemberg check the plugin that disables them
in more options, tool there is a flag that says:

- more tool
- then choose show gutemberg frontend styles


## brand doesn't work with normal logo set up in the menu page

    <?php
    	$brand_logo = get_field( 'company_brand', 'options' );
    	$brand_name = esc_attr( get_bloginfo( 'name', 'display' ) );
    	$brand_url = site_url('/');
    ?>
    
    <?php if ( $brand_logo ) : ?>
    	<a class="brand" href='<?php echo $brand_url; ?>' title='<?php echo $brand_name; ?>' rel='home'>
    			<img src='<?php echo $brand_logo['url']; ?>' alt='<?php echo $brand_name; ?>'>
    	</a>
    <?php else : ?>
    	<hgroup>
    		<h2 class='site-title shift'><a href='<?php echo esc_url( home_url( '/' ) ); ?>' title='<?php echo esc_attr( get_bloginfo( 'name', 'display' ) ); ?>' rel='home'><?php bloginfo( 'name' ); ?></a></h2>
    	</hgroup>
    <?php endif; ?>

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ2NTE4MTQ2OSwtMTc2NTg0NjE5NCwtMT
UzODcyNDYwNSwxMjA3MTk4MzQ5XX0=
-->