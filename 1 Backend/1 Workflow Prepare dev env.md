# Starting Dev Env for a new project



## 1 Existing Repository

1. Start Docker app

2. Run wizzard (Y on create host entry,  *same name as bitcubket repo*!!)

3. ```sudo nano /etc/hosts```, add entry projectName.site 127.0.0.1

4. in docker config add also the new hosting (if you say N on wizzard host, root folder name is same) Docker folder/ config / hosts/ default.conf

5. add .htaccess.   ```cp .htaccess ../meer/.htaccess```

6. restart docker apache container (only after modifying hosts)

7. add missing neat folder in the wp-content/theme/atomic/sass 

8. add plugins and uploads folders (from the dev folder or from FileZilla)

9. load database with `wp db import name.sql` in main project folder (export it from Cyon or ask for local developer copy)

10. SUPER IMPORTANT run `wp search-replace 'samichlous-schmutzli.ch' 'samichlous.site' --dry-run` for `'https://' 'http://'` and `'site.ch' 'site.site'`. this is important to avoid auto routing in mac

11. if it doesn't have atomic, use git clone of the repo and run npm install

12. create a user account `wp user create silvia silvia@duotones.ch --role=administrator`

    

## 2 New project, like Gemos



## 3 Older projects with older versions of Atomic

never pull on the server! It will load newer version of atomic and break the live website

there is a function that is called 2 times, the svg mime, comment that out

gulpfile.js proxy target might be wrong



# Issues / Errors

### 1 The routing of Vhost points to the normal website instead of local host

Steps tried with Form Forum

1. Rm -r projectfolder

2. in docker main folder launch sql

3. `mysql -u root -p docker -h mysql` pass:docker

4. `show databases;`  note that commands for mysql end in semicolon

   1. In mysql queries table names [may contain](http://dev.mysql.com/doc/refman/5.7/en/identifiers.html) alphanumeric characters, underscore and dollar sign. In order to be able to use other ANSI characters you must place names in single backquotes.

   ```
   `table-db`
   ```

5. drop database ```drop database `samichlous-schmutzli`; ```

6. `Exit` to quit mysql

7. reinstall

8. wizzard

9. Import db

10. wp cache flush

11. ping name website

12. restart docker

13. in sass style, @import in modo che il path sia nella stesso directory



Blue lamp stack screen is a proxying issue



### Routing tryout

Navigate to **chrome://net-internals/#dns** and press the "Clear host cache" button.

Sometimes you need to flush the socket pools after flushing the DNS:

```
chrome://net-internals/#sockets
```

----

OS X 10.11, 10.12+ (El Capitan, Sierra):

```
sudo killall -HUP mDNSResponder
```

----

In Chrome, click on the wrench icon, and then *Options*. Go to *Under the Hood* tab. Click on the *Clear browsing data* button under the *Privacy* section. Select just the "Empty the cache" check box, and then click on the *Clear browsing data* button.

---

Had to change these lines in my wp-config.php from

```
define('WP_CACHE', true);
define( 'WPCACHEHOME', 'C:\wamp64\www\wp-content\plugins\wp-super-cache/' );
```

to

```
define('WP_CACHE', false);
//define( 'WPCACHEHOME', 'C:\wamp64\www\wp-content\plugins\wp-super-cache/' );
```

---

https://wordpress.stackexchange.com/questions/263924/wordpress-localhost-site-redirect-to-live-site

---

I just change my permalink structure to plain and again to old one then Its working. thanks all of you for your help. :)

### search replace doesn't find them all

log in in phpmyadmin

in sql type

```
UPDATE wp_options SET option_value = replace(option_value, 'Existing URL', 'New URL') WHERE option_name = 'home' OR option_name = 'siteurl';
UPDATE wp_posts SET post_content = replace(post_content, 'Existing URL', 'New URL');
UPDATE wp_postmeta SET meta_value = replace(meta_value,'Existing URL','New URL');
UPDATE wp_usermeta SET meta_value = replace(meta_value, 'Existing URL','New URL');
UPDATE wp_links SET link_url = replace(link_url, 'Existing URL','New URL');
UPDATE wp_comments SET comment_content = replace(comment_content , 'Existing URL','New URL');
```

```
UPDATE wp_posts SET guid = replace(guid, 'samichlous-schmutzli.ch', 'samichlous.site');
```

Dominique's example for thomus

```
UPDATE thoemus.thoemus_options SET option_value = replace(option_value, 'https://stage.thoemus.ch/', 'http://thoemus.site/') WHERE option_name = 'home' OR option_name = 'siteurl';
UPDATE thoemus.thoemus_posts SET guid = replace(guid, 'https://stage.thoemus.ch/','http://thoemus.site/');
UPDATE thoemus.thoemus_posts SET post_content = replace(post_content, 'https://stage.thoemus.ch/', 'http://thoemus.site/');
UPDATE thoemus.thoemus_postmeta SET meta_value = replace(meta_value,'https://stage.thoemus.ch/','http://thoemus.site/');
```



# Extra Notes / Cases

to order

## 1 Without Atomic or Docker

in html folder in docker (when you start the shell)
mkdir directoryprogetto
cd directoryprogetto
wp core download
wp core config --dbname=portfolio --dbhost=mysql --dbuser=root --dbpass=docker
wp db create

(if the database is new, not if you import!)
wp core install --url=portfolio.site --title=Portfolio --admin_user=silvia --admin_email=email@email.com



## 2 Docker on window

1. Cd docker dev folder
2. Docker-compose up -d (-d stands for detached mode, no mysql root?)
3. wp core download
4. v hosts in window
   1. Note pad, run as administrator
   2. Open window/system32/driver/etc/hosts/*all files
5. docker compose restart
6. create ssh-keygen
7. Docker-compose build
8. search replace https to http
9. Uploads plugins db





