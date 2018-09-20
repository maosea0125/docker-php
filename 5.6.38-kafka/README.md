# docker-php
> docker centos7  php rdkafka

### 环境
```php
   系统: centos7
    php: php-5.6.38
php扩展:
    bcmath, Core, ctype, curl, date, dom, fileinfo, filter, gd, gettext, hash, iconv, json, libxml, mbstring, mysqli, mysqlnd, openssl, pcntl, pcre, PDO, pdo_mysql, pdo_sqlite, Phar, posix, rdkafka, Reflection, session, SimpleXML, sockets, SPL, sqlite3, standard, sysvsem, tokenizer, xml, xmlreader, xmlrpc, xmlwriter, xsl, zip, zlib
```

**php目录**

```
/usr/local/php
```

### 使用方式1
```sh
# 构建镜像
docker build -t "qq1060656096/php:5.6.38-kafka" 5.6.38-kafka
# 启动容器
docker run -tid --name php-kafka qq1060656096/php:5.6.38-kafka
# 进入容器
docker exec -ti php-kafka /bin/bash
# 查看容器nginx状态
查看容器php-fpm状态
docker exec -i php-kafka/bin/bash -c "ps -ef | grep php-fpm"
# 删除镜像
docker rm -f php-kafka
#查看镜像
docker ps
```


### 使用方式2
```sh
# 构建镜像
docker build -t "qq1060656096/php:5.6.38-kafka" 5.6.38-kafka
# 启动容器
docker run -tid -p 1090:9000 --name php-kafka qq1060656096/php:5.6.38-kafka /usr/local/php/sbin/php-fpm -F
# 进入容器
docker exec -ti php-kafka /bin/bash
# 查看容器nginx状态
docker exec -ti php-kafka /bin/bash -c "ps -ef | grep php-fpm"
# 删除镜像
docker rm -f php-kafka
```