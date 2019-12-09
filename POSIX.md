### 현재 디렉토리의 상태보기와 명령어의 형식

`-`pwd // 디렉토리 위치 확인

`-`ls // 어떤 파일, 디렉토리가 있는지 궁금하면??

`-`ls --help // 사용하는 간략한 사용법이 내장(없을수도 있음)

`-`man ls // ls 명령어의 사용 설명어 

`-`q // 바깥쪽으로 빠져나갈 수 있다.

`-`ls -l // list in long format

`-`cd // change directory

`-`cd ~ // home directory

`-`touch // make empty file

`-`.filename // hidden file

`-`ls -a // show all files(숨긴 파일까지 다 보여줌)

`-`ls -al or ls -la or ls -l -a(자세히 보고 숨긴 파일까지 다 보기)\

`-`mkdir // make directory

`-`mv // move(rename)

`-`rm -r // remove directory

`-` nano // text editor

### 디렉토리의 생로병사

'C'

`-`mkdir posix // posix 디렉토리 만들기

'R'

`-`cd ./posix // posix 디렉토리 읽기

'U'

`-mv dummy2 dummy // dummy2라는 파일을 dummy로 바꾸는 것`

`D'

`-`rm -r dummy // dummy라는 파일을 삭제

###  절대경로 VS 상대경로

`-` cd .. / = 부모 디렉터리로 가는 거(상대경로)

`-` cd / = 한 번에 루트로 가고 싶을 때(절대경로)



### 파일생성과 읽기

|        | File            | Directory |
| ------ | --------------- | --------- |
| Create | editor          | mkdir     |
| Read   | editor, cat, ls | ls        |
| Update | editor, mv      | mv        |
| Delete | rm              | rm        |

