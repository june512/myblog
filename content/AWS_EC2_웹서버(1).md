# -*- encoding: utf-8 -*-
---
title: "AWS_EC2_웹서버(1)"
date: 2020-05-19T17:48:02+09:00
---

# 클러스터 생성
```
aws 공식 홈페이지에서 가이드라인을 putty로 제공하기 때문에 사용.
putty를 사용하는 이유는 서버를 구성하는 우분투 리눅스를 원격으로 연결해서 사용하기 위함이다.
putty 설치 : <https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>
```
## 1. 키 변경
.pem 확장자의 키를 .ppk확장자의 private key로 변경하는 과정이다.

putty를 통합설치하면 딸려있는 puttygen을 이용한다.

![key_1](https://user-images.githubusercontent.com/65329769/82172214-8811ac80-9904-11ea-87a3-6e7a4804e55d.jpg)

Load 클릭 - 모든 파일 - 아까 만들었던 .pem 키 선택

![key_2](https://user-images.githubusercontent.com/65329769/82172307-c1e2b300-9904-11ea-9980-1c99159fc8cd.jpg)

Save private key로 저장. (이름은 똑같이)



## 2. 설정 및 접속
<https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/putty.html> 를 참조
호스트 네임 ubuntu@(public dns)
SSH 포트22
SSH-Auth-아까 만든 .ppk 키 불러오기


# 웹 서버(아파치) 설치

putty로 연 콘솔창에 이것들을 입력
```
sudo apt-get update

sudo apt-get update sudo apt-get install apache2
```

![993F4C4A5B5D39EA2F](https://user-images.githubusercontent.com/65329769/82172488-433a4580-9905-11ea-9329-481702b86e6c.jpg)

출처 : <https://woodforest.tistory.com/279>