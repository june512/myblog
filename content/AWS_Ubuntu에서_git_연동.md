---
title: "AWS_Ubuntu에서_git_연동"
date: 2020-05-19T18:03:33+09:00
---

# AWS Ubuntu에서 git 연동


```
1. github 저장소 만들기

- 모르면 검색해서 저장소 만들어 주세요.
```

```
2. git init

2.1 AWS를 putty로 연결을 했다라는 전제 조건이 붙는다.

2.2 github에 올리고 싶은 폴더에 가서 git init을 한다.

* git init : git을 사용하기 위해 git 초기화를 하는 단계.
```

```
3. git add -(-A를 하면 현재 폴더 전체, 각개를 하려면 -test.js라고 하면 된다.)

* 깃은 3가지 stage가 있는데 working Directory(로컬저장소), Staging Area(임시저장소), Git Directory(Repository)이다.

* git add 를 사용하는건 로컬->임시저장소로 보내는 과정이다.
```

```
4.  git remote add... 후 github에 넣는 작업입니다.
```
![99A4EA415B42CE9A2D](https://user-images.githubusercontent.com/65329769/82089385-7bd3f680-972e-11ea-90ef-ec7b7dafa2f4.png)

```
4.1 git에게 원격저장소(github)의 위치를 설정해야 합니다. 
 깃허브 저장소를 처음 만들었으면 노란색 부분을 사용하시면 됩니다.
```
![99B34A335B42E00A20](https://user-images.githubusercontent.com/65329769/82089593-da00d980-972e-11ea-9507-f3b44d9270bb.png)
<ol>
  * git remote add origin https://github.com/PARKJINHOH/kakao_chatbot_ysUniv.git
  
  <li>  - git(현재 로컬저장소)와 remote(원격저장소)를 add(연결) 합니다. </li>
  <li>    origin이라는 이름으로 http://... 라는 주소를 이라고 해석할 수 있습니다.</li>
  <li>  -- origin이라는 이름은 바꿀 수 있습니다.</li>
</ol>

```
4.2 git push -u origin master

Username : ID가 아닌, 유저 네임 입니다.

Password : 이건 ID/PW의 PW 입니다.

- origin(github)에 임시저장소에 있는것을 push 넣습니다. 
```

```
5. 끝 github에서 확인해 보세요.
```
![994DC5405B42E03419](https://user-images.githubusercontent.com/65329769/82089918-7dea8500-972f-11ea-8e0d-04164f43b7fe.png)

```
6. 이후에 수정이 되어서 깃허브에 업로드 할 경우.

git commit -am '#$%^'

git push
```


# * 정리

```
* 로컬저장소 -> 깃허브 백업하기

1. git init

2. git add -A

3. git remote add origin https://github.com/USERNAME/Repository

4. git push -u origin master

5. 깃허브에서 확인



* 수정후 다시 백업

git commit -am '설명'

git push



* 깃허브 -> 로컬저장소 (깃허브가 업데이트 되었을 시, 덮어쓰기?)

1. git init

2. git remote add origin https://github.com/USERNAME/Repository.git

3. git fetch --all

4. git pull origin master



* 깃허브 -> 로컬저장소 (새로운 로컬일시)

1. git clone https://github.com/USERNAME/Repository.git

2. 로컬저장소 확인
```


출처 : <https://adg0609.tistory.com/13>