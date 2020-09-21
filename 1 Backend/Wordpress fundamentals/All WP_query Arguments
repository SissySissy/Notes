#WP_Query arguments

## Authors

author: author id
author_in array of author ID
author_not_in 

## category

    cat //specific category id
    category_name

    category_and
    category_in
    category_not_in

 those three are arrays
 you can also use minus to exclude

     $query = new WP_Query('cat=-12, -34, -56');

## tag

     tag //retrieves the tag slug
     tag_id
    tag_and
     tag_in
     tag_not_in
    
     tag_slug_and
     tag_slug_in

you can use + to concatenate tags

     $query = new WP_Query('tag=bread+baking+recipe');


## taxonomy

simple taxonomy query
 $query = new WP_Query('taxonomy=term');


## search

you can use `s` to indicate search function

## posts and pages 

p //post id
page_id //page id
name // post slug
post_parent // parent page id
post_parent_in
post_parent_not_in

post_in
post_not_in

## passwords
has_password //true false null
post_password // string, shows post only with that password


## post type

you can register some yourself

post_type
	post
	page
	revision
	attachment
	nav_menu_item
	any

## status

publish
pending
draft
auto-draft
future
private
inherit
trash

## pagination

nopaging // display all post if true
posts_per_page // -1 is all posts
posts_per_archive_page
offset // how many post per a query to pass over. !! breaks normal pagination
paged // the page number of current page
ignore_sticky_posts 

## order and orderby

ASC //ascending
DESC // desceding highest to lowers

orderby
	none
	id
	author
	title alphabetically
	name
	type
	date
	modified // date last modified
	parent
	rand // random
	comment_count
	menu_order
	meta_value // if meta key is passed to query
	meta_value_num
	post_in

## date

year
monthnum
w /7 numeric week
day
hour
minute
second
m // year month  displayd like this 201502
date_query => array() for custom date dsplay

## meta ?

for more complex queries
meta_key
meta_value
meta_value_num
meta_compare

meta_query => array()
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwMzY5MDk4NDddfQ==
-->