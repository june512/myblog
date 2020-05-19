---
title: "AWS_EC2_웹서버(2)"
date: 2020-05-19T17:49:16+09:00
---

![99E3013E5B6070632E](https://user-images.githubusercontent.com/65329769/82184818-32003180-9923-11ea-8253-218a20c2c296.jpg)

이 화면은 (1)편에서 아파치 서버 설치 후 확인할 때 나타나는 화면의 일부입니다.
화면에서 스크롤을 조금 내려보면 document root directory, ubuntu document root가 어디인지 확인할 수 있습니다.
html폴더 안에 파일을 올려야 publicDNS/파일이름 으로 웹 브라우저에서 접근 가능합니다.

# 데이터베이스
```
sudo apt-get update //패키지 업데이트 
sudo apt-get install mysql-server
```

```
mysql -uroot -p //mysql root 계정 접속 
show databases; //db 확인 
exit //mysql 나와서 다시 리눅스로
```

![99B4A2495B6072020A](https://user-images.githubusercontent.com/65329769/82185207-d4201980-9923-11ea-94c4-81f03ac93e8f.jpg)


# PHP
```
sudo add-apt-repository ppa:ondrej/php          //보안을 위한 저장소 추가
sudo apt-get update                             //저장소에서 패키지 업데이트
sudo apt-get install php                        //했더니 php 7.x 설치됨
php -v                                          //버전 확인
```
vi편집기로 php 파일 작성해서 (파일 이름이 test.php라면)

```
<?php
phpinfo();
?>
```
웹 브라우저에서 publicDNS/test.php 입력하면 아래와 같은 화면 확인 가능.

![998B2D495B60706328](https://user-images.githubusercontent.com/65329769/82185413-1f3a2c80-9924-11ea-8932-97d37ed01f01.jpg)

# git 설치
bitbucket사용
```
sudo apt-get install git git clone ~ //git repository를 놓을 곳에서 하기! 
git pull origin master //bitbucket에 올려놓은 파일 끌어오기
```

# filezilla 이용
설치 사이트 : <https://filezilla-project.org/download.php>

파일-사이트관리자

![991C5A465B6070630E](https://user-images.githubusercontent.com/65329769/82185620-76400180-9924-11ea-8469-1651a687f7f2.jpg)

![991E74455B60706324](https://user-images.githubusercontent.com/65329769/82185647-848e1d80-9924-11ea-9e38-3cc212b5db99.jpg)

 파일을 마우스로 끌어다 놓으면 단순하게 파일을 서버로 업로드 가능!

출처 : <https://woodforest.tistory.com/280?category=860525>