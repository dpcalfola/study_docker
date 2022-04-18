## command

```shell
docker run \
--name w_idid_postgres \
-v /Users/folaflor/Desktop/coding/2022y_projects/What_IDid/db_data:/var/lib/postgresql/data \
-p ${W_IDid_DB_PORT}:5432 \
-e POSTGRES_USER=${W_IDid_DB_USER} \
-e POSTGRES_PASSWORD=${MY_KEY_1} \
-d \
postgres
```

/Users/folaflor/Desktop/coding/2022y_projects/What_IDid/db_data