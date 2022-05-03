# CentOS docker - failed
* privileged 모드 : 환경설정과 관련한 권한에 필요
* port 개방: 54982:22
* volume path : /home/fola/dockerVolumes/FolaCentOS:/sharedVolume



```shell
docker run \
-i -t \
--privileged=true \
--name FolaCentOS \
-v /home/fola/dockerVolumes/FolaCentOS:/sharedVolume \
-p 54982:22 \
centos

```

```shell
docker start FolaCentOS
```

```shell
docker attach FolaCentOS
```

# systememd dockerfile centos - failed

```shell
docker run \
-i -t \
--privileged=true \
--name FolaCentOS \
-v /home/fola/dockerVolumes/FolaCentOS:/sharedVolume \
-p 54982:22 \
c7-systememd

```