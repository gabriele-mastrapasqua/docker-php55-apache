# php 5.5 plus apache
installed dependencies: php 5.5,  php5-cli php5-common php5-curl php5-json php5-mcrypt php5-readline 

## 1) - build the Dockerfile
```
docker build -t php-55-apache .
```

## 2) - run container

```
docker run -d -p 8090:80 --rm --name php-55-apache -v $(pwd)/.:/var/www/webapp -v $(pwd)/conf/vhost.conf:/etc/apache2/sites-available/000-default.conf php-55-apache
```

----

# 3) install composer dependencies (optionally)

```
docker exec -it php-55-apache composer install
```

