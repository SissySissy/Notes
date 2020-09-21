

# PHP

## Basics

### Unique ID
    <?php $ID=uniqid(); ?>

### if else

    <?php if($variable){ ?>
    // code
    <?php } ?>
    
    <?php if($headerListTitle){echo $headerListTitle; }?>
### foreach

	<?php foreach($action_list_items As $cols): ?>
	<li>
		<?php foreach($cols As $col): ?>
		<?php
			$extra_classes = $col[1] ? $col[1] : '';
		?>
		<div class="action-list-col <?php echo $extra_classes; ?>">
			<?php echo $col[0]; ?>
		</div>
		<?php endforeach; ?>
	</li>
	<?php endforeach; ?>

### ternary operator

    $extra_classes = $col[1] ? $col[1] : '';

### echo array and key value in a foreach loop
setting the array
```
$scale_section_sort_options = $scale_section_sort_options ? $scale_section_sort_options : array(
	'display-option_standard' => 'Schlechteste',
	'order-by_best' => 'Beste',
	'order-by_change_pos' => 'Positive Veränderung',
	'order-by_change_neg' => 'Negative Veränderung',
	'order-by_group' => 'Gruppe',
	'order-by_topic' => 'Thema'
);
```
echoing the array
```
foreach($array as $key => $value) {
  <option value="<?php echo $key ?>"><?php echo $value ?></option>
}
```
### Php in a template

    //at the top
    <?php
	    $action_list_items = $action_list_items ? $action_list_items : array();
	 ?>
	
	// at the bottom, all variables set back to null 
    <?php $action_list_items = NULL; ?>
  
  
### get page tempalte name

You can get the filename of the page template that the post in the WordPress admin is set to using:

```text
$page template = get_post_meta( $post->ID, '_wp_page_template', true );
```
### replace string

    Input:  $subjectVal  = "It was nice meeting you. May you shine brightly."
            str_replace('you', 'him', $subjectVal)



## ACF

### Getting a field
option is the name of the page where the AFC or the field are set
	
from option page
	   

     $copyright = get_field('copyright', 'option');

from page

		$full_height = get_field('full_height');

### easier way to get subgroups:

    $navigation_content = $company_array['home'];
    
### getting a subfield from a group with get_sub_field
notare che metti direttamente il nome in have rows, non una variabile con get_field
	

    while( have_rows('wrapper_column')): the_row();
    		$image = get_sub_field('wrapper_column_image');
    		$map = get_sub_field('wrapper_column_map');
    		$slideshow = get_sub_field('wrapper_column_slideshow');
    
    		//get section image
    		$img_source = wp_get_attachment_image_src( $image['ID'] , $size = 'xxxl_size' )[0];
    		$img_sizes = $custom_full_container_width_sizes; // responsive image sizes
    		$img_srcset = esc_attr( wp_get_attachment_image_srcset( $image['ID']) ); // responsive image srcset
    		$img_alt_text = get_post_meta( $image['ID'], '_wp_attachment_image_alt', true );
    		$img_attributes = 'class="focus-' . get_field('image_focus', $bike_category->taxonomy . '_' . $bike_category->term_id) . '"'; // add attributes you like
    	endwhile;
    ?>


## Debugging

### echo something
is only for strings and not complex types! doesn't work x array!

    <?php echo $ID?>
    
### debug array: <pre>

    echo "<pre>";
    	print_r($var);
    	echo "</pre>";

### debug bool: var_dump

    <?php var_dump($format) ?>
var dump mostra true and false, senno se usi print_r ti mostra solo 1 se true e niente se false.



### debug in the console

add this file to function.php


	function console_log( $data ){
	echo '<script>';
	echo 'console.log('. json_encode( $data ) .')';
	echo '</script>';
	}


## Wordpress related

### current page slug

```
<?php 
    global $post;
    $post_slug = $post->post_name;
?>
```

### home url + additional parameters

    home_url(  string $path = '',  string|null $scheme = null )
    <?php  echo  esc_url( home_url(  '/'  )  )?>

Retrieves the URL for the current site where the front end is accessible.
`esc_url` is used to check and clean a URL.

### Wp post as array problem
It's not a normal array because you're actually retrieving an object.
so you want to go through it with key value pair and save or map the value to some variable using -> php syntax. 


    foreach ($originalArray as $key => $data) {
    	  $post_date = $data->post_date; // 2017-07-10 11:50:32
    }

Because to access data inside an object, use ->.

Ex: `$data['post_date'] to $data->post_date`
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTAxNTU4NTE2LDk0MDA0OTg1MywxNzQwMz
gyNTEsLTI5OTA2MDY0OSwtMTMzMDk2OTM3NywtMjgyMzgzMDcw
LDEwNjAwNTQwODksLTE2Njc5MjM4MCwyMDA2NjI4MjIzLC00Mj
kwOTM5ODQsNzQxNDIzODkyLDgyOTQ2ODU0MCwxMjAwMjcwMTMw
LC03MDI1NDIzMzIsLTUxMzgwNjAwNyw2ODcxODM1ODcsMTEyND
YyMDE0NCwtMTA3MDM5Nzg0NywxOTQ1MDgwNjQzLDczMDk5ODEx
Nl19
-->