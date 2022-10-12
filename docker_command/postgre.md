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


#### postgres run command for local use

```shell
docker run \
--name fola_studio_postgres \
-v fola_studio_postgres:/var/lib/postgresql/data \
-p ${FOLA_POSTGRES_PORT}:5432 \
-e POSTGRES_DB=${FOLA_POSTGRES_DB} \
-e POSTGRES_USER=${FOLA_POSTGRES_DB} \
-e POSTGRES_PASSWORD=${FOLA_POSTGRES_PASSWORD} \
-d \
postgres:15rc2-alpine3.16
```