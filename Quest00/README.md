# Quest 00. 형상관리 시스템

## Introduction

-   git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics

-   git
    -   `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
    -   `.git` 폴더
-   GitHub

## Resources

-   [Resources to learn Git](https://try.github.io)
-   [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
-   [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist

-   형상관리 시스템은 왜 나오게 되었을까요?
-   git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?
    -   git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
-   git과 GitHub은 어떻게 다를까요?
-   git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
-   git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
-   리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?

## Quest

-   GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
-   Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
    -   앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
-   이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
-   `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced

-   Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
-   실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?

---

## GIT 명령어

-   **git init** : Repo 초기화, 현재 폴더를 git 저장소로 설정하고 .git 폴더를 생성하여 이력과 설정을 저장합니다.
-   **git status** : 현재 변경 사항과 스테이징 영역의 상태를 보여줍니다. 어떤 파일이 수정되었고 어떤 파일이 스테이징 되었는지 확인할 수 있습니다.
-   **git retmoe** : 원격 저장소를 추가합니다.
    git remote add <원격 이름> <원격 URL> ex) git remote add origin git@github.com:<User-name>/<reponame>.git
-   **git config** : 전역또는 폴더별 사용자 정보, 커밋 메시지 편집기, 병합 동작등을 설정하는데 사용됩니다.
    -   —global user.name or user.email <User name or email> : 사용자를 정의하면 히스토리에 입력한 사용자 이름과 이메일이 표기됩니다.
    -   —global alias.<co> checkout : 단축 명령어를 설정합니다.
-   **git clone** : 원격 저장소를 복제하여 로컬로 가져옵니다.
-   **git add** : 변경된 파일을 스테이징 영역에 추가합니다. \*스테이징 영역은 커밋을 준비하는 단계로 어떤 변경사항을 포함할지 결정하는 단계
-   **git commit** : 스테이징 영역에 있는 변경 사항을 로컬 저장소에 커밋합니다. 변경 사항을 스냅샷으로 저장하고 이록을 기록하는 역할

    -   **convention**

        > 커밋 메시지의 형식과 내용을 표준화하여 프로젝트의 히스토리를 이해하고 변경 사항을 추적하여 효과적으로 협업하기 쉽게 만드는 것입니다.

        ### 템플릿 규칙

        커밋시 Git commit.template 옵션에 설정한 템플릿 파일을 보여준다.

        ```jsx
        // .git_commit_template.txt
        ################
        # <타입> : <제목> 의 형식으로 제목을 아래 공백줄에 작성
        # 제목은 50자 이내 / 변경사항이 "무엇"인지 명확히 작성 / 끝에 마침표 금지
        # 예) feat: 로그인 기능 구현, 이슈트래킹시 => [이슈번호] feat: 로그인 기능 구현

        # 바로 아래 공백은 지우지 마세요 (제목과 본문의 분리를 위함)

        ################
        # 본문(구체적인 내용)을 아랫줄에 작성
        # 여러 줄의 메시지를 작성할 땐 "-"로 구분 (한 줄은 72자 이내)

        ################
        # 꼬릿말(footer)을 아랫줄에 작성 (현재 커밋과 관련된 이슈 번호 추가 등)
        # 예) Close #7

        ################
        # feat : 새로운 기능 추가
        # fix : 버그 수정
        # docs : 문서 수정
        # style : 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우
        # refactor : 코드 리펙토링
        # test : 테스트 코드, 리펙토링 테스트 코드 추가
        # chore : 빌드 업무 수정, 패키지 매니저 수정
        ################
        ```

        템플릿 설정 : git config —global commit.template .git_commit_template.txt

-   **git push** : 로컬 저장소의 변경 사항을 원격 저장소로 업로드합니다.
-   **git pull** : 원격 저장소의 변경 사항을 로컬로 가져와 병합합니다.
    -   git merge : 다른 브랜치의 변경 사항을 현재 브랜치로 가져와 병합합니다. 로컬에서 수행되며 원격 저장소와 직접 상호작용하지 않습니다.
-   **git branch** : 브랜치를 생성, 확인 및 관리합니다.
    ex) git branch develop - checkout : 선택한 브랜치로 이동
    ex) git checkout (main or commit hash) - checkout -b : 브랜치 생성 및 이동
    ex) git checkout -b feature/header
-   **git stash** : 변경하지 않은 작업을 일시적으로 보관하고 나중에 다시 적용합니다.
    -   git stash list : 현재 보관중인 작업 확인
    -   git stash apply <stash name>: 보관중인 작업을 적용, stash name이 없을시 최신 작업을 가져옵니다.
    -   git stash drop <stash name>: 보관중인 작업을 삭제, stash name이 없을시 최신 작업을 삭제합니다.
-   **git rm** : 원격 파일을 삭제합니다.

## GIT 시나리오

1. **Create new repository 시나리오**
    1. git config —global [user.name](http://user.name) [user.email](http://user.email) 설정
    2. Create [README.md](http://README.md), .gitignore
    3. git init
    4. git add [README.md](http://README.md) && .gitignore
    5. git commit -m “<message>”
    6. git branch -M main
    7. git remote add origin <Remote URL>
    8. git push -u origin main
2. **feature/header 작업 develop 브랜치로 이동**
    1. git add .
    2. git commit -m “헤더 구현”
    3. git push origin featrue/header
    4. git checkout develop
    5. git pull origin feature
    6. git push origin develop
