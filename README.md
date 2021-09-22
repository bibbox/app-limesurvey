# LimeSurvey BIBBOX application

This container can be installed as [BIBBOX APP](http://silicolabv4.bibbox.org/applications "BIBBOX App Store") or standalone. 
* initial user/passwordd: **admin / admin**
* after the docker installation follow these [instructions](https://github.com/bibbox/app-limesurvey/blob/master/INSTALL-APP.md)

## Standalone Installation 

To install the app locally execute the commands:

`git clone https://github.com/bibbox/app-limesurvey`

`cd app-limesurvey`

`docker network create bibbox-default-network`

`docker-compose up -d`

After the Installation open "http://localhost:8082/admin" in a browser to get to the admin panel and do some configuration

The public survey page can be reached at "http://localhost:8082"

The default port of the app Limesurvey is 8082.

If necessary change the ports and the volume mounts in `docker-compose.yml`. See volume mounts below

## Docker Images Used
 * [BIBBOX/limesurvey](https://hub.docker.com/r/bibbox/limesurvey) 
 * [mySQL](https://hub.docker.com/_/mysql/), offical mySQL container
 
## Install Environment Variables

 * LIMESURVEY_DB_PASSWORD
 * LIMESURVEY_DB_HOST
 * LIMESURVEY_ADMIN_USER
 * LIMESURVEY_ADMIN_PASSWORD
 * LIMESURVEY_ADMIN_NAME
 * LIMESURVEY_ADMIN_EMAIL
 
 The default values for the standalone installation are:
 * LIMESURVEY_DB_PASSWORD = limesurvey
 * LIMESURVEY_DB_HOST = mysql:3306
 * LIMESURVEY_ADMIN_USER = admin
 * LIMESURVEY_ADMIN_PASSWORD = admin 
 * LIMESURVEY_ADMIN_NAME = admin 
 * LIMESURVEY_ADMIN_EMAIL = admin@admin.de

## Mounted Volumes

### Limesurvey Container
 ./plugins:/var/www/html/plugins
 ./upload:/var/www/html/upload
 ./config:/var/www/html/application/config
 ### DB-Container
 ./database/mysql:/var/lib/mysql
