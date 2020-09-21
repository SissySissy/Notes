# Tips for wordpress



#### get_the vs the_title

in wordpress get_ is the unprocessed data, while the_tilte is simply echoing!

#### Showing the menu in the admin panel

Basically, the menu are not out of the box, you have to add the theme support for those, add the function into inc.

it's better to rely on the location of the menu instead of the name, since it can be changed for other stuff. you hve to specify the location through the code and in the backend

- in the inc folder/admin mods

- Wp_register_menu_location function add

- add theme support (menus)

- Menu_settings locations



#### feature image

like the menu, you will need the theme support, is not out of the box

it's called something like image_mods

Inc/theme_setup.php





### posts

for articles, blogpost, works etc, they are under post! not single pages

and the custom template to modify them is named single.php

