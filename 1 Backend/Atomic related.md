##  Atomic workflow

1. Atomic copy the stuff you need to create
2. in sass style, @import in modo che il path sia nella stesso directory
3. se devi modificare qualcosa globalmente come wpcf7 scrivi css nel main files
4. new whole php templates are created in the project folder, get footer organism
5. same x js, include it in the organism folder and import it in js/script.js
6. media query are directly in the atom sass



# atomic wizzard behind the scenes



**Start installation**

cd /var/www/html
mkdir ./$theme
cd ./$theme



**Download WP and Config**

wp core download --allow-root
wp core config --dbname=$db --dbuser=root --dbpass=docker --dbprefix=wp_ --dbhost="mysql" --allow-root
wp db create --allow-root



**Run WP Install**

wp core install --url=$url --title="$title" --admin_user=$admin_usr --admin_password=$pass --admin_email=$admin_mail --skip-email --allow-root

echo "Downloading ACF Pro Plugin with lisence"
curl -o acf-pro.zip "http://connect.advancedcustomfields.com/index.php?p=pro&a=download&k=b3JkZXJfaWQ9NDMzNjV8dHlwZT1wZXJzb25hbHxkYXRlPTIwMTQtMTEtMDEgMTY6MzE6Mzg="



**Add and Remove Base Plugins**

wp plugin install acf-pro.zip --activate --allow-root



if [ $allplugins == "true" ]
then
	wp plugin install contact-form-7 wp-nested-pages wordpress-seo --activate --allow-root
fi

wp plugin delete hello akismet --allow-root



**Create homepage**

wp option update page_on_front 2 --allow-root
wp option update show_on_front page --allow-root



**Set Your Timezone - Most of you will want to change this**

wp option update timezone_string Switzerland/Bern --allow-root
wp option update blogdescription "" --allow-root



**Options checkboxes the way I like them**

wp option update default_pingback_flag 0 --allow-root
wp option update default_ping_status 0 --allow-root
wp option update default_comment_status 0 --allow-root
wp option update comment_registration 1 --allow-root



**Update rewrite (You'll still need to resave the Settings > Permalinks Page)**

wp rewrite structure '/%year%/%monthnum%/%postname%' --allow-root



**Copy base theme to site**

cd wp-content/themes/
git clone -b develop git@bitbucket.org:duotones/atomic.git
git clone -b develop git@bitbucket.org:duotones/"$theme".git
wp theme activate $theme --allow-root



**Install gulp**

cd "$theme"
git flow init -d
npm install
sed -i.bak "s/'matter'/'$theme'/g" gulpfile.js
rm gulpfile.js.bak

if [[ $directoryentry == "true" ]]
then
	echo -e "" >> /etc/apache2/sites-enabled/default.conf
	echo -e "<VirtualHost *:80>" >> /etc/apache2/sites-enabled/default.conf
	echo -e '\tDocumentRoot "/var/www/html/'$theme'"' >> /etc/apache2/sites-enabled/default.conf
	echo -e '\tServerName '$url >> /etc/apache2/sites-enabled/default.conf
	echo -e '\t<Directory "/var/www/html/'$theme'/">' >> /etc/apache2/sites-enabled/default.conf
	echo -e '\t\tAllowOverride all' >> /etc/apache2/sites-enabled/default.conf
	echo -e '\t</Directory>' >> /etc/apache2/sites-enabled/default.conf
	echo -e '</VirtualHost>' >> /etc/apache2/sites-enabled/default.conf
fi



**Spit out username and password details**

printf "\n\n"
printf "${GREEN}TATAA! I'm done, now it's your turn, happy coding!${NC} \n"
printf "${CYAN2}By the way, ${RED}$admin_usr${CYAN2} is your username \n"
printf "${CYAN2}and ${RED}$pass${CYAN2} is your password${NC} \n"