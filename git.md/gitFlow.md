## 3. Git Flow
### 1. Git Flow란?
1. Git Flow는 기능이 아니고 서로간의 약속인 방법론이다.
2. 완벽한 방법론이 아니고 각자 개발 환경에 따라 수정하고 변형해서 사용해야한다.

### 2. 5가지 브랜치를 사용해서 운영
1. master : 기준이 되는 브랜치로 제품을 배포하는 브랜치
2. develop : 개발 브랜치로 개발자들이 이 브랜치를 기준으로 각자 작업한 기능들을 합(Merge)칩니다.
3. feature : 단위 기능을 개발하는 브랜치로 기능 개발이 완료되면 develop 브랜치에 합칩니다.
4. release : 배포를 위해 master 브랜치로 보내기 전에 먼저 QA(품질검사)를 하기 위한 브랜치입니다.
5. hotfix : master 브랜치로 배포를 했는데 버그가 생겼을 때 긴급 수정하는 브랜치 입니다.
6. master와 develop이 중요한 매인 브랜치이고 나머지는 필요에 의해서 운영한는 브랜치이다.

### 3. Git Flow 브랜치 설명
![깃 플로우](https://t1.daumcdn.net/cfile/tistory/99CD994C5E69CCF223)

1. 일단 master 브랜치에서 시작
2. 동일한 브랜치를 develop에도 생성함. 개발자들은 이 develp 브랜치에서 개발을 진행함.
3. 개발을 하다가 회원가입, 장바구니 등의 기능 구현이 필요할 경우 A개발자는 develop 브랜치에서 feature 브랜치를 하나 생성해서 회원가입 기능을 구현하고 B개발자도 develop 브랜치에서 feature 브랜치를 하나 생성해서 장바구니 기능을 구현합니다.
4. 완료된 feature브랜치는 검토를 거쳐 다시 develop 브랜치에 합침(merge)
5. 이제 모든 기능이 완료되면 develop브랜치를 release 브랜치로 만듭니다. 그리고 QA(품질검사)를 하며너 보완점을 보완하고 버그를 픽스함
6. 모든 것이 완료되면 이제 release브랜치를 master브랜치와 delvelop 브랜치로 보냅니다. master 브랜치에서 버전 추가를 위해 태그를 하나 생성하고 배포를 합니다.
7. 배포를 했는 데 미처 발견하지 못한 버그가 있을 경우 hotfixes 브랜치를 만들어 긴급 수정 후 태그를 생성하고 바로 수정 배포를 합니다.

### 4. Fork와 Pull requests
![포크](https://t1.daumcdn.net/cfile/tistory/99E9D24E5E69CCF224)

1. react나 bootstrap같이 규모가 있는 개발을 할 경우 브랜치 보다는 Fork와 Pull requests를 활용하여 구현을 합니다.
2. Fork는 브랜치와 비슷하지만 프로젝트를 통째로 외부로 복제해서 개발을 하는 방식입니다.
3. 그렇게 개발을 해서 브랜치 처럼 merge를 바로 하는 것이 아니라 Pull requests로 원 프로젝트 관리자에서 머지 요청을 보내면 원 프로젝트 관리자가 Pull requests된 코드를 보고 적절하다 싶으면 그때 그 기능을 붙히는 식으로 개발을 합니다.
