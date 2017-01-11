# Magento 2 Docker to Development

Apache 2.4 + PHP 7.0.8 + OPCache + MariaDB + Magerun + DevAlias

[![Build Status](https://travis-ci.org/clean-docker/Magento2.svg?branch=master)](https://travis-ci.org/clean-docker/Magento2)
[![Microbadger](https://images.microbadger.com/badges/image/rafaelcgstz/magento2.svg)](https://microbadger.com/images/rafaelcgstz/magento2 "Get your own image badge on microbadger.com")

This cluster ready docker-compose infrastructure.

### Copy and run

```
git clone https://github.com/clean-docker/Magento2.git m2-docker &&
cd m2-docker &&
docker-compose up -d ;
docker ps
```

### !Important

Default folder in your machine is `/var/www/html`, if you use **MacOS** please change this folder in your docker-compose cloned file.

### Access the container Docker

To access in you browser you can use http://localhost ( I recommend change your /etc/hosts ).

```
docker exec -ti m2docker_apache_1 bash
```

### Install Magento 2

You can access in http://localhost/magento2/

```
composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition magento2
```

### Access the MySQL

In your terminal out of the container run this command.

```
mysql -u root -proot -h 0.0.0.0
```

To know what is the IP to use in the Magento 2 installation (Database Server Host), you can use this command out the container.

```
docker inspect m2docker_db_1 | grep IPAddress
```

### License

MIT © 2017 [Rafael Corrêa Gomes](https://github.com/rafaelstz/) and contributors.
