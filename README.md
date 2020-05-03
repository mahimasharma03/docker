# docker
it is project of docker using joomla


version: '3'


service:
  joomladb:
   volumes:
    - mysql_storage_new:/var/lib/mysql
    restart: always
    envirnment:
      MySQL_ROOT_PASSWORD: rootpass
      MYSQL_USER: mahima
      MYSQLL_PASSWORD:redhat
      MYSQL_DATABASE:mydb
      
   joolmaos:
    image: joomla:3.9-php7-apache
    restart : always
    depends_on:
        -joomladb
        
    ports:
        -80:80
    environment :
      JOOMLA_DB_HOST: joomladb:3306
      JOOMLA_DB_USER: mahima
      JOOMLA_DB_PASSWORD: redhat
      JOOMLA_DB_NAME: mydb
     volumes:
      - jm_storage_new:/var/www/html
     volumes:
            mysql_storage_new:
            jm_storage_new:
