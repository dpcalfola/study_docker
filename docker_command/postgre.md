## command

```shell
docker run \
--name fola_postgres \
-v /Users/folaflor/docker_volumes/fola_postgres:/var/lib/postgresql/data \
-p 45432:5432 \
-e POSTGRES_USER=folaflor \
-e POSTGRES_PASSWORD=${MY_KEY_1} \
-d \
postgres
```
