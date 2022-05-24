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

