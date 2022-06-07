```shell
docker run \
-i -t \
--privileged=true \
--name ubuntu_for_linux_exam \
-v ~/docker_volume/ubuntu_for_exam_home:/home \
ubuntu
```

```shell
docker run \
-i -t \
--privileged=true \
--name ubuntu_for_linux_exam_2 \
--hostname exam_ubuntu \
-v ~/docker_volume/ubuntu_for_exam_home:/home \
ubuntu
```

### how to set local timezone in ubuntu docker container

```shell
apt-get install tzdata
```


### install apt-get
```shell
apt-get install uuid -y

```