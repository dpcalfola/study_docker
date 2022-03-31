# How to docker image commit and push

<hr>

## Make container

### *command

docker run -i -t \
--name fola_ubuntu \
-v /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes/fola_ubuntu_home:/home \
-p 61265:61265 \
ubuntu

<hr>

## Commit

> -a : author

> -m : commit message

> fola_ubuntu : container name

> fola_ubuntu_image : image name

> v1 : tag(version)

### *command

docker commit \
-a "folaSmile" \
-m "fola ubuntu setting commit" \
fola_ubuntu \
fola_ubuntu_image:v1

<hr>

## Make tag

> docker tag local-image:tagname new-repo:tagname

> docker push new-repo:tagname

### *command

docker tag \
fola_ubuntu_image:v1 \
dpcalfola/fola_ubuntu:v1

<hr>

## Image push

> docker push dpcalfola/fola_ubuntu:tagname
>

###  * command

docker push dpcalfola/fola_ubuntu:v1


<hr>

## run from my image

docker run -i -t \
--name fola_ubuntu_v1 \
-v /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes/fola_ubuntu_home:/home \
fola_ubuntu_image:v1
