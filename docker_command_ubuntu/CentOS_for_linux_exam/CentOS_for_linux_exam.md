# CentOS 7 docker - 성공
* privileged 모드 : 환경설정과 관련한 권한에 필요
* port 개방: 54982:22
* volume path : /home/fola/dockerVolumes/FolaCentOS:/sharedVolume

## centos 8 버전은 지원 종료되었음. -> yum 사용 불가
* centos:centos7 이미지로 컨테이너 생성할 것
* centos7 ->


```shell
docker run \
-i -t \
--privileged=true \
--name FolaCentOS \
-v /home/fola/dockerVolumes/FolaCentOS:/sharedVolume \
-p 54983:22 \
centos:centos7

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



# CentOS stream 9 - latest version
```shell
docker run \
-i -t \
--privileged=true \
--name CentStream9 \
-v /home/fola/dockerVolumes/FolaCentStream9_home:/home \
-p 54984:22 \
quay.io/centos/centos:stream9
```