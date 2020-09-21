# Basic concepts


how to code like a wordpress nijna ++ 

## WP_Query

is a class defined in wp-includes/query.php
is the primary mean to create custom loop

## The "loop" in wordpress

    if ( have_post() ) : while ( have_posts() ) ) :  the_post();
A post content with this syntax is usually defined as a loop

## $post
only contains data if it's in the loop

## $wp_query
is a global variable that stores data from the current query in the Loop
the the WP_Query is instantiate, this will be part of it

## post_meta
custom fields saved for a post in the wp_postmeta database table
post can have meta data associate with it stored in other database. by ID
wp, and other plugins creates some of it, you can create custom of it.

## taxonomy
a means of grouping posts together
there are 2 types: **category** and **post_tag**(non hierarchical)
custom taxonomy can be created for just certain posts

## term
an item in a taxonomy
eg: if the taxonomy is genre, the terms can be jazz. rock, electronic for a song **post type**

## post types
a type of content in wp
ex: pages and posts, but also media are post types

## Query string, our url string
the part of a URL containing data that does not fit conveniently into a hierachical path structure
the query string commonly incldes fields added to a base URI or Web browser or other client applcation, for example an html form

##  $wpdb

wordpress global
an instantiation of the wpdb class. it is by default instantiated to talk to the wordpress database
if you want to do direct db queries, you will use it to sanitaze data correctly.
read about that in the wordpress codex

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM5OTIwNzc3M119
-->