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
---------------------


### Windos
------------





Language :
--------------
             - All Language Install and Setup

### Java Command
--------------------










### Php Command
--------------------
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
                    - bin/magento dep:mod:show
                    - sudo bin/magento de:mo:se developer
           Install
           ---------
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
                                                       server_name local.test.com;
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
              


           Un-install
          ------------          
           
           
       
IDE,EDITORS & Other
===================
### Anydesk
-----------


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
                            - 





### PhpStrom
-------------------------

          - sudo snap install phpstorm --classic
  
          - sudo snap remove phpstorm

    Activation of Php
    ------------------
                       - Help -- > Register
                       
                       
     Key -1
     ---------
                    - BQDN55OGPC-eyJsaWNlbnNlSWQiOiJCUURONTVPR1BDIiwibGljZW5zZWVOYW1lIjoi5rC45LmF5r+A5rS7IHd3d8K3YWppaHVvwrdjb20iLCJhc3NpZ25lZU5hbWUiOiIiLCJhc3NpZ25lZUVtYWlsIjoiIiwibGljZW5zZVJlc3RyaWN0aW9uIjoiIiwiY2hlY2tDb25jdXJyZW50VXNlIjpmYWxzZSwicHJvZHVjdHMiOlt7ImNvZGUiOiJEUE4iLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJEQiIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IlBTIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiSUkiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJSU0MiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJHTyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IkRNIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiUlNGIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiUEMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJSQyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IkNMIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiV1MiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJSRCIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IlJTMCIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IlJNIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiQUMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJSU1YiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJEQyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IlJTVSIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9LHsiY29kZSI6IkRQIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiUERCIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiUFdTIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiUFNJIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5In0seyJjb2RlIjoiUENXTVAiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJQUFMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJQR08iLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJQUEMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJQUkIiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJQU1ciLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkifSx7ImNvZGUiOiJSUyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSJ9XSwiaGFzaCI6IjI2MDM0MTc3LzA6LTIyNDU2NjQ0NSIsImdyYWNlUGVyaW9kRGF5cyI6NywiYXV0b1Byb2xvbmdhdGVkIjpmYWxzZSwiaXNBdXRvUHJvbG9uZ2F0ZWQiOmZhbHNlfQ==-q/+BqoUmMy43f3bVHXVnWMI5HPhQvjcMPzvIBkwG8Z0mMHaQnGamDIiYPT0pUr8ui39PBliZ8ZKe07aOzKUN9FqZcGUOXc2todcPP2kv/0xP6tmvYvI7z574GjYvyvOnzfTvXd8elzF/w4imvmgH28D2q1Okvqr5OdWuw6KpGpgA4CV70QLs3xWSVjEdmb9+rkXTyfpJ/7g4U5ad40QmmunOL3KwvO0RzH5mw7BF314ZS0w9Zh80LiGWSlg+/q7+p3Ci2wNbrmBVHlvXW4GkSIrkwglkn0NcTD9kjPdmNNnF1xPvkuTBDuHmD+ENtIB+9ZECI/NYEp2OLlr/4EEwxQ==-MIIETDCCAjSgAwIBAgIBDTANBgkqhkiG9w0BAQsFADAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBMB4XDTIwMTAxOTA5MDU1M1oXDTIyMTAyMTA5MDU1M1owHzEdMBsGA1UEAwwUcHJvZDJ5LWZyb20tMjAyMDEwMTkwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDCP4uk4SlVdA5nuA3DQC+NsEnZS9npFnO0zrmMWcz1++q2UWJNuGTh0rwi+3fUJIArfvVh7gNtIp93rxjtrQAuf4/Fa6sySp4c32MeFACfC0q+oUoWebhOIaYTYUxm4LAZ355vzt8YeDPmvWKxA81udqEk4gU9NNAOz1Um5/8LyR8SGsSc4EDBRSjcMWMwMkYSauGqGcEUK8WhfplsyF61lKSOFA6VmfUmeDK15rUWWLbOMKgn2cxFA98A+s74T9Oo96CU7rp/umDXvhnyhAXSukw/qCGOVhwKR8B6aeDtoBWQgjnvMtPgOUPRTPkPGbwPwwDkvAHYiuKJ7Bd2wH7rAgMBAAGjgZkwgZYwCQYDVR0TBAIwADAdBgNVHQ4EFgQUJNoRIpb1hUHAk0foMSNM9MCEAv8wSAYDVR0jBEEwP4AUo562SGdCEjZBvW3gubSgUouX8bOhHKQaMBgxFjAUBgNVBAMMDUpldFByb2ZpbGUgQ0GCCQDSbLGDsoN54TATBgNVHSUEDDAKBggrBgEFBQcDATALBgNVHQ8EBAMCBaAwDQYJKoZIhvcNAQELBQADggIBAB2J1ysRudbkqmkUFK8xqhiZaYPd30TlmCmSAaGJ0eBpvkVeqA2jGYhAQRqFiAlFC63JKvWvRZO1iRuWCEfUMkdqQ9VQPXziE/BlsOIgrL6RlJfuFcEZ8TK3syIfIGQZNCxYhLLUuet2HE6LJYPQ5c0jH4kDooRpcVZ4rBxNwddpctUO2te9UU5/FjhioZQsPvd92qOTsV+8Cyl2fvNhNKD1Uu9ff5AkVIQn4JU23ozdB/R5oUlebwaTE6WZNBs+TA/qPj+5/wi9NH71WRB0hqUoLI2AKKyiPw++FtN4Su1vsdDlrAzDj9ILjpjJKA1ImuVcG329/WTYIKysZ1CWK3zATg9BeCUPAV1pQy8ToXOq+RSYen6winZ2OO93eyHv2Iw5kbn1dqfBw1BuTE29V2FJKicJSu8iEOpfoafwJISXmz1wnnWL3V/0NxTulfWsXugOoLfv0ZIBP1xH9kmf22jjQ2JiHhQZP7ZDsreRrOeIQ/c4yR8IQvMLfC0WKQqrHu5ZzXTH4NO3CwGWSlTY74kE91zXB5mwWAx1jig+UXYc2w4RkVhy0//lOmVya/PEepuuTTI4+UJwC7qbVlh5zfhj8oTNUXgN0AOc+Q0/WFPl1aw5VV/VrO8FCoB15lFVlpKaQ1Yh+DVU8ke+rt9Th0BCHXe0uZOEmH0nOnH/0onD
                      
      Key -2
      --------
                  
            BQDN55OGPC-eyJsaWNlbnNlSWQiOiJCUURONTVPR1BDIiwibGljZW5zZWVOYW1lIjoi5rC45LmF5r+A5rS7IHd3d8K3YWppaHVvwrdjb20iLCJhc3NpZ25lZU5hbWUiOiIiLCJhc3NpZ25lZUVtYWlsIjoiIiwibGljZW5zZVJlc3RyaWN0aW9uIjoiIiwiY2hlY2tDb25jdXJyZW50VXNlIjpmYWxzZSwicHJvZHVjdHMiOlt7ImNvZGUiOiJEUE4iLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IkRCIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5IiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJQUyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiSUkiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IlJTQyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJHTyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiRE0iLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IlJTRiIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQQyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUkMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IkNMIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5IiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJXUyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUkQiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IlJTMCIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUk0iLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IkFDIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5IiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJSU1YiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiREMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IlJTVSIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiRFAiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUERCIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5IiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBXUyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQU0kiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUENXTVAiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUFBTIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5IiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBHTyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQUEMiLCJwYWlkVXBUbyI6IjIwMjEtMDktMjkiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUFJCIiwicGFpZFVwVG8iOiIyMDIxLTA5LTI5IiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBTVyIsInBhaWRVcFRvIjoiMjAyMS0wOS0yOSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJSUyIsInBhaWRVcFRvIjoiMjAy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


    Key- 3
    ------
              BISACXYELK-eyJsaWNlbnNlSWQiOiJCSVNBQ1hZRUxLIiwibGljZW5zZWVOYW1lIjoiQ2hpbmFOQiIsImFzc2lnbmVlTmFtZSI6IiIsImFzc2lnbmVlRW1haWwiOiIiLCJsaWNlbnNlUmVzdHJpY3Rpb24iOiIiLCJjaGVja0NvbmN1cnJlbnRVc2UiOmZhbHNlLCJwcm9kdWN0cyI6W3siY29kZSI6IklJIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJBQyIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiRFBOIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlJTQyIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQUyIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUlNGIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IkdPIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJETSIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJDTCIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUlMwIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlJDIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlJEIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJQQyIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUlNWIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlJTVSIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiUk0iLCJwYWlkVXBUbyI6IjIwOTktMTItMzEiLCJleHRlbmRlZCI6ZmFsc2V9LHsiY29kZSI6IldTIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJEQiIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjpmYWxzZX0seyJjb2RlIjoiREMiLCJwYWlkVXBUbyI6IjIwOTktMTItMzEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUERCIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBXUyIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQR08iLCJwYWlkVXBUbyI6IjIwOTktMTItMzEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUFBTIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBQQyIsInBhaWRVcFRvIjoiMjA5OS0xMi0zMSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQUkIiLCJwYWlkVXBUbyI6IjIwOTktMTItMzEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUFNXIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IkRQIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlJTIiwicGFpZFVwVG8iOiIyMDk5LTEyLTMxIiwiZXh0ZW5kZWQiOnRydWV9XSwibWV0YWRhdGEiOiIwMTIwMjAwNzI4RVBKQTAwODAwNiIsImhhc2giOiIxNTAyMTM1NC8wOi0xMjUxMTE0NzE3IiwiZ3JhY2VQZXJpb2REYXlzIjowLCJhdXRvUHJvbG9uZ2F0ZWQiOmZhbHNlLCJpc0F1dG9Qcm9sb25nYXRlZCI6ZmFsc2V9-H7NUmWcLyUNV1ctnlzc4P79j15qL56G0jeIYWPk/HViNdMg1MqPM7BR+aHR28yyuxK7Odb2bFDS8CeHNUtv7nT+4fUs85JJiqc3wc1psRpZq5R77apXLOmvmossWpbAw8T1hOGV9IPUm1f2O1+kLBxrOkdqPpv9+JanbdL7bvchAid2v4/dyQMBYJme/feZ0Dy2l7Jjpwno1TeblEAu0KZmarEo15or5RUNwtaGBL5+396TLhnw1qL904/uPnGftjxWYluLjabO/uRu/+5td8UA/39a1nvGU2nORNLk2IdRGIheiwIiuirAZrII9+OxB+p52i3TIv7ugtkw0E3Jpkw==-MIIDlzCCAn+gAwIBAgIBCTANBgkqhkiG9w0BAQsFADAYMRYwFAYDVQQDEw1KZXRQcm9maWxlIENBMCAXDTE4MTEwMTEyMjk0NloYDzIwOTkwODA5MDIyNjA3WjBoMQswCQYDVQQGEwJDWjEOMAwGA1UECBMFTnVzbGUxDzANBgNVBAcTBlByYWd1ZTEZMBcGA1UEChMQSmV0QnJhaW5zIHMuci5vLjEdMBsGA1UEAxMUcHJvZDN5LWZyb20tMjAxODExMDEwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCdXyaNhhRySH1a8d7c8SlLLFdNcQP8M3gNnq7gudcpHC651qxRrN7Qks8gdXlIkA4u3/lp9ylp95GiIIDo4ydYje8vlTWDq02bkyWW/G7gZ3hkbBhRUK/WnNyr2vwWoOgwx5CfTRMjKkPkfD/+jffkfNfdGmGcg9yfnqPP9/AizKzWTsXSeS+0jZ8Nw5tiYFW+lpceqlzwzKdTHug7Vs0QomUPccRtZB/TBBEuiC7YzrvLg4Amu0I48ETAcch/ztt00nx/oj/fu1DTnz4Iz4ilrNY+WVIEfDz/n3mz+PKI9kM+ZeB0jAuyLsiC7skGpIVGX/2HqmZTtJKBZCoveAiVAgMBAAGjgZkwgZYwSAYDVR0jBEEwP4AUo562SGdCEjZBvW3gubSgUouX8bOhHKQaMBgxFjAUBgNVBAMMDUpldFByb2ZpbGUgQ0GCCQDSbLGDsoN54TAJBgNVHRMEAjAAMBMGA1UdJQQMMAoGCCsGAQUFBwMBMAsGA1UdDwQEAwIFoDAdBgNVHQ4EFgQUYSkb2hkZx8swY0GRjtKAeIwaBNwwDQYJKoZIhvcNAQELBQADggEBAJZOakWgjfY359glviVffBQFxFS6C+4WjYDYzvzjWHUQoGBFKTHG4xUmTVW7y5GnPSvIlkaj49SzbD9KuiTc77GHyFCTwYMz+qITgbDg3/ao/x/be4DD/k/byWqW4Rb8OSYCshX/fNI4Xu+hxazh179taHX4NaH92ReLVyXNYsooq7mE5YhR9Qsiy35ORviQLrgFrMCGCxT9DWlFBuiPWIOqN544sL9OzFMz+bjqjCoAE/xfIJjI7H7SqGFNrx/8/IuF0hvZbO3bLIz+BOR1L2O+qT728wK6womnp2LLANTPbwu7nf39rpP182WW+xw2z9MKYwwMDwGR1iTYnD4/Sjw=


  


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
       
       
       
       
       Import Existing Database
       -------------------------
             - mysql -u username -p database_name < file.sql          -  Syntax for import existing database file                      - 







### Docker Command
--------------------






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
                               
    
    
    
    
    
    






