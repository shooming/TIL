# GIT

## GIT의 간단한 개요

git은 VCS(version contorl System)로서 소스코드의 버전관리하는 시스템이다.

보통 협업툴로서 많이 사용한다.

github은 git으로 Local 저장소에서 파일을 관리를 하게 해주던걸 인터넷에서 여러명이 원격저장소로 관리할 수 있게 해준다.

기준이 되는 저장소 필요한데 레포지토리라고함.

만약 github없다면 서버올려서 코드공유해야하고 불편하고 비용도 많이 들었을것이다.

중앙서버(github)와 local(git)로 구분된다.

------

## Git Hub의 사용법

일단 git을 사용하기위해서는 git을 사용할 수 있도록 폴더에 설정을 해줘야한다.

```bash
git init
```
그 명령어는 `git init`이다 이 명령어를 사용하면 프로젝트를 git repository로 만들기위해 사용 .git폴더가 생성됨  
  
GitHub에 있는 자료를 내 로컬 저장소로 복제하려면 clone 해야한다. 
```bash
git clone <원격저장소 위치>
```
참고로 `git clone`을 하면 자동으로 해당 저장소가 폴더채로 다운받아지며 폴더안은 이미 `init`이 된상태이다.

git에서 수정된 파일이나 폴더들에는 3가지 상태가 존재한다.

- modified - 수정일어나서 변화 감지

- staged - 중간세이브 commit 되기전에 중간상태 저장하고 문제가 생기면 되돌리기 위해서존재한다. staged상태라면 commit이 가능하다

- committed - commit이 된상태로 push가 가능한 상태가 된다.

이렇게 3가지 순서가있는데 일단 파일을 수정한다.

그리고 지금 수정을 다 마치고 현재 상태를 확인해야한다.

```bash
git status
```
그때 사용하는 명령어가 `git status`이다. 해당 명령어를 사용하면 현재 modified상태인지 staged상태인지 알려준다.

modified 상태라면 staged상태로 만들어야할 것이다.

```bash
git add <파일 / 폴더명>
git add * # 모든 파일, 폴더 선택
git add . # 현재폴더 아래 있는 모든 파일 선택
```
그때는 `git add`를 사용하면된다.

이때 원하지 않은데 add하여 staged된 파일은 `git checkout -- "파일 / 폴더명"`을 쓰면 modified상태가 된다.

그다음 staged되었으니 commit을 해야할것이다.

```bash
git commit -m "메세지 입력"
```
`git commit`을 사용하면되고 `-m` 옵션을 사용하여 바로 뒤에 메세지를 입력한다. 만약 `git commit`만 사용하게되면 해당 터미널에서 사용하는 기본 편집기가 실행된다.

이제 committed된 파일 / 폴더를 원격저장소로 보낼것이다.
```bash
git push origin <branch명>
```
`git push`명령어를 사용하면 원격저장소로 파일을 보내줄 수 있다.

만약 원격저장소에서 최신상태의 버전을 받고싶다면

```bash
git pull
```
`git pull`명령어를 사용하면된다.

아래는 간단한 git 명령어 모음이다.

```bash
git init
프로젝트를 git repository로 만들기위해 사용 .git폴더가 생성됨 

git add
옵션 -a 모든파일 선택
옵션 . 현재폴더 아래 있는 모든 파일 선택
modified 파일을 staged 상태로 옮기고자 할 때 사용함.

git commit
add 된 파일들을 메시지 작성하여 커밋함

git diff
modified 상태에서만 나옴 수정사항 보여줌

git status
git repository의 상태를 보여줌

git log
commit 내역 보여줌 commit history라고도 함

git rm
git에 등록된 파일 삭제할때 사용

git mv
파일 위치 옮기거나 이름 바꿀때 사용

git branch
branch 생성, 삭제, 관리하는 명령어

git checkout
branch 이동할때 사용하는 명령어

git checkout -- <modified파일이름>
잘못된 add 파일 풀때 -- 다음은 띄어야한다.

git clone
남의 저장서 퍼올때 사용하고 fork라고도 함
```
------

## branch & merging

소스의 가지라고 한다 새로운 작업할때 branch 만들게 되며,
기존 소스 영향 안받게하고 안전하게 버전을 관리하게 하기위해 꼭 필요하다. 여러사람이 만들면 언제 바뀔지 알수없지 때문이기 때문이다.
협업에서 branch명은 `feature(원하는 이름)`을 보통 사용한다.

branch에서 작업을 하고 마친다음 pull request(pr)를 하여 master branch에 merge시키는 형태가 된다.

merge는 branch를 합치는 것을 말하는데 내 master 버전이 update 하려는 저장소의 master버전보다 낮고 수정하려는 부분이 같은 상태라면 conflict된다.

pull request(pr)을 하게되면 충돌일어 github에서 그 사실을 알려준다. 그럴경우 `git pull`을 하여 수정이 필요하다고 표시된 부분을 수정하여 다시 `git push`하면 pull request에 자동적으로 다시 반영한다.

pull request되면 원격저장소에 branch는 자동적으로 사라지게 되고 local에는 남아있는데 branch의 재사용은 권장되지 않으므로 삭제하고 다시 만드는 것이 좋다.

git은 local에서 협업은 github에서 한다.

## .gitignore file
git repo의 파일 중 원하지 않는 포함되는 거 막기위해 .gitgnore file 생성해서 그안에 들어가지 않았으면 하는 내용 적음

-----

## ETC..

git mremote add origin 원격저장소 주소
origin이 기본이고 다르게 작성해도 됨 원격저장소의 별명임(origin)

touch (파일명).txt
touch 파일 생성 명령어

`git push origin(리모트 별명) (푸쉬할 브랜치명)`
브랜치상태로 push 가능~

pull request는 원격저장소에서함 그이유는 conflict 때문임

브랜치는 사용하고 다시 사용하지 않음 브랜치는 사용 후 버릴것 항상 새로 생성할것

git pull써서 다른사람 작업한 최신상태 땡겨 온다. `git pull origin(원격저장소 별명) master(로컬 브랜치)` 라고 치면됨

tig 치면 바로 브랜치 상태 볼수있음

`git branch -d (삭제시킬 브랜치이름)`