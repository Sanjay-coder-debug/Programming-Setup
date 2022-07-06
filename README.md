# Programming-Setup
one place for all tech stack
                             NEVER FEAR FOR NOT TRY !! IF TODAY YOU NOT TRY THEN WHEN YOU TRY -- TRY AND LEARN

     


## Little Help
--------------------
- You can  use various version of Php on Ubuntu-18.04 and 20.04
- You can use various version of Web Server on Ubuntu
-  



OS Installation 
------------------
  


### Kali Linux Command
-------------------------



### Ubuntu Command
------------------
                Basic 
                       - ls
                       - ll
                       - clear
                       - exit
                       - ll -la
                       - mkdir
                       - rm -rf 
                       - chmod -R 777 
                       - sudo su
                       - mv
                       - cp
                       - nano
                       - cat 
                       
        
      Check Ubuntu version
      --------------------
            - lsb_release -a
            


### Windos
------------





Language :
--------------
             - All Language Install and Setup

# Java Setup
--------------------
#Java Setup For Windows
-----------------------
 Basic Java Program Setup
 -------------------------
 - 






#Php Setup
----------
# Php Setup for Windows
------------------------
Basic Php Program Setup Also For Project Setup Based on Core Php 
-----------------------------------------------------------------
                   - Install Xampp   
                   - Install Vs Code or Atom or Sublime Text
                   

Laravel Setup For Windows
-------------------------
  Prerequisite For Laravel Install in Windows Os
  -----------------------------------------------
         Method-1 - https://www.youtube.com/watch?v=Czhoqx86V24&ab_channel=EduonixLearningSolutions
         =========
            Step-I
            -------
                       - Install Xampp  - Apache will not work in new windows - https://stackoverflow.com/questions/27333203/xampp-couldnt-start-apache-windows-10
                       - Install Composer 
                       - Install Vs Code or Any Editor You Want
           Step-II
           -------
                      - 
                      - 
                      - 
                   



# Php Setup For Ubuntu
----------------------




### Php Command For Ubuntu
---------------------------
        General
        -------
           - php --version                              - Check Which Version php You have in your system
           - sudo update-alternatives --config php      - List All The Php Version & use as per your need 
           - sudo systemctl restart php7.3-fpm  | start php7.3-fpm  | stop php7.3-fpm 
           - sudo a2dismod php7.2
           - sudo a2enmod php7.4
           - sudo service php7.3-fpm status
           - sudo service php7.3-fpm stop
           - sudo service php7.3-fpm start
           - sudo service php7.4-fpm status
           - sudo service php7.4-fpm stop

           
        Install
        --------
           - sudo apt install software-properties-common
           - sudo add-apt-repository ppa:ondrej/php
           - sudo apt-get update
           - sudo apt install php7.4 || sudo apt install php7.3  || sudo apt install php - choose your version
           - sudo apt-get install php7.4-common php7.4-xml php7.4-curl php7.4-bcmath php7.4-intl php7.4-gd php7.4-zip php7.4-mysql php7.4-soap php7.4-mbstring
           - sudo apt install php7.4-common php7.4-mysql php7.4 php7.4-cgi libapache2-mod-php7.4 php-pear php7.4-mbstring
           - ext-bcmath,ext-ctype,ext-curl,ext-dom,ext-gd,ext-hash,ext-iconv,ext-int,ext-mbstring,ext-openssl,ext-pdo_mysql,ext-simplexml,ext-soap,ext-xsl, ext-zip,              ext- sockets
           
             
        Un-install
        -----------
             - sudo apt-get purge php7.*
             - sudo apt-get autoclean
             - sudo apt-get autoremove
             - sudo apt autoremove
             - sudo apt-get --purge remove apache2
             
           

### Python Command
-------------------







Framework : - : 
=================

