<h1>도커 공유 볼륨 (리눅스) </h1>
<br>
<br>


> <h2> 1. 알파인 볼륨 마운트 시도 (1) </h2> 

<br>

* path : /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes
  * /alpine_vol_01
* 결과 : 
  * 마운팅 된 볼륨에 리눅스 커맨드 명령어 로그 파일만 생성됨.
  * vi 으로 텍스트 파일을 만들어 봤으나 공유되지 않음.
* docker command

  docker run -i -t \
  --name alpine_volume \
  -v /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes/alpine_vol_01:/root/ \
  alpine

<br>
<hr>
<br>
<br>

> <h2> 2. 알파인 볼륨 마운트 시도 (2) </h2>

<br>

* 시도 : alpine 리눅스 내의 home 폴더를 지정하여 공유 시도

* 컨테이너 이름: alpine_volume_02
  
* path : /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes
  * /alpine_vol_02_home
  * alpine_vol_02_home:/home

* 결과 :
  * 로컬 디렉터리와 컨테이너 디렉터리간 완전한 볼륨 공유 확인
  * 리눅스 내에 /root 라는 디렉터리가 존재함을 확인. 
    * 이곳에 컨내이너 내부에서 사용한 명령어들이 로그로 남는다는 것을 알아냄

* docker command

  docker run -i -t \
  --name alpine_volume_02 \
  -v /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes/alpine_vol_02_home:/home \
  alpine


<br>
<hr>
<br>
<br>


> <h2> 3. 두개의 우분투 볼륨 마운트 시도 (1) </h2>
* 시도 : /share_vol 디렉터리를 양쪽 우분투에서 공유 할 수 있는지?
  * 컨테이너 생성시 /share_vol 디렉터리가 자동으로 생성 되는지?

* 컨테이너 이름 : 
  * ubuntu_vol_01
  * ubuntu_vol_02

* path :
  * /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes
    * /ubuntu_home_share_vol
    
* 결과
  * 디렉터리를 양쪽 컨테이너 모두에서 공유 가능 확인 
  * 컨테이너 생성시 볼륨으로 지정한 디렉터리가 없다면 자동 생성 확인 

* 참고
  * dockerhub ubuntu official image 에는 vi 나 vim 이 내장되어 있지 않음
  * cat 명령어를 이용하여 파일을 생성하거나 읽음

* docker command
  
  docker run -i -t \
  --name ubuntu_vol_01 \
  -v /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes/ubuntu_home_share_vol:/share_vol \
  ubuntu

  docker run -i -t \
  --name ubuntu_vol_02 \
  -v /Users/folaflor/Desktop/coding/project_2022y/study_docker/volumes/ubuntu_home_share_vol:/share_vol \
  ubuntu
 
  
<br>


> <h2> 4. 테스트를 종료하고 모든 컨테이너와 로컬 삭제함 </h2>

* docker command
  
  docker stop $(docker ps -q) \
  docker rm $(docker ps -a -q) 
