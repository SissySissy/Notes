# Menu

## complex menu with active link

    $array_menu =  wp_get_nav_menu_items('menu name',  $args);
    
    // calling the right menu depending on the parent's page
    
    if($array_menu){
    
	    $menu =  array();
    
	    $current_page_id =  get_queried_object_id();
    
	    foreach ( $array_menu as  $m ) {
    
    	if (empty($m->menu_item_parent)) {
    
    			$menu[$m->ID] =  array();
    
    			$menu[$m->ID]['title'] =  $m->title;
    
    			$menu[$m->ID]['url'] =  $m->url;
    
    			$menu[$m->ID]['classes'] = ($m->object_id ==  get_queried_object_id() ?  'active-link'  : false);
    
    		}
    
	    }
    
    }


## easier menu

	$footer_menu =  wp_get_nav_menu_items('footer menu');
	
	<?php	if($footer_menu){ ?>
			<div class="footer-impressum">
				<?php
					foreach ($footer_menu as $key => $data) {
					$page_title = $data->title; 
					$url = $data->url; 
				?>
					<a href="<?php echo $url; ?>"><?php echo $page_title; ?></a>
				<?php } ?>
			</div>
		<?php } ?>
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDU5MjAyMDAyLDc2NDM1OTYwNSwzNzM3OD
QxMzddfQ==
-->