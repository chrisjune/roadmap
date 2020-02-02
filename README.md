# WEBDEVELOPER ROADMAP
* from `https://github.com/kamranahmedse/developer-roadmap`
## Introduction
### Git
* Area
    * `add`
        * working dir -> staging area
    * `commit`
        * staging area -> local repository
    * `push`
        * local repository -> remote repository
    * `pull`
        * remote repository -> local repository
* Command
    * `git add`
        * 깃 저장소를 초기화, 저장소나 디렉토리 안에서 명령어를 실행하기 전까지는 일반폴더
        * 초기화 후 부터는 git 저장소가됨
    * `git status`
        * 저장소 상태를 체크, 변경파일 확인, 브랜치 정보등 정보를 제공
    * `git add`
        * 저장소에 새 파일을 staging area에 올려서 깃 저장소 추적할 수 있도록 추가한다
    * `git commit -m "message"`
        * 저장소에 스냅샷을 찍어서 언제든 해당 스냅샷에 어떤 내용이 저장되어있는지 확인할 수 있다
    * `git push`
        * local repository의 변경사항을 remote repository에 반영시킨다
    * `git pull`
        * remote repository의 변경사항을 local repository에 반영시킨다
    * `git checkout`
        * 브랜치를 변경하는 명령어
        * 현재브랜치 -> develop `git checkout develop`
    * `git checkout -b <branch name>`
        * 현재 checkout된 브랜치를 기준으로 신규 브랜치를 생성후 신규브랜치로 checkout
        * master 브랜치에서 branch1 생성
        ```sh
        > git checkout master
        > git checkout -b branch1
        ``` 
    * `git branch -D <branch name>` 
        * 브랜치를 삭제하려고 할 때
    * `git remote -v`
        * 관리되는 repository 리스트를 출력
    * `git remote add <name> <url>`
        * 관리할 repository를 추가
    * `git remote remove <name>`
        * repository를 제거
    * `git merge <branch>`
        * 현재 브랜치에 <branch> 를 머지할 때 사용
        * 작업 브랜치를 release 브랜치에 머지할 때
        ```sh
        > git checkout working-branch # 작업브랜치로 체크아웃
        > git merge master # 작업브랜치에 master 신규 내용머지
        > git checkout release/20200101 # 릴리즈 브랜치로 체크아웃
        >d git merge working-branch # 릴리즈 브랜치에 작업 브랜치 머지
        ```
