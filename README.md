# limesurvey BIBBOX application

This container can be installed as [BIBBOX APP](https://bibbox.readthedocs.io/en/latest/ "BIBBOX App Store") or standalone. 

After the docker installation follow these [instructions](INSTALL-APP.md).

## Standalone Installation 

Clone the github repository. If necessary change the ports in the environment file `.env` and the volume mounts in `docker-compose.yml`.

```
git clone https://github.com/bibbox/app-limesurvey
cd app-limesurvey
docker network create bibbox-default-network
docker-compose up -d
```

The main App can be opened and set up at:
```
http://localhost:8082
```

## Install within BIBBOX

Visit the BIBBOX page and find the App by its name in the store. Click on the symbol and select install. Then fill the parameters below and name your App, click install again.

## Docker Images used
  - [bibbox/limesurvey](https://hub.docker.com/r/bibbox/limesurvey) 
  - [mariadb](https://hub.docker.com/r/mariadb) 


 
## Install Environment Variables
  - ADMIN_USER = LimeSurvey Admin Username
  - ADMIN_EMAIL = E-mail of the for admin user
  - ADMIN_PASSWORD = Password for admin user
  - MYSQL_ROOT_PASSWORD = Root Password for the MySQL DB, remember well

  
The default values for the standalone installation are:
  - ADMIN_USER = admin
  - ADMIN_EMAIL = admin@bibbox.org
  - ADMIN_PASSWORD = changethispasswordinproductionenvironments
  - MYSQL_ROOT_PASSWORD = changeforproduction

  
## Mounted Volumes
### bibbox/limesurvey Conatiner
  - *./plugins:/var/www/html/plugins*
  - *./upload:/var/www/html/upload*
  - *./config:/var/www/html/application/config*
### mariadb Conatiner
  - *./database/mysql:/var/lib/mysql*

