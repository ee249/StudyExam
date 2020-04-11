## Git 특강

#### \- OPEN API 반 데이터



http://abit.ly/r7if5x

#### GIT

Source Code Management(SCM) : 코드 관리 도구

\- Version Control System

where(어떤 단위) -> 폴더(디렉토리)(저장소:repository)

- 최상단에 git 폴더를 만들었으며 그 밑에 git을 만들면 안된다.
- 

#### 용도

- 코드 관리 도구
- 협업 도구
- 배포 도구



#### 코드 관리

\- Git bash : 윈도우에서 rinux처럼 이용하는 거





#### CLI

Command Line interface(명령어 인터페이스) 



#### 명령어들 (tap을 누르면 자동완성)

\- `ls` : 현재 디렉토리 내부의 파일 & 디렉토리를 보여줌(**list**)

\- `ls -a`: 숨김 디렉토리 또는 파일까지 보여준다.(**a**ll)

\- `ls -al`: 리스트 형식으로 보여주는 거

\- `pwd` : 현재 위치를 출력함**(p**rint **w**orking **d**irectory) - 절대(최상단 디렉토리로부터)경로

\- `mkdir [디렉토리명]`: 디렉토리(폴더)를 생성(**m**ake **d**irectory)

\- `cd [경로]`: 디렉토리를 변경/이동(**c**hange **d**irectory) 

\- `cd ..`: 상위 디렉토리로 이동(..)

\- `cd .`: 현재 디렉토리로 이동(.)

~~\- `cd /` : 루트(최상단) 디렉토리로 이동(잘쓰지 않는다.(리눅스 홈으로 온다.)) ()~~ // ~~를 하면 취소선이 생긴다.

\- `cd ~` : 홈디렉토리로 이동(~)

\- `git init` : git 마스터 설정

\- `rm`[파일명] : 파일을 삭제함(remove)

\-  `rm -rf [폴더명]` : recursive force 기능 중지(폴더를 삭제함)

1. git master 폴더에서 git 기능 중지

\-`touch [파일명]` : 파일을 생성함

\-`exit` : 나가진다.

\- `code` : code로 들어가진다.  

\- `git status` : git 상태를 보여준다.

#### 코드 관리 CLI

1. **git init** : git 저장소의 시작
2. **git status** : git 상태 보기 
3. **git add [파일명/폴더명]**

- staging area에 파일을 추가(add)

4. **git rm --cached [파일명/폴더명] (-r [폴더명])**

- **staging area에서 파일을 제거(remove)**

5. **git commit -m "커밋메시지"**

- 스냅샷을 찍기(현재 상태를 저장하기)



 git remote add origin https://github.com/ee249/collabo.git // 이것도 중요 원격 등록

6. **git log**

- commit의 history(버전들의 내역)
- git log --oneline 
- git log --oneline -[개수]

7. git remote add[저장소의 이름]\[주소]



##### git 주소 바꾸기

$ git config --global user.email "메일주소" ; github저장된 메일주소
$ git config --global user.name "이름"



\- fetch + merge = pull

\- push, fetch 동일한 repository

\- git remote add origin 주소

#### Push & Pull

- 같은 저장소를 공유하고(저장소 공유가 필수)

- Push와 Pull 만을 통해서 협업 방식

- (A)synchronous : 한 가지 task가 끝나야지 다음 task 가 진행될 수 있는

  \- 끝말잇기

  \- 한가지 작업이 끝나야 다음 작업을 할 수 있는 경우

- Fork & PR(Pull Request)

  \- 저장소의 작성 권한이 없을 경우(공유가 되지 않은 경우)

  \- Open

  \- 인턴

  \- N행시 백일장

#### Branching & PR with Shared Repository

- git brach [브랜치의 이름]
- git branch : 현재 생성된 모든 branch를 보여줌

- git checkout [브랜치이름] : 브랜치를 이동

- git branch -D [파일명] : 브랜치 Delete

- git merge [합치고자 하는 branch]: 합치기
- checkout_b[브랜치명]: 브랜치 생성 & 이동



대장

​    README.md : 팀소개 markdown

노예

​	index.html : 팀 페이지



#### Branch를 통한 협업 원칙

1. `master 브랜치는 건드리지 않는다.`
2. 각자는 각자의 브랜치에서 먼저 작업을 한다.
   - 본인의 이름을 딴 브랜치를 생성 후 작업을 하고
   - 해당 브랜치를 push 한다.
   - Pull Request를 보낸다.
3. 대장은 각자의 브랜치를 점검하고, merge를 진행한다.
4. **merge 후에는 pull을(`master`를 기준으로) 통해 동기화 한다.**
5. 기존 브랜치는 삭제한다.(로컬컴퓨터)
6. (대장/노예) Github에서 브랜치도 삭제한다.
7. 1-5까지 반복



#### Conflict를 두려워하지 말기

- merge 상황에서 발생함



### 1. Fast Forward Merge

- 한쪽 branch에만 커밋이 있는 경우

### 2. Auto Merge

- 동일 파일의 특정 번경 사항이 중복되지 않을 경우(특정 파일의 내용을 두 사람이 함께 변경하지 않은 경우)
- 서로의 범위를 침범하지 않아야 한다.

### 3. Merge Conflict

- 



 



