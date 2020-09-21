# Deployment at Duotones



## Creating domain at Cyon

1. Cyon buy a single plan
2. add data to bill from client
3. it will generate user and password, save the pass
4. in the terminal, `ssh username@server`
5. create a directory in /www ssh  `mkdir prod/stage`
6. Install WP cli in the main directory
7. with curl, and make it executable (check on mac!)
8. create bin folder
9. put the wp cli in the bin folder
10. in the prod directory install wordpress (wp core install)
11. modify the configurations: wp core config (db user = name user dbprefix = db_ or gems_)
12. Remove the other child themes generated from wp install `rm -r twenty*`(-r means recursive, all the sub folders)
13. once it is done, activate the ssl security certificate (during the night, so the client doesn't check on it)



### Creating a subdomain

under duotones.stage.. find notes!



###  Push changes to subdomain

1. login ssh duotone1.duotones.ch
2. pass from thomas
3. in the folder, pull from bitbucket
4. Fetch, pull
5. refresh



## enter in live website

get access 

`ssh serveraddress` 

Password

check version of atomic in prod, 

`git log --pretty=format:'%h' -n 1`to see just the hash

exit to log out



## Creating a database

1. in Cyon, create a new database
2. save pass and username
3. in Filezilla (port 22) enter duotone1@duotones.ch
4. export the plugins, uploads and database to desktop
5. Log in with the new project serverspace and load them



## Bitbucket load child theme

1. ssh key paste it in the main folder..

2. if your laptop isn't connected, generate the public key in the main folder of the project with the keygen command `ssh-keygen`

3. enter to copy the public key with `cat .ssh/d-rsa-public`

4. send it to thomas that has access of bitbucket and can paste it to allow you to pul the repo

5. git clone with ssh link to the child theme (atomic and current repo)

   

## Fake routing to test?

1. Copy Ip address from Cyon
2. Ghost = ip gemos.ch
3. Visit gemos.cyon.site



## Rerouting A ?

to check hosting service ask for

​	data access

​	access DNS provider

- you can look what someone is using by visiting ping.eu or dns lookup
- a good hosts has ftpuser, php, manage domains and htaccess or ssh (helpful to push code)
- change the DNS points to ns1.cyon.ch and ns2.cyon.ch (fallback)



## SSL certificate that doesn't want to update itself

http://lists.gno.org/cert-maint-mac-10.5.8/



## End

1. send Marcel the generated logins of Cyon for the real rerouting
2. export old content of the site



