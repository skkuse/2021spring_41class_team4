# PracticeCoding
## 프로젝트 목표
>깃허브 사용법의 이해 및 코딩 연습

## 깃허브와 연결방법
> + 깃허브에 공간 만들기
> + 작업공간에 깃허브 설치
>   + vscode
>   ```
>   sudo apt-get install git
>   ```
>   + wsl
>   ```
>   # add-apt-repository ppa:git-core/ppa 
>   # apt update
>   # apt install git
>   ```
> + 깃 복사하기
> ```
> # git clone <깃허브 레포 주소>
> # git clone https://github.com/Forenser0/network.git
> ```
> + 폴더 만들어서 작업 폴더로 설정하기
> + 초기화 및 초기 세팅하기
> ```
> # git init
> # git config --global user.name "CheShireCat0430" 
> # git config --global user.email vickey043011@gmail.com
> ```

## 깃허브 사용하기
> + commit 방법
> ```
> # git add .
> # git commit -m "커밋 내용"
> # git push
> ```
> + pull 방법
> ```
> # git pull
> ```

## 에러 상황
> 1. add 에러
> ```
> $ git add .
> error: '~' does not have a commit checked out
> fatal: adding files failed
> ```
> 작업 폴더 내부에 깃 레포명과 같은 이름의 파일이 생기고 그 안에 .git 파일이 존재해서 생긴 에러
> .git 파일을 삭제하거나 상위 폴더에서 git clone을 사용한다.
> 
> ```
> $ add .
> warning: CRLF will be replaced by LF in ~
> The file will have its original line endings in your working directory.
> ```
> 이 경우에는 아래의 명령어를 입력해주자
> ```
> $ git config --global core.autocrlf true
> ```
-----
> 2. commit 에러
> ```
> $ git commit -m "~"
> warning: adding embedded git repository: ~
> ```
> 바뀐 정보가 없어서 커밋할 수 없다.
-----
> 3. push 에러
> ```
> $ git add .
> $ git commit -m "~"
> $ git push
> fatal: No configured push destination
> ```
> 연결 오류인듯... 삭제하고 다시 git clone ㄱㄱ

## 특정 파일 무시하기
> 1. .gitignore 파일을 작성한다.
> gi 확장 프로그램 설치 후 f1을 눌러 명령 팔레트에 gi를 입력한다.
> 그 후 운영체제, IDE 및 프로그래밍 언어를 선택합니다. 
> 만들어진 파일을 편집합니다.
> * # 은 주석의 역할
> ```
> # 모든 확장자 .txt 파일을 무시
> *.txt
> 
> # 무시하는 모든 확장자 .a 파일들 중에서 text.txt 파일은 무시하지 않음
> !text.txt
> 
> # 현재 폴더 중에서 main 폴더에 있는 모든 파일을 무시
> /main
> 
> # 프로젝트 전체 폴더 중 TODO라는 폴더명을 사용하는 TODO 폴더의 하위 파일은 모두 무시
> main/
> 
> # 현재 폴더 중에서 main 폴더 바로 밑에 있는 .txt 확장자 파일만 모두 무시
> # 단, main/medium/text.txt 와 같은 형식에서는 .txt 확장자 파일이 무시되지 않음
> main/*.txt
> 
> # 현재 폴더 중에서 main 폴더 하위에 있는 .txt 확장자 파일은
> # main 폴더 하위 어떤 폴더에 들어 있더라도 모두 무시
> main/**/*.txt
> ```
-----
> 2. Tracked 파일 삭제
> * 로컬 디렉토리와 git 저장소 모두 삭제
> ```
> $ git rm sample.txt
> $ git rm -r sampleDirectory
> ```
> * git 에서만 삭제
> ```
> $ git rm --cached sample.txt
> $ git rm --cached -r sampleDirectory
> ```
> * 하지만 위의 방법으로 막혀서 git history 확장 프로그램을 설치해 모든 history를 지워버렸다.
-----
> 3. 다시 push
> ```
> $ git add .
> $ git commit -m "~"
> $ git push -u origin +master
> ```
> 이미 git에 불필요한 내용이 올라가 있기 때문에 강제로 push했다.
