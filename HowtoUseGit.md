#### 2021-03-12

### 1.vscode 설치

### 2.깃터미널 설치

참고
-https://coding-factory.tistory.com/245

### 3.Git Bash 파일을 열고 다음을 입력
git config --global user.name "grandsisters"
- tip! 붙여 널기는 shift + insert 키를 사용

git config --global user.email "grandsisters@naver.com"

### 4.본인의 github 페이지에서 repositories 탭 클릭후 new버튼으로  새 레포지토리를 생성

### 5.C드라이브에 Git_dondon 이라는 폴더를 생성, 추후에 이 폴더에 레포지토리들을 담는다
- 이번에는 JavaScript 폴더를 만들었다

### 6.vscode에서 File -> Open Folder 선택후 방금만든 폴더를 선택

### 7.ctrl + ` 버튼입력

아래 터미널 창에서 
1. Select Default Shell을 클릭
2. Git Bash를 선택
3. +버튼 클릭
4. bash 항목이 생긴 것을 확인


### 8.새로만든 bash 터미널에서 명령어 입력
mkdir JavaScript

cd JavaScript

- git bash는 리눅스로 환경에서 제작 되었기 때문에 리눅스 명령어가 쓰인다
- 상위 폴더로 다시 이동할때는 cd ../ 명령어 입력

git init
- 레포를 처음 생성함과 동시에 로컬의 폴더가 깃과 연결될 수 있게 해주는 명령어
- 로컬이 원격 저장소에 연결이 되었다

git remote add origin https://github.com/grandsisters/JavaScript
- 로컬을 원격 저장소에 연결
- origin은 원격연결한 것의 이름, 보통 origin이라고들 많이 쓰고 다른것으로 바꿔도 된다

git remote -v
- 연결되었는지 확인

### 9.JavaScript 폴더에 readme.md파일을 생성
생성하고자 하는 폴더를 클릭하고 New File 버튼을 클릭

- 파일 이름 옆에 꽉찬 동그라미는 저장이 안되었다는 의미
- u표시는 untracked, 깃헙이 추적할수 없는 파일로 한번도 깃헙에 반영되지 않은것들
- u표시가 있는 파일을 깃헙에 반영후 수정을 하게되면 m(modified)으로 바뀌게 되는데 수정된 파일이라는 의미이다

### 10.git status로 깃헙의 상태확인
깃헙에 스테이징 영역이 있는데 깃헙에 올라가기를 대기하고 있는 영역으로써 git status 명령어 입력시 빨간색으로 나오는 파일들은 스테이징 영역에 올라가지 못한 파일들이다

### 11.git add README.md 명령어로 스테이징 영역에 넣어주자
- 만약 하나의 파일만 생성,수정 되었다면 git add 명령어 후에 별도의 파일이름 입력없이 tab 버튼만 눌러줘도 파일명이 자동 완성 된다

### 12.git status 재입력, 파일명이 초록색으로 뜬다면 성공

### 13.커밋의 차례
- 커밋을 할때는 변동사항이 적힌 메세지를 함께 적어줘야하는데 보통 혼자서 작업할때는 그렇게 중요하지 않다 
- 그럼에도 메세지는 보내줘야하는데 커밋 컨벤션(파이썬 PEP같은 전통적으로 개발자들이 사용하는 작성방식)에 의해서 보통은 "initial commit"이라고 입력한다

### 14.git commit -m "initial commit"
- 여기서 -m은 메세지를 날리는 것을 의미한다
- 스테이징 영역의 '모든' 파일들이 함께보낸 "initial commit" 메세지와 함께 커밋된다
- 어떤 메세지를 보내도 상관없지만 "initial commit" 이라는 메세지는 보통 처음 보낼때쓴다 추후에는 어떤 메세지를 보내도 상관없다

### 15.origin이라는 원격연결의 이름으로 변동된 사항들을 마스터 브랜치에 푸쉬
- git push origin master
- 처음 입력시 로그인 창이 뜨는데 브라우저에서 로그인-연동 하면된다

### 16.제대로 푸쉬 되었는지 브라우저를 이용해 깃헙에 접속해보자