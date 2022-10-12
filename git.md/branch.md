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
![rebase](https://velog.velcdn.com/images%2Fkwonh%2Fpost%2Fd3f91e4a-cbc0-44d4-9ae5-dedea55cca55%2Fimage.png)
1. experiment 브랜치로 이동해 master를 base 삼아 Rebase 하겠다는 의미
2. 아래와 같은 명령으로 rebase 한다.
    - $ git checkout experiment
    - $ git rebase master
    1. 내부에서는 master가 base가 되고, C3,C4의 차이를 임시 저장하는 공간에 저장합니다. 이 임시 저장 공간을 Patch라고 합니다. 그리고 base가 되는 master에 patch들이 적용됩니다.
    2. patch : 다른 내용(수정한 내용)을 빼내서 다른 환경에 적용할 수 있도록 파일을 만든다고 생각하면 된다. 
3. 다시 정리
    1. 공통 커밋(C2)에서 시작해서 현재 체크아웃한 experiment 브랜치가 가리키는 커밋까지 diff(코드변경)를 차례로 만들어 Patch에 저장
    2. experiment 브랜치가 master브랜치를 가리키게 함
    3. C3에 Patch를 순서대로 적용
![image](https://velog.velcdn.com/images%2Fkwonh%2Fpost%2F8c779a0b-ce4b-4760-97c9-9f68bca74656%2Fimage.png)
4. 커밋 히스토리가 한 줄로 깔끔하게 정렬된 것을 볼 수 있었다.
5. 그리고 나서 master 브랜치를 fast-forward 시킨다.
    - $ git checkout master
    - $ git merge experiment
![image](https://velog.velcdn.com/images%2Fkwonh%2Fpost%2F777b0f21-ae9d-400e-9265-6adc77188ed0%2Fimage.png)
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