### Magento
-------------
             General
             ---------
                    - sudo php bin/magento setup:upgrade
                    - sudo bin/magento setup:di:compile
                    - sudo bin/magento setup:static-content:deploy -f
                    - sudo bin/magento indexer:reindex
                    - sudo bin/magento cache:flush
                    - sudo bin/magento cache:clean
                    - sudo bin/magento module:status 
                    - sudo php bin/magento   - check when Namespace error
                    - sudo php bin/magento setup:di:compile
                    - sudo chmod -R 777 var/ pub/ generated/        
                    - sudo bin/magento module:disable Codilar_Thor   - Disable any Module
                    - rm -rf FolderName   - To Remove any Folder 
                    
             
             Disable the module
             ------------------
                    -  sudo bin/magento module:disable Module_Name
                    
             
             Magento Mode Show
             -----------------
                 - sudo php bin/magento deploy:mode:show
                 - sudo php bin/magento deploy:mode:set production
                 - php bin/magento deploy:mode:set developer
                 - php bin/magento deploy:mode:set default
               
             (Or)
                  - Go to - app/etc/env.php 
                  -  'MAGE_MODE' => 'developer',    ------> here you need to specify - production, default
             
                   
             Two Factor Authentication
             -------------------------
                    - bin/magento module:disable Magento_TwoFactorAuth
                    - bin/magento cache:flush 
                    
               
               Set the Mode - Production and Development
               -------------------------------------------
                    - bin/magento dep:mod:show
                    - php bin/magento deploy:mode:set production
                    - sudo bin/magento de:mo:se developer
           Install
           -------
                  step- 1
                  --------
                            - Check the System Requirement
