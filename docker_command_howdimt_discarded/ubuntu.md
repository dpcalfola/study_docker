```shell
docker run -i -t \
--privileged \
--name howdimt_ubuntu \
-v /Users/folaflor/docker_volumes/howdimt:/work_dir \
ubuntu
```

```shell
passwd root

apt-get update
apt-get upgrade -y
apt-get install net-tools -y
apt-get install neovim -y
apt-get install openssh-server -y
```

> 2
>

