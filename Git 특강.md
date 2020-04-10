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

\-  `rm -rf` : recursive force 기능 중지

1. git master 폴더에서 git 기능 중지

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

6. **git log**

- commit의 history(버전들의 내역)
- git log --oneline 
- git log --oneline -[개수]

7. git remote add[저장소의 이름]\[주소]



\- fetch + merge = pull

\- push, fetch 동일한 repository







​    





 



