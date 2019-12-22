# easy-zabbix
make zabbix installation easier again 

## install dependencies
    sudo apt-get update
    sudo apt install -y apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

## install docker-ce
    curl -fsSL https://get.docker.com -o get-docker.sh
    sudo sh get-docker.sh
    
## install docker-compose
    sudo curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
    sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

## clone repo
    git clone https://github.com/akenamon/easy-zabbix.git
    cd easy-zabbix
    
## Create folder for store zabbix database 
    sudo mkdir /docker/mysql/zabbix/data
  
## Start zabbix stack
    sudo docker-compose -f docker-compose-easy-zabbix.yml up -d 
 
 ### You could easily stop all related services with
    sudo docker-compose -f docker-compose-easy-zabbix.yml up -d 
     
 
 # Enviroment 
 #### Those are the default user and password, They are just examples, plese modify it before deploying on production.
    - MYSQL_ROOT_PASSWORD=secret
    - MYSQL_DATABASE=zabbix
    - MYSQL_USER=zabbix
    - MYSQL_PASSWORD=zabbix

 #### You should adjust for your own timezone
    - PHP_TZ=America/Sao_Paulo

    


