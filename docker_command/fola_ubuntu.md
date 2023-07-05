```shell
docker run \
-i -t \
--privileged=true \
--name fola_ububtu \
--hostname fola_ubuntu \
-v ~/docker_volume/fola_ubuntu_home:/home \
ubuntu:22.04
```

```shell
docker run \
-i -t \
--name fola_ububtu \
--hostname fola_ubuntu \
-v ~/docker_volume/fola_ubuntu_home:/home \
ubuntu:22.04
```



* docker exec:
  * docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```shell
docker exec -it 0060 /bin/bash
```