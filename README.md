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
    * `git grep <검색단어>`
        * Find in path, 특정 단어가 포함된 파일과 주변 내용을 출력해준다
    * `git log -n 10`
        * 로컬 저장소의 커밋 히스토리를 탐색
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
### Licenses
* Apache
    * 아파치 라이센스는 아파치소프트웨어재단(ASF)이 자신의 SW에 자체 적용을 위하여 만든 라이센스이다.
    * 소스코드 공개의무는 없다.
    * 다만, 아파치 라이센스 소스코드를 수정배포하는 경우 아파치라이센스 버전 2.0을 포함하고 아파치재단에서 만든 SW임을 명시해야한다.
    * ex) 안드로이드, 하둡
* GNU GPL(General Public License)
    * 자유소프트웨어재단(FSF)에서 만든 라이센스다. GNU에서 배포하는 SW(emacs, GDB, GCC)등에 적용하기 위하여 리처드 스톨만이 만든 라이센스이다.
    * 가장 강력한 제약조건을 포함하는 카피레프트 조항을 담고있다.
    * GPL 프로그램은 어떤 목적과 형태로든 사용과 변경이 가능하지만 배포하는 경우 무조건 동일한 라이센스인 GPL로 공개해야한다
    * ex) Firefox, Linux kernel, Git, MariaDB, Wordpress
* GNU Affero GPL(AGPL)
    * GPL을 기반으로 만든 라이센스
    * 1,2버전은 아페로, 3버전은 FSF에서 개발됐다
    * 수정한 소스코드를 바탕으로 서비스는 하지만 배포는 하지 않는 경우 사용자는 코드를 가질 수 없는 문제를 해결하기 위한 라이센스이다.
    * 서버에서 사용자들과 통신하면 실행중인 소스코드를 다운로드 할 수 있도록 공개해야한다는 조항을 담고있다
    * ex) MongoDB
* GNU Lesser GPL(LGPL)
    * FSF 강력한 철학을 담긴 GPL의 카피레프트 조항을 보완하기 위한 라이센스이다.
    * GPL SW를 사용만 하여도 공개해야하기 때문에 상용으로 사용하기엔 부담이 있다. 
    * 초기에는 단순한 라이브러리, 모듈을 허용한 라이센스여서 Library GPL이었지만, 이후 Lesser GPL로 변경됐다
    * ex) Firefox
* MIT
    * MIT 라이센스는 MIT SW개발자들을 돕기 위하여 개발한 라이센스이다.
    * 라이센스와 저작권 관련 명시만 지켜주면되는 가장 느슨한 조건을 가진 라이센스이기 때문에 인기가 많다
    * 부트스트랩, Angular, Backbone, jQuery
* Artistic
    * Pearl 기능을 위하여 만든 라이센스이다
    * 시적허용(틀린 표현이라도 시적인 효과를 위하여 허용한다)를 참조하여 만들어진 라이센스
    * ex) NPM(Node Package Manager)
* Eclipse
    * 이클립스에서 비지니스 환경에 적합하게 만든 기업을 위한 라이센스
    * GPL의 카피레프트보다 완화된 라이센스
    * ex) Eclipse
* BSD(Berkely Software Distribution)
    * UC Berkely에서 배포하는 SW 라이센스이다.
    * BSD 자체가 공공기관에서 만들어서 공공의 몫으로 돌리자는 의미가 강하다
    * 라이센스 자체에는 아무런 제한 없이 누구나 자신의 용도로 사용가능하다
    * 라이센스 및 저작권 표시 이외엔 제약이 없는 자유로운 라이센스이다
    * ex) Nginx
* MPL(Mozila Public License)
    * 모질라재단에서 작성한 라이센스이다
    * 수정한 코드는 MPL로 공개하고 원작자에게 알려야한다
    * 소스코드는 공개의무가 있지만, 별도의 코드와 실행파일은 독점라이센스를 가질 수 있다
    * ex) Firefox, Thunderbird
### Semantic versioning
* versioning
    * 소프트웨어 협업의 도움으로 다른사람에 의해 개발된 기능을 손쉽게 가져다 쓸 수 있는 혜택을 누리고 있습니다.
    * 하지만 여러 사람이 이용하는 패키지가 업데이트 될 때마다 의도하지 않는 동작을 일으키거나 사용법을 바꾸어버리게 됩니다
    * 따라서 기존의 코드와 변경 내용을 구분해야할 필요성에 의하여 버전이라는 개념이 탄생하게 되었습니다.
