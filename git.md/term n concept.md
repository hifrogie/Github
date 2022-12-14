# 목차
### 1.[Git](https://github.com/hifrogie/Github/blob/main/term%20n%20concept.md#git)
1. Git
2. Git을 사용하는 이유
3. Git의 동작 원리
### 2. [term & concept](https://github.com/hifrogie/Github/blob/main/term%20n%20concept.md#term--concept)
1. Repository
2. version control
3. commit
4. branch
5. push
6. pull
7. local
8. remote
9. head
### 3. [command](https://github.com/hifrogie/Github/blob/main/term%20n%20concept.md#command)
1. git init
2. git help
3. git status
4. git add
5. git commit
6. git branch
7. git checkout
8. git merge
9. git push
10. git pull


## 1. Git
1. **Git** 
    - 프로젝트의 어떤 부분도 겹쳐쓰지 않도록 프로젝트의 변경을 관리하는 버전 관리 소프트웨어이다.

2. **Git을 사용하는 이유**
    - 협업을 할 때 같은 페이지에 각자 수정사항을 업로드할 수 있고 이를 병합할 수있다.
    - 이전에 만들어진 모든 변경 사항의 스냅샷을 저장한다.
    이는 이전 시점의 버전으로 되돌릴 수 있다.
    - 다른 깃허브 사용자의 프로젝트를 둘러보고 배우기 위해 자신만의 복사본으로 가져올 수 있다.

3. **Git의 동작 원리**
    1. git 프로젝터에 담겨있는 데이터들은 파일 시스템 상에서 일종의 '스냅샷'이라고 볼 수 있음.
        - 스냅샷: 사진 찍듯이 특정 시점에 스토리지(저장소)의 파일 시스템을 포착해 보관하는 기술
    2. 프로젝트를 commit하여 적용할 때의 순간을 중요시한다는 특징이 있음.
    3. 파일 자체를 저장하기 보다는 수정 내역 자체를 저장함. 

    4. 동작 원리 이미지
    ![동작 이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fczxu6b%2FbtqxJw0zusR%2F9EkX1Un1VRduwA4DN8FCGK%2Fimg.png)
        1. **Working directory** : 작업할 파일이 있는 디렉토리
        2. **Staging Area** : 커밋을 수행할 파일들이 올라가는 영역
            - 커밋 : 데이터 베이스에서 영구적인 변경을 확정하는 일
        3. **git directory** : git 프로젝트의 메타 데이터와 데이터 정보가 저장되는 디렉토리, .git을 말함
            - **메타 데이터**: 시간이 지남에 따라 많은 양의 데이터를 수집, 저장 및 분석할 수 있도록 일관된 방식으로 구조화된, 다른 데이터를 설명하는 데이터입니다.
        4. **git add** : 작업한 내용을 Staging Area에 올릴 때 사용
        5. **git push** : 실제로 git에 반영하기 위함
        6. **git fetch** : 타인이 작업한 내용을 내 컴퓨터로 다운 받기 위해서 사용
        7. **git pull** : git fetch와 git merge를 동시에 수행하는 명령어

## 2. term & concept
1. **Repository(저장소)**
    - 프로젝트가 거주할 수 있는 디렉토리나 저장 공간.
    - repo라고도 줄여 사용한다.
2. **version control(버전 관리)**
    - 프로젝트의 히스토리의 모든 시점의 스냅샷을 유지하여 버전을 관리한다.
3. **commit(커밋)**
    - 해당 시점의 스냅샷을 찍어 프로젝트를 재평가하거나 복원할 수 있는 체크포인트를 가질 수 있다.
    - git에 파일을 추가하거나 변경 내용을 저장하는 작업
4. **branch(브랜치)**
    - 작업자들은 메인 프로젝트의 브랜치를 따서 자신만의 버전을 만드는 것을 말한다. 작업이 끝난 후 프로젝트의 메인 디렉토리인 master에 브랜치를 다시 merge한다.
5. **push**
    - github에 파일을 추가하거나 변경내용을 저장하는 작업
6. **pull**
    - github에서 파일을 다운로드하는 작업
7. **local**
    - 인터넷 없이 접속되는 저장소
    - 보통 내 컴퓨터에 저장되는 것
8. **remote**
    - 인터넷을 통해 접속해야 하는 것
    - github라 생각해도 무방
9. **head**
    - 현재 작업 중인 branch
## 3. command
1. **git init**
    - 깃 저장소를 초기화한다.
    - 이 명령을 실행하기 전까지는 일반 폴더이다.
    - 이 것을 입력한 후에야 추가적인 깃 명령어를 줄 수 있다.
2. **git help**
    - 깃 명령어를 잊어버렸다면 이것을 이용해 유용한 명령어를 볼 수 있다.
3. **git status**
    - 저장소의 상태를 체크하는 명령어이다. 
    - 프로젝트의 수정된 파일이나 어떤 브랜치에서 작업하는지 등을 체크할 수 있다.
4. **git add**
    - working directory 상의 변경 내용을 staging area에 추가하기 위해 사용되는 Git 명령어
    - 사용자가 커밋을 하기 전까지 변경된 내용들을 모아놓기 위해 사용함
5. **git commit**
    - 변경사항을 만든 후 스냅샷을 찍기 위해 이를 입력한다.
    - -m을 이용하여 메세지를 남겨 놓는다.
6. **git branch**
    - 자신만의 변경을 원한다면 새로운 브랜치를 만들고 자신만의 변경사항과 파일 추가등의 커밋 타임라인을 만든다.
7. **git checkout**
    - 현재 위치하고 있지 않은 저장소를 체크아웃할 수 있다.
    - 체크하길 원하는 저장소로 옮겨가게 해주는 탐색 명령이다.
    - master 브랜치를 들여다 보고 싶으면 git checkout master를 사용할 수 있다.
8. **git merge**
    - 브랜치에서 작업을 끝내고 master브랜치로 병합할 수 있다.
9. **git push**
    - 로컬 컴퓨터에서 작업하고 당신의 커밋을 깃허브에서 온라인으로도 볼 수있기 원할 때 이 명령어를 이용해 변경사항을 push한다.
10. **git pull** 
    - 로컬컴퓨터에서 작업할 때, 작업하고 있는 저장소의 최신버전을 원한다면 이 명령어를 이용해 깃허브로 부터 변경사항을 다운로드한다.