![demo](https://user-images.githubusercontent.com/78407424/132894029-ca0e0732-1334-4a66-93dd-62dcff27752e.png)
                            
                 step- 2
                 --------
                    Step For Local Magento Setup
                    -------------------------------
                        - composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition:2.3.7-p1 .
                        - composer create-project --repository=https://repo.magento.com/ magento/project-community-edition:2.3.7 Magento237(your folder name)
                        
                  (Or)
                  
                     If You Want To Setup  For Project
                        -  Need step -1 complete
                        -  clone the project repo
                        
                step -2)i)
                -----------
                        - Create Database on Mysql for install DB
                        - Also If You Want To Setup Using new User You can Create
                       
                       
                step-3
                -------
                Database Setup  (Both for Local and Project)
                -----------------------------------------------
                - bin/magento setup:install  --base-url=http://magento237.local/  --db-host=localhost  --db-name=magento  --db-user=magento237  --db- password=Sanjay1997@@ --backend-frontname=admin  --admin-firstname=admin  --admin-lastname=admin  --admin-email=devops1@codilar.com  --admin-user=admin1  --admin-password=admin123  --language=en_US  --currency=INR  --timezone=Asia/Kolkata  --use-rewrites=1
                
                
                (Or)
                
                 - sudo bin/magento setup:install --base-url=http://casio.local/ --db-host=localhost --db-name=casio --db-user=root --db-password=1234 --admin-firstname=Sanjay --admin-lastname=Das --admin-email=cod34082@adobe.com --admin-user=sanjay --admin-password=sanjay123 --language=en_US --currency=USD --timezone=America/Chicago --use-rewrites=1 --search-engine=elasticsearch7 --elasticsearch-host=localhost --elasticsearch-port=9200
                
                
                
           If You Want To Create New User For Magento
           --------------------------------------------- 
               -  php bin/magento admin:user:create --admin-user=local --admin-password=admin123 --admin-email=sanjay1@gmail.com --admin-firstname=admin --admin-lastname=admin



           Some Issue Need To Check After Install(May You Get Error)
           ----------------------------------------------------------
             
              - cd /etc/nginx/sites-available/
              - cd /etc/nginx/sites-enabled/
              - nginx.sample.config
              
              
         If You Have More Than One Magento 
         -----------------------------------
              - sudo ln -s /etc/nginx/sites-available/magento237 /etc/nginx/sites-enabled     (Enable your project)  
              - sudo unlink folder_name                                                       (Inside (/etc/nginx/sites-enabled/) Path)
              - sudo update-alternatives --config php                                        (list php and change the Php Version as per Magento Version)
              - sudo service nginx restart                                                    (Restart Your nginx)




        Some Error To Solve in Magento 
        ------------------------------
        
              - etc/nginx/sites-available/magento237(magento setup folder_name)         - Path of Folder
              - sudo nano magento237(folder_name)                                       - Need To Open this file or as same for other magento file
              
             - Check The Below Format
                                      upstream fastcgi_backend {
                                                         server unix:/run/php/php7.4-fpm.sock;
                                                      } 
                                               server {
                                                       listen 80;
                                                       server_name local.test.com or (server_name _;);
                                                       set $MAGE_ROOT /var/www/html/test;
                                                       set $MAGE_RUN_TYPE website;
                                                       include /var/www/html/test/nginx.conf.sample;
                                                     }
                                         
                                         
                                         
              - Also Some time Some memory  issue(502 Bad gateway Error) so you can add  Inside(var/www/html/Magento_Folder_Name/nginx.conf.sample file)
                                  
                                             fastcgi_buffers 8 16k;
                                             fastcgi_buffer_size 32k;
                                             fastcgi_connect_timeout 90;
                                             fastcgi_send_timeout 90;
                                             fastcgi_read_timeout 90;
                                             
              Some Quick Way Need To Check For Get Error
              -------------------------------------------
                 -  var/www/html/magento_folder_name/app/etc/env.php        ---- >  check the user and database password and all
                 -  var/www/html/magento_folder_name/nginx.conf.sample      ----->  check the memory code 
                 -  other location --> computer  --> etc/hosts              -----> check the url is added or not 
                 -  other location --> computer  --> etc/nginx              -----> check  file inside nginx 
                 -  
                 
             - Check with Error
             ==================
                         This site can’t be reached
                          Check if there is a typo in magento.local.
                          DNS_PROBE_FINISHED_NXDOMAIN.
                          
                            Solution - make sure you declare - url(http://name/) -In  etc—> hosts
                            
             -Check with This Error Also
             ============================
             Failed to send the message. Please contact the administrator
              
                            - Solution - bin/magento module:disable Magento_TwoFactorAuth
                            

              
              
              
Setup Database in Magento (If you have  Already Existing Project Setup and Also You Have Existing Database but You Forget Your Uname and PassWd )   
------------------------------------------------------------------------------------------------------------------------------------------------

Step-1
-------
  - bin/magento setup:install  --base-url=http://shopmonk.local/  --db-host=localhost  --db-name=rehandel  --db-user=magento  --db-password=Magento@123 --backend-frontname=admin  --admin-firstname=admin  --admin-lastname=admin  --admin-email=sanjay.d@codilar.com  --admin-user=admin1  --admin-password=admin123  --language=en_US  --currency=INR  --timezone=Asia/Kolkata  --use-rewrites=1

Step -2 
--------
 - sudo php bin/magento admin:user:create --admin-user='admin1' --admin-password='admin123' --admin-email='sanjay.d@codilar.com' --admin-firstname='Sanjay' --admin-lastname='Kumar'

Step -3
-------
 - SELECT *FROM `core_config_data`WHERE (`scope` LIKE '%cookie%' OR `path` LIKE '%cookie%' OR `value` LIKE '%cookie%') LIMIT 50
 - Change the Value -  web/cookie/cookie_domain  to / 
 - Syntax to update => update core_config_data set value="/" where config_id = 102;



 Un-install
------------          
           
           
       
IDE,EDITORS & Other
===================
### Anydesk
-----------
- wget -qO - https://keys.anydesk.com/repos/DEB-GPG-KEY | apt-key add -
- echo "deb http://deb.anydesk.com/ all main" > /etc/apt/sources.list.d/anydesk.list
- sudo apt update
- sudo apt install anydesk
- anydesk

### Postman
--------------


### Eclipse
------------
       General
                 - sudo snap remove eclipse
                 - 
                 - 
                 
       Install
                 - 
                 - 
                 - 
                 - 
          
       Un-Install
                 -
                 - 
                 - 
              


### Atom
--------------------



### Vs Code
-------------------------

   Install Vs Code
   -------------------
       - sudo snap install code --classic 
       
       
   Un-Install Vs Code
   -------------------
         - 
         
   
   Git Configuration For Vs Code 
   -----------------------------
   
   - 
   

  Vs Code Setting
  -----------------
             For Tree View OF Files 
             ----------------------
                                 - Setting>Search Compact Folder > Un-Checked the Check Box
                                 - Setting > Search Tree Indent 
                                                      
                
            Codding Help Extensions
            -----------------------
                                  - Auto Rename Tag
                                  - Live Server 
                                  - Prettier - Code Formatter
                                  - vscode-icons
                                  - codeStackr Theme
                                  - Fluent Icons
                                  - Bracket Pair Colorizer
                                  

                         


### Install Slack 
-----------------
             - sudo snap install slack


### PhpStrom
-------------------------
Install Phpstrom
-----------------
          - sudo snap install phpstorm --classic
  
          - sudo snap remove phpstorm
          
Completly Uninstall PhpStrom
----------------------------
        - sudo snap list
        - sudo snap remove phpstorm
        - whereis phpstrom

    Activation of Php
    ------------------
                       - Help -- > Register
                       
 
   

  


OpenSource Tools
==================


### Composer
------------
        General
        ---------
            - composer -v
            - cd
            - pwd
            - check the php must be install
        Install
        ---------
            - sudo apt install unzip
            - curl -sS https://getcomposer.org/installer -o composer-setup.php
            - sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
       Un-install
       -----------
       
     
      Composer Self-Update to Other Version
      -------------------------------------
            - sudo composer self-update --1
            - sudo composer self-update --2
            
            
      Install Any Third Party Module using Composer
      ---------------------------------------------
      -    Here we need to Install this third party module   E.g -  amasty/promo "version": "2.9.7",
      
      By Terminal Way
      ---------------
      -    composer require amasty/promo:2.9.7
      
       

### Github , Gitlab , BitBucket
-------------------------------------------





Android Studio
-------------------------------



Chrome 
------------------------



## Apache Command
-----------------
           General
           ---------- 
                        - whereis apache2                       - check the if furthur exist after uninstall
                        - apache2 -v  || apache2 --version         
                        - sudo service apache2 start
                        - sudo service apache2 status
                        - sudo service apache2 stop
                        - systemctl status apache2.service
                        - sudo systemctl enable apache2.service
                        - sudo nano /etc/apache2/sites-available/magento2.conf
                        - sudo a2enmod rewrite
                        
           Install
           --------
                     - sudo apt install apache2
 
         Un-install
         -----------
                      - sudo apt-get purge apache2 apache2-utils apache2.2-bin apache2-common
                      - sudo apt-get autoremove
                      - sudo rm -rf /etc/apache2
                      - sudo apt autoremove apache2
                      
                     


## Nginx Command 
-----------------
      General
      --------
           - nginx --version
           - sudo service nginx status | stop | start | restart
           - sudo systemctl stop nginx.service
           - sudo systemctl start nginx.service
           - sudo systemctl enable nginx.service
           - sudo nano /etc/nginx/sites-available/default 
        
        (Or)
            - /etc/init.d/nginx status
            - /etc/init.d/nginx stop
            - /etc/init.d/nginx start
           
      Install
      ---------
           - sudo apt install nginx
           - 
           - 
           - 
           - 
      
      Un-install
      -----------
           - sudo apt-get remove nginx nginx-common
           - sudo apt-get purge nginx nginx-common
           - sudo apt-get autoremove
      Nginx Issue
      ------------
           - sudo nginx -t
           - tail -f /var/log/nginx/error.log
           - ps auxf | grep nginx
           
      

## Mysql Command 
-----------------
        General 
        --------       
             - mysql --version
             - sudo service mysql status
             - sudo service mysql stop
             - sudo service mysql start
        Install
        --------
             - sudo apt policy mysql-server  
             - sudo apt update
             - sudo apt install wget -y
             - wget https://dev.mysql.com/get/mysql-apt-config_0.8.12-1_all.deb
             - sudo dpkg -i mysql-apt-config_0.8.12-1_all.deb
         
        (Or)
             - sudo apt-cache policy mysql-server
             - sudo apt install -f mysql-client=5.7* mysql-community-server=5.7* mysql-server=5.7*
             - sudo mysql_secure_installation
             
             
             
             
        Un-install
        -----------
            - sudo systemctl stop mysql
            - sudo apt-get purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-*
            - sudo apt-get remove --purge mysql*
            - sudo apt autoremove
            - sudo apt-get autoclean
            - sudo rm -rf /var/lib/mysql
            - sudo rm -rf /etc/mysql
            - 
            
       Mysql  user issue 
       ------------------
             - SELECT User, Host FROM mysql.user;
             - select user from mysql.user;
             - CREATE USER 'magento237'@'localhost' IDENTIFIED BY 'password';
             - GRANT ALL PRIVILEGES ON *.* TO 'magento237'@'localhost' WITH GRANT OPTION;
             - FLUSH PRIVILEGES
             - exit
             
      Mysql User error
      ----------------
           - SELECT user,authentication_string,plugin,host FROM mysql.user;
           - ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '1234';
           - FLUSH PRIVILEGES;

             
       
       
       
       
       Import Existing Database
       -------------------------
             - mysql -u username -p database_name < file.sql          -  Syntax for import existing database file    
              - 
       Import Other Way 
       -----------------
           - Download the Sql File 
           - Go To that Directory 
           - Open Terminal From That Directory
           - Open MySql(mysql -u Username -pPassword)
           - run the command  for import --->(source file.sql(only this name- rehnadel_22-02-14.sql ) not this name -> /home/prem/Desktop/rehnadel_22-02-14.sql
           - source rehnadel_22-02-14.sql;

      Export Database 
      ----------------
              - mysqldump -u magento -p rehandel > rehandel.sql
              - mysqldump -u magento -p rehandel > rehandel.sql --single-transaction (If this command not run just try in (prem@sanjay:~/Downloads$) other path 





### Redis Installation
----------------------




### Varnish Installation
------------------------







### Docker Command
--------------------
- sudo docker compose ps                      -to check the details
- sudo docker compose stop                    
- sudo docker compose start  
- sudo docker compose exec app bash           -go inside to magento directory
- sudo docker compose exec mysql bash         -go inside to mysql 
- sudo docker volume ls                       - list all remaning container present in docker
- sudo docker compose down

## Install Magento Using Docker Way
====================================

  step -1
          -  Download the sample docker file and extract in the desired location and   Rename the extracted folder to desired project name . 
           Link - https://drive.google.com/file/d/1WVtY4EUHqb0KQVWTH8kEzjjzkIP6QIh-/view?usp=sharing
           
  step -2
  
         - Delete the src folder which is inside the docker file and create a new fresh src folder.
           Ex:
               - sudo rm -rf src
               - sudo mkdir src
               
 step -3
         - Edit .env file , .application file and docker-compose.dev.yml files

                    - .env file change mysql version to 5.7 . 

                    - .application file you can configure mysql , elasticsearch , rabbitmq and magento setting.

                    - .docker-compose.dev.yml file you have edit 
            app:
                     - image: magento24/php7.4:${PROJECT_IMAGE}
                     
                     
 step -4
           Run this docker build command :
                                           - sudo docker-compose -f docker-compose.dev.yml up -d --build .
                                            
                                              -  This command will build your all the container using “docker-compose.dev.yml ” file.
                                              
 step -5
               Now for get into the docker app container use this command.
               
                           -  " sudo docker-compose exec app bash" .
                                               
                            - Before this you must have the docker location and checked with below command for confirmation
                                            - sudo docker compose ps
                                            - sudo docker compose start    - make sure all the container are up (running)
                                            
step -6
                - composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition:2.4.3-p1 .

                                        - This command will clone the particular magento project .

                                                         - In this command 2.4.3-p1 is the magento version.you can choose as per your need
                                                         
step -7                
               - Run this command for magento installation :
               
               - Before run this command we need to create database as we need to use to install magento things 
               
                   - sudo docker compose exec mysql bash   - to go into mysql application  
               
bin/magento setup:install --base-url=http://magento24.local/ --db-host=mysql  --db-name=magento --db-user=root --db-password=codilar -- admin-firstname=admin --admin-lastname=demo --admin-email=sachin@codilar.com --admin-user=sachin --admin-password=admin123 --language=en_US --currency=INR --timezone=Asia/Kolkata --use-rewrites=1 --search-engine=elasticsearch7 --elasticsearch-host=elasticsearch --elasticsearch-port=9200


### Elastic Search Command
---------------------------
      General
      --------
                  - service elasticsearch status
                  - /etc/init.d/elasticsearch status
                  - /etc/init.d/elasticsearch start
                  - /etc/init.d/elasticsearch stop
                  - /etc/init.d/elasticsearch restart
                  - /etc/init.d/elasticsearch force-reload - service elasticsearch status
                  - /etc/init.d/elasticsearch status
                  - /etc/init.d/elasticsearch start
                  - /etc/init.d/elasticsearch stop
                  - /etc/init.d/elasticsearch restart
                  - /etc/init.d/elasticsearch force-reload
 
     Check The Version
     -----------------
                    - curl -XGET 'http://localhost:9200'
                    - bin/elasticsearch --version
    
    
     Install Command for Elasticsearch
     ---------------------------------
     - 
     
     
     
     
     UnInstall Command For Elasticsearch
     -----------------------------------
     - 
    
    
    Configuration Of Elastic Search in Magento2
    -------------------------------------------
                               - 
                               - 
                               - 
                               -
                               -
                               
                    
    Use Of Elastic Search in Magento2
    ---------------------------------
                               - 
                               - 
                               - 
                               - 
                               - 
    Links:-
    ------
         - https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-elasticsearch-on-ubuntu-20-04
         
                               
### RabbitMQ Setup Command
--------------------------                              
           Install of RabbitMQ   - All setup mention in given docs link only .
           -------------------
                   - sudo apt install -y rabbitmq-server   - you can go this or you can go with below link
                   
                                                                      - https://tecadmin.net/install-rabbitmq-server-on-ubuntu/
                   
                   
                   
           
           General Command
           ---------------
           - systemctl status rabbitmq-server
           
           
           
           
           Configure With Magento Project
           ------------------------------
           Step -1
           -------
           
           - Open - Magento Project Directory  -- Check with  env.php  inside this file paste the below code. for run RabbitMq wth Magento
                     
                          'queue' => [
                                     'amqp' => [
                                               'host' => '127.0.0.1',
                                               'port' => '5672',
                                               'user' => 'guest',
                                               'password' => 'guest',
                                               'virtualhost' => '/',
                                               'ssl' => ''
                                               ] 
                                      ],
                                      
            Step -2
            -------
                    - after this run setup & upgrade command in magento directory.
                    - open your local rabbitMQ and go to Queue check any queue you have or not.
                    
           - Check the rabbitMQ is working or not 
           
                              - your project url and port number like - http://adobe.training:15672/
                              - you may got this project used in some other location then kill the port.
                                       Ex - npx kill-port 8080(put which port error is showing)
           Un-Install Command
           ------------------
           
           
## Install MailHog For Ubuntu -18.04 & Configure for Magento2
=============================================================


    step -1
    ------- 
                  - Go with below link 
                           - https://nishchay.io/blog/mailhog-installation-on-ubuntu                
    step -2
    -------
               - create one simple .php file which contain php mail() function and it have message
               - in your terminal anywhere you can  type - php file.php(this is the file you created as mention in above step)
               - Now Check in - mailHog Server you must recevice the mail 
    step -3
    --------
               - I am going with  SMTP Extension for Sending mail (you can go with Other)
               - sudo composer require mageplaza/module-smtp    - install the SMTP
               - run se:up and ca:fl 
               
               
               
## Setup - Xdebug in Magento Proect
-----------------------------------
                   - Go With Below link

                   - https://www.linkedin.com/pulse/how-install-xdebug-config-phpstorm-ubuntu-jun-wu/


                   
                     
                     
                     
                     
                     
    
   #  Study Reff
     ------------
    
   -  https://www.emizentech.com/blog/magento-2-4-with-elasticsearch-complete-guide.html
  
    
    
 
