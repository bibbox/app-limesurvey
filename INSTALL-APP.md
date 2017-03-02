## LimeSurvey Installation Instructions 

## Install Parameters

* Database location = limesurvey-db
* Database user = limesurvey
* Database password = limesurvey4bibbox
* Database name = limesurvey

![FINAL](install-screen-01.png)

## Populate the Database

## Login

* user: admin
* password: password

Please change the password. 


## BUGFIX (does not work)

* run the command 
* sudo docker exec -it container-name /bin/bash

within the container appy this bath to the config.php

* sed -i "s/'urlFormat' => 'path'/'urlFormat' => 'get'/g" /var/www/html/application/config/config.php 

A better container will be provided soon. 



## After the installation

Have a nice ride with the new Admins youngtimer.

![FINAL](install-screen-final.jpg)
