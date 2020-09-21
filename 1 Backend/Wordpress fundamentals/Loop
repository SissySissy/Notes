# The "loop" in wordpress

**WP_Query** instantiate always this function

    if ( have_post() ) : while ( have_posts() ) ) :  the_post();

**if have post**: check if any post exists in a query.
**the_post();** this function prepares the data to be used in the template.
you could skip this, but then you would call the data like this: prepares the $post global

    $post -> ID  $post -> post_title
    instead of the_ID(),  the_tilte().


## Query strings in loops

the loop works by query strings
if the post id is 123
the query string is ?p=123
even when you hide it

    ?cat=music
    ?post_type=article
    ?s=search phrase

**htaccess** contains the data to decide what to show.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMyODIwMjA3MF19
-->