* Semantic Versioning
    * 버전을 통해 변경사항을 관리할 수 있지만 버전에 대한 기준이 패키지마다 다르다는 문제점은 남아있었습니다.
    * Gihub의 창업자인 [Tom Preston-Werner](https://en.wikipedia.org/wiki/Tom_Preston-Werner)가 Sementic versioning이라는 제안을 합니다.
    * 이 제안은 [RFC2119](https://tools.ietf.org/html/rfc2119)의 규칙으로 표기하고 있습니다.
* 규칙
    1. Semantic versioning을 쓰는 SW는 반드시 공개 API를 정의 해야한다. 이 API는 코드 자체에 정의되어 있거나 명시적으로 문서화 되어있어야 한다. 이 과정은 포괄적이며 정확해야한다.
    2. 일반 버전 명은 반드시 X.Y.Z 형태를 보여야 하며 X,Y,Z는 음이 아닌 정수이다. X는 주요한 버진이며, Y는 작은 버전, Z는 패치버전이다. 각 요소는 1씩 차례로 증가해야 한다. 예: 1.9.0 -> 1.10.0 -> 1.11.0
    3. 주요 버전 숫자가 올라갈 때, 작은 버전 숫자와 패치 버전 숫자는 0으로 재설정되어야 한다. 작은 버전 숫자가 올라갈 때, 패치버전 숫자는 0으로 재설정되어야 한다. 예: 1.1.3 -> 2.0.0, 2.1.7 -> 2.2.0
    4. 버전 명이 주어진 패키지가 한번 공개되면, 해당 버전의 내용은 절대 수정되어선 안된다. 어떤 수정도 반드시 새로운 버전으로 공개되어야 한다.
    5. 주요버전 0(0.y.z)은 초기 개발을 위한 것이다. 언제든 변경될 수 있다. 공개 API는 안전하지 않다고 여긴다.
    6. 버전 1.0.0은 공개 API를 정의한다. 이 공개 이후의 버전 숫자가 바뀌는 방법은 공개API와 변경 방법에 따라 결정된다.
    7. 패치버전Z은 하위호환을 하지만 버그수정이 있을 때 올라간다. 버그 수정은 내부적으로 잘못 처리되고 있는 것을 고치는 것을 의미한다.
    8. 작은버전Y는 새로운 기능이 추가되었지만 기존의 공개 API가 하위호환되고 있을 때 올라간다. 공개API가 하나 이상 deprecated될 시에도 올라가야 한다. 부가적인 새 기능이나 개선이 내부코드(Private code)에 있을 시에도 올릴 수 있다. 이는 패치 수준의 변화를 포함할 수 있으나, 작은 버전이 올라가면 패치 버전은 꼭0이 되어야 한다.
    9. 주요버전X는 하위호환되지 않는 변화가 추가될 때 반드시 올라가야 한다. 이는 패치 수준과 작은 수준의 변화를 포함할 수 있으나, 주요 버전이 올라가면 작은 버전과 패치버전은 꼭 0이 되어야 한다.
    10. 선행 배포 버전은 대시(-)와 점으로 나누어진 식별자들의 묶음을 패치버전 뒤에 표시한다. 식별자들은 ASCII 영숫자와 대시로만 구성되어야한다. [0-9A-Za-z-]. 선행 배포 버전은 연관된 일반 버전보다 낮은 우선순위를 가진다. 예: 1.0.0-alpha
    11. 개발 버전은 더하기(+)와 점으로 나누어진 식별자들의 묶음을 패치 버전 뒤에 표시한다. 식별자들은 ASCII 영숫자와 대시로만 구성되어야 한다. [0-9A-Za-z+]. 빌드 버전은 연관된 일반 버전보다 높은 우선순위를 가진다. 예: 1.3.7+build
    12. 우선순위는 주요, 작은, 패치, 선행배포, 빌드 식별자 내 숫자 순으로 계산되어야한다. 주요, 작은, 패치 버전은 항상 숫자로 비교되어야 한다. 선행 배포와 빌드 버전의 우선순위는 반드시 각 점으로 나누어진 식별잗르이 아래 규칙에 따라 비교되어야 한다.
        * 숫자로만 이루어진 식별자는 숫자로 비교
        * 문자와 대시가 포함된 식별자는 ASCII정렬 순서대로 비교. 숫자 식별자는 숫자식별자가 아닌 식별자보다 낮은 우선순위를 가진다.
        * 예: 1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-beta.2 < 1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0-rc.1+build.1 < 1.0.0 < 1.0.0+0.3.7 < 1.3.7+build < 1.3.7+build.2.b8f12d7 < 1.3.7+build.11.e0f985a.
* Python Semver
    * Versioning에 대한 구분과 차이등 이해하는데 도움되는 패키지
    * https://github.com/python-semver/python-semver
### SSH
    * 컴퓨터간 네트워크를 통해 통신할 때 안전함을 보장해주는 프로토콜
## Secure Shell Protocol
    * Secure
        * 보안적으로 안전한
    * Shell
        * 명령어와 프로그램을 실행하는 `커널`과 사용자간의 인터페이스
        * 사용자의 명령어를 해석하고 전달하는 명령어 해석기능
        * 여러 명령어를 사용해 반복기능을 하는 프로그래밍 기능
        * 사용자마다 환경을 다르게 바꿔주는 사용자 환경 설정기능
    * Protocol
        * 규약이라는 뜻으로, 쉽게는 약속이라고 할 수 있다.
        * 메일을 보낼 때 받는사람, 보내는 사람, 내용이 꼭 필요한 것 처럼 정보를 주고 받을 때 필요한 약속이다
    * 예시
        * 데이터전송
            * Github
        * 원격제어
            * Cloud service, AWS
## 구현방법
* SSH는 사용자 인증을 위하여 비밀번호를 입력하지 않고 공개키와 개인키방식을 사용합니다
* 공개키
    * 공개되어도 비교적 안전한 Key입니다. 공개키를 통해서 메시지를 암호화합니다. 하지만, 공개키로 복화화는 불가능합니다.
* 개인키
    * 공개되서는 안되는 키입니다. 컴퓨터 내부에 저장되어있고 이 키를 통해 메시지복호화가 가능합니다.
* 통신방법
    * 통신을 위해서 Public키를 통신하기 위한 컴퓨터에 복사하여 저장합니다
    * 클라이언트에서 요청할 때 공개키로 암호화하고 서버에서는 요청을 개인키로 복호화하여 처리합니다.
    * 서버의 응답을 개인키로 암호화하고 클라이언트는 이를 공개키로 복호화하여 응답을 받을 수 있습니다.


