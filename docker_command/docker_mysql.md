```shell
docker run \
--platform linux/amd64 \
-e MYSQL_ROOT_PASSWORD=p123456 \
-p 48921:3306 \
--name m1-mysql-1 \
-v /Users/folaflor/docker_volumes/mysql_data:/var/lib/mysql \
-d \
mysql
```