# oracle linux for nas docker

```shell
docker run \
--name nas_oracle_xe_11 \
-d \
-p 42151:1521 \
-e ORACLE_ALLOW_REMOTE=true \
oracleinanutshell/oracle-xe-11g
```