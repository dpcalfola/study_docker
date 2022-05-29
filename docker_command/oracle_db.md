# oracle linux for nas docker

```shell
docker run \
--name nas_oracle_xe_11 \
-d \
-p 42151:1521 \
-e ORACLE_ALLOW_REMOTE=true \
oracleinanutshell/oracle-xe-11g
```

```shell
docker run \
--name sqld_oracle_xe_11 \
-v /volume1/docker/oracle_data/sqld:/sqld \
-d \
-p 42152:1521 \
-e ORACLE_ALLOW_REMOTE=true \
oracleinanutshell/oracle-xe-11g
```

```shell
docker run \
--name sqld2_oracle_xe_11 \
-v /volume1/docker/oracle_data/sqld:/sqld \
-d \
-p 42153:1521 \
-e ORACLE_ALLOW_REMOTE=true \
oracleinanutshell/oracle-xe-11g
```



```shell
docker commit \
-a "folaSmile" \
-m "sqld_oracle_backup" \
sqld_oracle_xe_11 \
sqld_oracle_xe_11:v1.0
```