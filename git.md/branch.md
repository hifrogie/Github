## 4. Branch 사용법
### 1. 기본적인 branch 명령어 총정리
1. branch 생성 및 생성된 branch로 전환
    - git checkout -b < branch 이름>
2. 현재 자신의 파일과 연결된 branch 목록
    - git branch
3. branch 전환
    - git checkout < branch 이름>
4. branch 생성
    - git branch < branch 이름>
5. branch 삭제
    - git branch -d < branch 이름>
6. branch 강제 삭제
    - git branch -D < branch 이름>
7. branch에 코드 push
    - git push origin < branch 이름>
8. merge하는 법
    - git checkout < branch 이름>
    - git merge < branch 이름>
9. branch 끼리 비교
    - git diff < branch 이름> < branch 이름>

### 2. rebase
![rebase](https://git-scm.com/book/en/v2/images/basic-rebase-2.png)
![rebase2](https://git-scm.com/book/en/v2/images/basic-rebase-3.png)
1. c3에서 변경된 사항을 Patch로 만들고 이를 다시 c4에 적용시키는 방법을 rebase 라고 한다.
    - patch : 다른 내용(수정한 내용)을 빼내서 다른 환경에 적용할 수 있도록 파일을 만든다고 생각하면 된다. 
2. 아래와 같은 명령으로 rebase 한다.
    - $ git checkout experiment
    - $ git rebase master
3. 실제로 일어나는 일을 설명하자면 일단 두 브랜치가 가리키는 커밋 까지 diff를 차례로 만들어 어딘가에 임시로 저장해 놓는다.
4. Rebase할 브랜치(experiment)가 합칠 브랜치(master)가 가리키는 커밋을 가리키게 하고 하까 저장해 놓았던 변경사항을 차례대로 적용한다.
![image](https://git-scm.com/book/en/v2/images/basic-rebase-3.png)
5. 그리고 나서 master 브랜치를 fast-forward 시킨다.
    - $ git checkout master
    - $ git merge experiment

### 3. Fork와 Pull Request
1. 코드 기여 원리
    1. A가 B 개발자의 프로젝트가 맘에 들어 같이 프로젝터에 참여해 기여자로써 공헌을 하고 싶다고 한다. 하지만 내가 다른 사람의 저장소에 있는 코드를 수정하려면 관리자가 직접 나를 기여자(contribute)로 등록해주어야한다. 하지만 모든 사람을 다 기여자로 등록할 수는 없는 현실이다.
    2. 이때 사용하는 것이 Fork이다.
    3. 포크로 쿡 찔러 가져오듯 다른 사람의 저장소에 있는 레포지토리를 내 원격 저장소, 깃허브로 가져오는 것이다.
    4. 즉, A라는 유저가 B의 레포지토리 중 하나를 fork하였다면 A의 github에 해당 레포지토리가 그래도 가져와 지게 된다. 그리고 나서 fork해온 원격 레포지토리를 내 로컬에 clone한 후 코드를 수정하면 된다.
    5. Fork : 레포지토리를 원격 저장소에 복사
    6. Clone : 레포지토리를 로컬저장소에 복사
    7. A 개발자가 코드를 업그레이드 한 후 B의 레포지토리에도 반영되었으면 좋겠다 생각이 들면 Pull Request를 보내는 것이다.
    8. B가 코드 리뷰를 하고 문제가 없으면 자신의 메인 브랜치에 merge하는 식으로 프로젝트에 기여하는 방식이다.
2. Pull Request(PR)란?
    1. 내가 수정한 코드가 있으니 내 branch를 가져가 검토 후 병합 해주라고 요청 해주는 것
    2. PR을 통해 코드 충돌을 최소화할 수 있고 push 권한 이 없는 오픈 소스 프로젝터에 기여할 때 많이 사용한다.