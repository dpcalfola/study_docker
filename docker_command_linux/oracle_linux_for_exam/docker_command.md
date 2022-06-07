# oracle linux for ubuntu laptop

```shell
docker run \
-i -t \
--privileged=true \
--name FolaOracleLinux \
-v /home/fola/dockerVolumes/FolaOracleLinux:/sharedVolume \
-p 54982:22 \
oraclelinux:8.5
```

<Br>

# oracle linux for mac studio

### volume ro(read-only) test

* result :
    * volume mounted but can't write or modify inside of container although container's root has writing authority for
      mounted volume
    * It means volume is synchronized only one-side. So host volume will be protected from container

```shell
docker run \
-i -t \
--privileged=true \
--name FolaOracleLinux_ro_test \
-v ~/docker_volume/test_ro/:/test_ro:ro \
oraclelinux:8.6
```

### docker run with mounting volume which has timezone data from mac

(failed)

```shell
docker run \
-i -t \
--privileged=true \
--name FolaOracleLinux \
-v ~/docker_volume/oraclelinux_for_exam_home:/home \
oraclelinux:8.6
```