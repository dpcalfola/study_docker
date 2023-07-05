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
-e POSTGRES_USER=${FOLA_POSTGRES_USER} \
-e POSTGRES_PASSWORD=${FOLA_POSTGRES_PASSWORD} \
-d \
postgres:15rc2-alpine3.16 && \
docker ps
```

* Command to discard all this container data 
```shell
docker stop fola_studio_postgres ; \
docker rm fola_studio_postgres ; \
docker volume rm fola_studio_postgres ; \
docker rmi postgres:15rc2-alpine3.16
```

#### postgres run command for interview

```shell
docker run \
--name fola_studio_postgres_interview \
-p 5432:5432 \
-e POSTGRES_DB=interview_postgres \
-e POSTGRES_USER=interview_postgres_user \
-e POSTGRES_PASSWORD=interview_password \
-d \
postgres:15.2-bullseye
docker ps
```