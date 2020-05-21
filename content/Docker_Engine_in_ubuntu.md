---
title: "Docker_Engine_in_ubuntu"
date: 2020-05-21T12:47:08+09:00
---

# 전제 조건

## OS 요구 사항

Docker Engine을 설치하려면 다음 Ubuntu 버전 중 하나의 64 비트 버전이 필요

    -우분투 Eoan 19.10
    -우분투 바이오닉 18.04 (LTS)
    -우분투 제니 얼 16.04 (LTS)


## 이전 버전 제거
<ul>
    <li>docker, docker.io 또는 docker-engine 설치되어 있으면 제거</li>
</ul>

```
$ sudo apt-get remove docker docker-engine docker.io containerd runc
```

# 설치

## 저장소를 사용하여 설치
1. HTTPS를 통해 저장소를 사용할 수 있도록 패키지 색인을 업데이트하고 패키지를 설치

```
    $ sudo apt-get update

    $ sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        gnupg-agent \
        software-properties-common
```

2. Docker의 공식 GPG 키를 추가
```
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

3. 안정된 저장소 를 설정하려면 다음 명령을 사용

```
    $ sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

## DOCKER ENGINE 설치

1. apt패키지 색인을 업데이트하고 최신 버전의 Docker Engine 및 컨테이너를 설치하거나 다음 단계로 이동하여 특정 버전을 설치
    ```
        $ sudo apt-get update
        $ sudo apt-get install docker-ce docker-ce-cli containerd.io
    ```

2. 특정 버전 의 Docker Engine을 설치하려면 저장소에 사용 가능한 버전을 나열한 후 다음을 선택하고 설치
    a.  리포지토리에서 사용 가능한 버전을 나열하기
        ```
            $ apt-cache madison docker-ce

            docker-ce | 5:18.09.1~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
            docker-ce | 5:18.09.0~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
            docker-ce | 18.06.1~ce~3-0~ubuntu       | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
            docker-ce | 18.06.0~ce~3-0~ubuntu       | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
            ...
        ```

    b. 두 번째 열의 버전 문자열을 사용하여 특정 버전을 설치하기 (예 : 5:18.09.1~3-0~ubuntu-xenial)
        ```
            $ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io

            -> $ sudo apt-get install docker-ce=5:18.09.1~3-0~ubuntu-xenial docker-ce-cli=5:18.09.1~3-0~ubuntu-xenial containerd.io
        ```
3. hello-world 이미지 를 실행하여 Docker Engine이 올바르게 설치되었는지 확인하기
    ```
        $ sudo docker run hello-world
    ```
## 패키지에서 설치
1. https://download.docker.com/linux/ubuntu/dists/ 다음를 찾아 여러분의 우분투 버전을 선택 pool/stable/을 선택, amd64, armhf, arm64, ppc64el, 또는 s390x, 그리고 다운로드 .deb설치하려는 도커 엔진 버전 파일이동

2. 아래 경로를 Docker 패키지를 다운로드 한 경로로 변경하여 Docker Engine을 설치
    ```
        $ sudo dpkg -i /path/to/package.deb
    ```
3. hello-world 이미지 를 실행하여 Docker Engine이 올바르게 설치되었는지 확인
    ```
        $ sudo docker run hello-world
    ```

### DOCKER ENGINE 업그레이드
    Docker Engine을 업그레이드하려면 최신 패키지 파일을 다운로드하고 새 파일을 가리키는 설치 절차를 반복

# Docker Engine  제거
1. Docker Engine, CLI 및 컨테이너 패키지를 설치 제거
```
    $ sudo apt-get purge docker-ce docker-ce-cli containerd.io
```

2. 호스트의 이미지, 컨테이너, 볼륨 또는 사용자 정의 구성 파일은 자동으로 제거되지 않음. 모든 이미지, 컨테이너 및 볼륨을 삭제하려면...
```
    $ sudo rm -rf /var/lib/docker
```
## 다음 단계

    -Linux의 설치 후 단계를 계속 하십시오 .
    -Docker 로 개발 에서 주제를 검토하여 Docker 를 사용하여 새 애플리케이션을 빌드하는 방법을 학습하십시오.



출처 : <https://docs.docker.com/engine/install/ubuntu/#prerequisites>