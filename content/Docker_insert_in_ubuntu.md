---
title: "Docker_insert_in_ubuntu"
date: 2020-05-21T12:28:08+09:00
---

# 기존 도커 설치 버전을 제거
sudo apt-get remove docker docker-engine docker.io containerd runc


# 저장소를 업데이트 한다.
sudo apt-get update


# apt 가 https 저장소를 사용할 수 있도록 설치한다.
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common


# 도커 저장소 키를 apt에 등록한다.
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -


# 아래 명령어로 docker-ce 키가 등록되었는지 확인한다.
sudo apt-key fingerprint 0EBFCD88

```
pub rsa4096 2017-02-22 [SCEA] 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88

uid [ unknown] Docker Release (CE deb) <docker@docker.com>

sub rsa4096 2017-02-22 [S]
```
 

# 도커 저장소를 등록한다.
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
 

```
stable는 안정판인데 목적에 따라 nightly, test 를 사용할 수 있다.

$(lsb_release -cs) 는 현재 명령이 실행되는 우분투 배포판 이름을 가져온다.

필요하다면 직접 넣을 수 있다. ex) precise 등.
```
 

# 저장소를 등록했다면 apt 업데이트 해준다.
sudo apt-get update
 

# 도커를 설치한다.
sudo apt-get install docker-ce docker-ce-cli containerd.io
 

# 도커의 특정 버전 설치를 원한다면 아래 단계를 따른다.

# 도커 설치 가능 버전 목록 확인하기
apt-cache madison docker-ce

```
docker-ce | 5:18.09.1~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu xenial/stable ...

docker-ce | 5:18.09.0~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu xenial/stable ...

docker-ce | 18.06.1~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable ...

docker-ce | 18.06.0~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable ...
```
 

# 위 버전 중 원하는 버전을 입력하여 설치한다.

sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io

```
ex) sudo apt-get install docker-ce=18.06.1~ce~3-0~ubuntu docker-ce-cli=18.06.1~ce~3-0~ubuntu containerd.io
```
 

 

# 도커 설치 확인

sudo docker version

sudo docker run hello-world

 

 

# 도커 root 외의 사용자도 사용할 수 있도록 권한 추가하기

# 도커 권한 확인하기

cat /etc/group | grep docker
docker:x:999:

 

 

# 도커 그룹에 사용할 사용자 아이디 추가
sudo usermod -aG docker 사용할아이디

```
ex) sudo usermod -aG docker iamdeveloper
```
 

# 실행 후 확인하면 아래와 같이 사용자 아이디 추가됨
cat /etc/group | grep docker

```
docker:x:999:iamdeveloper
```
 

# 시스템을 재 시작하여 사용자 권한으로 도커 사용 가능한지 확인
sudo reboot

 
# 사용자 계정으로 도커 사용 확인
docker version

 
# Client: 와 Server: 정보가 나오면 사용 가능함.

# 아래 메시지가 나오면 권한 설정이 제대로 된 것이 아니므로 다시 설정시도하거나 관련 메시지로 구글링하여 해결한다.
```
Got permission denied while trying to connect to the Docker daemon socket
```