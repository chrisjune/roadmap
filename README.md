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
        > git merge working-branch # 릴리즈 브랜치에 작업 브랜치 머지
        ```
    * `git commit --allow-empty -m "empty commit"`  
        * 수정 내용없이 커밋추가할 때
    * `git commit --amend --date "Mon 20 Aug 2020 20:19:19 KST"`
        * 마지막 커밋의 시간을 변경할 때
    * `git commit --amend -m "수정할 메시지"`
        * 마지막 커밋의 메시지를 변경할 때
    * `git reset <commit hash> --hard`
        * git의 커밋을 강제로 삭제해버릴 때. 이미 다른 로컬에 체크아웃 받은 경우,
        * git이 깨지게 되므로 반드시 이를 유념하고 사용해야한다
### Basic Terminal Usage
* Command
    * `cd <path>`
        * change directory, 현재 위치를 path로 변경
        * path를 주지 않은 경우 HOME directory로 이동한다
        ```sh
        cd /var/lib/postgres/bin/data
        ```
    * `ls <path>`
        * lists the contents, path에 속한 파일 또는 디렉터리들을 출력해준다
        * path를 주지 않는 경우 현재 디렉터리에 있는 파일과 디렉터리를 출력해준다
        ```sh
        ls /var/lib
        ```
    * `open <filename>`
        * open files, 파일을 기본 편집기로 열어준다
    * `cp <from/file> <to/file>`
        * copy file, 파일을 선택한 위치로 복사한다
        ```
        cp current.txt subdirectory/newfile.txt
        ```
    * `mv <file> <new path>`
        * move file, 파일을 선택한 위치로 이동한다
        ```sh
        cp current.txt subdirectory/newfile.txt
        ```
    * `mv <file> <new file>`
        * rename file, move와 동일한 명령어이다.
        * 다만, file의 위치가 동일할 경우 이름이 변경된다.
        ```sh
        mv ~/oldname.txt ~/newname.txt
        ```
    * `mkdir <path/path/name>`
        * make directory, 지정한 위치에 디렉터리를 생성해준다.
        * -p 옵션을 붙이면 nested하게 디렉터리를 생성해준다
        ```sh
        mkdir -p ~/not/exist/path/directory
        # 모든 디렉터리를 한번에 생성해준다
        ```
    * `rmdir <path>`
        * remove empty directory, 비어있는 디렉터리를 삭제
    * `rm -r <path>`
        * remove directory recursively, 중첩된 디렉터리를 삭제
        * 만약 디렉터리내에 파일이 있다면 `rm -rf <path>` 형태로 명령을 해야한다
        * 단, rm으로 삭제한 경우 복구가 불가능 하기 때문에 `rm -rf` 명령어는 상당히 주의해야한다
    * `sudo <command>`
        * do with super user privileges, 관리자 권한으로 실행
        ```sh
        sudo ls /var/lib
        ```
    * `top`
        * 프로세스와 메모리관리 모니터링
        * 현재 메모리 상황과 프로세스 현황, Load average등 여러 정보를 확인할 수 있다
    * `q`
        * `top`, `git diff`, `more`, `vi` 등 active한 프로세스를 종료시킬 때 사용한다
    * `clear`
        * 터미널을 처음 튼 것 처럼 지난 명령어와 출력결과물을 지워준다.
    * `help <command>`
        * 명렁어에 대한 도움말 정보를 출력해준다
    * `man <command>`
        * manual page, 명령어에 대한 자세한 설명과 예시를 출력해준다
        ```sh
        man grep
        ```
    * `whatis <command>`
        * 명령어에 대한 소개를 한줄로 요약하여 출력해준다
    * `exit`
        * 터미널 세션을 종료한다.