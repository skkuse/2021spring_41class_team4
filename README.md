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
> 2. commit 에러
> ```
> $ git commit -m "~"
> warning: adding embedded git repository: ~
> ```
> 바뀐 정보가 없어서 커밋할 수 없다.
> 
> 3. push 에러
> ```
> $ git add .
> $ git commit -m "~"
> $ git push
> fatal: No configured push destination
> ```
> 연결 오류인듯... 삭제하고 다시 git clone ㄱㄱ
