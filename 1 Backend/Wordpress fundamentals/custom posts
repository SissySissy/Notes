## Custom postTypes

    register_post_type( $post_type, $args);

one of the first funciton that wp launches, because it's hooked to init


To create a custom post type for any particular theme on WordPress, navigate to **function.php** file from your WordPress theme directory then add the following code to it.
When you create custom post types, it is necessary to use **init** for the hook in **add_action()**. The **register_post_type()** function takes the arguments.

    /* Custom Post Type Start */

	function create_posttype() {
	register_post_type( 'news',
	// CPT Options

	array(
	  'labels' => array(
	   'name' => __( 'news' ),
	   'singular_name' => __( 'News' )
	  ),
	  'public' => true,
	  'has_archive' => false,
	  'rewrite' => array('slug' => 'news'),
	 )
	);
	}
	// Hooking up our function to theme setup
	add_action( 'init', 'create_posttype' );

	/* Custom Post Type End */

## arguments

```php 
/*Custom Post type start*/

	function cw_post_type_news() {

	$supports = array(
	'title', // post title
	'editor', // post content
	'author', // post author
	'thumbnail', // featured images
	'excerpt', // post excerpt
	'custom-fields', // custom fields
	'comments', // post comments
	'revisions', // post revisions
	'post-formats', // post formats
	);

	$labels = array(
	'name' => _x('news', 'plural'),
	'singular_name' => _x('news', 'singular'),
	'menu_name' => _x('news', 'admin menu'),
	'name_admin_bar' => _x('news', 'admin bar'),
	'add_new' => _x('Add New', 'add new'),
	'add_new_item' => __('Add New news'),
	'new_item' => __('New news'),
	'edit_item' => __('Edit news'),
	'view_item' => __('View news'),
	'all_items' => __('All news'),
	'search_items' => __('Search news'),
	'not_found' => __('No news found.'),
	);

	$args = array(
	'supports' => $supports,
	'labels' => $labels,
	'public' => true,
	'query_var' => true,
	'rewrite' => array('slug' => 'news'),
	'has_archive' => true,
	'hierarchical' => false,
	);
	register_post_type('news', $args);
	}
	add_action('init', 'cw_post_type_news');

```

public
	show_ui
	publicly_queryable
	exclude_from_search
	show_in_nav_menu

supports
	title
	editor
	thumbnail
	excerpt
	comments
	trackbacks
	custom-fields
	page-attributes
	revisions
	post-formats

hierarchical
	true // can have child post

has_archive
	true / false it's created automatically
	
can_export

taxonomies
	array( 'category', post_tag);

menu_icon
	url to imge
	or dashicon

show_in_menu

show_in_admin_bar
	for new subnav

capability_Type

capabilities
	array

query_var
	query_Var => 'some-slug'

rewrite
	to allow pretty permalinks
	and define different slug
	pages
	feeds

labels
	when the word 'item' is used, it usually refers to the label that you use
	when items is plural, it indicates there are more labels used, array
	so it's good practice, to define both
		name ( in plural form)
		singular_name
		menu_name
		...

archive
	for single custom post type and archives they check if
	single-{post_type}.php exist if not, they use the standard single.php


## Create a Template and Fetching List

Once, you have developed the code, your next task will be to create a new file called **template-news.php** and place it in your theme folder. As soon as you have created this file, add the following code to it.

```php 
<?php
   /*Template Name: News*/
   get_header();
   query_posts(array(
      'post_type' => 'news'
   )); ?>
   <?php
   while (have_posts()) : the_post(); ?>
   <h2><a href="<?php the_permalink() ?>"><?php the_title(); ?></a></h2>
   <p><?php the_excerpt(); ?></p>
   <?php endwhile;
   get_footer();
?>
```
### Confused between choosing the theme &

## Select a Template

Now create a new page called **News** from the **Pages** option in your WordPress dashboard and access it. You can see a Template option available in **Page Attributes** on the right side of your screen. Select the new template **News** and then click the update button.


## Add Menu for Custom Post Type

To add your new custom post type as a part of the Menu options on your WordPress website, navigate to **Appearance → Menus** and add the News page to your main menu. This step is necessary as it will display a navigational link to our newly created WordPress custom post type, News.

## Display Detail Page of Custom Post Type

We also need to create a detail page for custom post types. To do so, we just need to add a new file called **single-news.php** which is located in your WordPress theme and then add the following code to it.
```php
<?php
get_header();
/* Start the Loop */
while (have_posts()) : the_post();
   get_template_part('template-parts/post/content', get_post_format());
endwhile; // End of the loop.
get_footer();
?>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg2MTAyNzU0MSwyMDAzMzM5MzM2LDE0NT
U5MDE3NywtNTc0NzM4XX0=
-->