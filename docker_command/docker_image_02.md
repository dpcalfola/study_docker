# nas 실행을 위한 도커 이미지 푸시/풀 테스트


## 테스트 환경

> MacBook Air (M1, 2020) 

> macOS Monterey

> 도커 엔진 ver - Engine: 20.10.13

> 도커 이미지 - ubuntu (official image)  

<hr>

## *command


### amd64 platform 명시

```shell
docker run -i -t \
--name nas_ubuntu \
--platform linux/amd64 \
ubuntu
``` 

### platform 명시하지 않음

```shell
docker run -i -t \
--name fola_ubuntu \
ubuntu
```
- amd64 platform 이미지가 로컬에 저장되어 있는 상태에서
플랫폼을 명시하지 않고 컨테이너 생성 -> 기존 이미지 사용 (아키텍쳐 경고 메세지 출력)

### native platform (arm64) 명시

```shell
docker run -i -t \
--name fola_ubuntu \
--platform linux/arm64/v8 \
ubuntu
```


### delete image

```shell
docker rmi dpcalfola/fola_ubuntu:v1
```

<hr>

## 결과

1. 같은 버전(태그) 같은 플랫폼의 도커 이미지는 이미지 ID 값이 같다. 
   - (이미지를 반복적으로 pull 하더라도 이미지 id값은 동일)
2. 도커를 구동하는 시스템과 다른 버전의 아키텍쳐는 --platform 명령어를 이용하여 pull 및 run 이 가능하다. 
   - (엔진 내부에서 에뮬레이팅 되어 돌아간다)
3. 도커 run 명령어 사용시 베이스 이미지가 존재하면 그 이미지가 구동 시스템과 다른 아키텍쳐일지라도 새로 pull 하지 않고 기존의 이미지를 사용한다.
4. 이후 네이티브 플랫폼의 컨테이너 생성을 위해서는 플랫폼을 명시해줘야 한다.
   - 이미지를 새로 pull 하며 새로 받은 이미지에는 latest TAG 가 붙고 기존의 이미지의 latest TAG 는 <none> 으로 바뀐다.
   - docker ps 명령어 실행 시 기존의 amd64 아키텍쳐 컨테이너의 베이스 이미지가 ubuntu 에서 IMAGE ID 로 변경된다.



<hr>


#### ** 다른 버전의 아키텍쳐로 run 할 경우 다음과 같은 경고 메세지 출력

>WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested