```shell
docker run \
-d \
-e "ACCEPT_EULA=Y" \
-e "SA_PASSWORD=m!osdjkFAGowquig978*" \
-p 51343:1433 \
--name nas_sql-server \
mcr.microsoft.com/mssql/server:2019-latest
```