# connect-to-fe-git

## memo

강사님 이메일 주소
https://ulgoon.github.io/

git bash 에 $사인은 shell 이 명령을 받아들일 준비가 됬다는 것을 의미

~ : 유저디렉토리

ls : 탐색 (list segment)

- flag
  -a : 숨김 파일까지 전부 표시
  -l : 상세한 정보 표시 / 어떤 사람이 수정했고, 어떤 권한이 있는지까지 표시

cd : change directory

mkdir : make directory

touch : creating new file (텍스트 기반의 새 파일을 만들 때)

mv : 파일의 이동

- 상대 경로 :
  . 현재 디렉토리 / .. 상위 디렉토리가 존재함
  > 다른 위치에 있는 파일을 상대경로를 이용하여 이동시키는 것이 가능

복사 : copy 복제 : clone / duplicate

mv [파일명] [바꿀파일명] : 파일의 이름 바꾸기

cp [복제할 파일] [위치와 이름지정] : 복제하여 가져옴

- 이름을 지정해주지 않고 경로만 표현할 경우 이름 그대로 복사됨.

remove : 논리적인 삭제 화확적 삭제 : 네일아트면 리무버 생각(발린거 지움) / 파일에 접근하는 방법을 지우는 것
어떻게 용량이 줄어드냐 = 일단 존재하면서 안쓰이는 상태가 되었다가 다른 파일이 덮어쓰게 되면서 그렇게됨
파일복구가 가능한 이유

delete : 물리적인 삭제 : 손톱뽑기 / 하드 디스크를 꺼내서 삭제하는 것

rm : 파일 삭제

rm \*.js (모든 js파일을 지워라) - 모든의 의미를 부여하는 \*

디렉토리는 rm으로 지울 수 없음

rm -r (존재하는 모든 오브젝트를 지우면서 디렉토리까지 지워라)

vi [파일] 파일을 vim으로 열어라
노말모드 / 인서트모드 / 비주얼모드 / 커맨드모드 등 경험

기본 동작 익히는 이유
commit 명령 편집을 vim으로 할거라서

cat : 파일 내용을 확인

#### git objects

1. blob: 파일 하나의 내용에 대한 정보
2. tree: blob이나 subtree의 메타데이터(디렉토리 위치, 속성, 이름 등)
3. 커밋 순간의 스냅샷

clone 방식과 init 방식

이폴더가 git repository인가 아닌가를 아는방법
폴더에 .git 이있나 없나 확인
.git 지우면 원래대로 돌아감

브랜치네임 Master = 깃이 만들어질 때부터 있었던 이름.
master slave 라는 용어가 있는데 남북전쟁 노예에 있던 용어가 아니냐는 논의
master라는 표현을 그만 쓰고, main이라는 표현 사용

- init

  - 디렉토리 만들기 - git init - github에서 레포지토리 생성(레포지토리명은 로컬 레포지토리명과 같게) - git branch명 변경(git branch -M main) - \*로컬에서 따로만들고 github에서 따로 만들어서 연관성이 없음. 서로 같은 녀석이라는 것을 알려주기 위해 -u를 꼭 넣어줌. 새로만든 브랜치에서의 첫 푸쉬는 항상 **-u**를 넣어주기.

  - clone

    - 디렉토리로 가서 git clone [주소]

TIL 작성법
항상 파일앞에 날짜 적는다
뒤에 공부한 기술 명시

- daily 파일
  파일 안에 날짜 오늘 무슨 일을 했다 정도.

conventional commit
사용자와 기계가 모두 이해할 수 있는 의미를 부여하기 위한 스펙
feat:
fix:
docs:
conf:
BREAKING CHANGE:
refactor:

### README.md

- 프로젝트와 Repository를 설명하는 책의 표지와 같은 문서
- 나와 동료, 이 repo의 사용자를 위한 문서

### .gitignore

blocklist 설정 (blacklist 용어 수정)

gitignore.io 가면 프로젝트 환경에 맞춰서 셋팅 가능

### LICENSE

MTI : 모든 행동에 제약 X / 저작권자는 소프트웨어와 관련한 책임에서 자유롭다.
Apache License 2.0 : Apache 재단이 만든 라이센스, 특허권 관련 내용 포함
GPL General Public License v3.0 :
가장 많이 알려져 있으며, 의무사항 (해당 라이센스가 적용된 소스코드 사용시 GPL을 따라야 함)이 존재합니다.

정적 사이트 생성기
hexo

### Branch

브랜치 명 설정시 어떠한 일을 하는 브랜치인지 명확하게 표현.

git branch : branch 확인

일은 로컬에서 / remote는 커밋을 끌어오는 용도로만 쓰는게 좋음.

git switch : 브래친 바꾸기

git merge : 땡기는 느낌인 것을 항시 기억. 보내는 것이 아니라

#### merge conflict

서로 다른 브랜치에서 같은 파일을 수정했을 때 발생.
=== 기준으로 각 브랜치를 비교하여 수정. 최종 결과물 완성
최종 결과를 add commit 하면 끝.

#### rebase

대상 브랜치를 분기점으로 다시 설정.

#### rename 작업

mv readme.md 를 unread.txt로 바꾸면
바꾼게 아니라 삭제하고 새로 생성한거 처럼 됨.

되돌리려면 다시 이름 바꿔주면 되돌려짐.

이름만 바꿔주기 위해서 mv 앞에 git만 써줘서 git한테 알려주면 됨.

git add . 할필요 없게 해주는 방법.

#### undo

최신 기준에서 변경된 변화량이 맘에들지 않아서 다시 최근상태로 돌리는 것.

git restore : 작업 디렉토리를 최근 기준으로 되돌리는 것.

#### commit message 수정

git commit --amend []

#### Reset Commit

Worst case: Reset
부수적인 효과
부정적인 부수적인 효과: 잘못된 파일을 만들고 취소했을 때 이미 퍼블릭 남아서 다른 사람들이 갖고 있었을 때 내거에선 지워도 다른사람들 가지고있어서 푸쉬될때마다 딸려 올라옴.

Best case: Revert
시점을 이전 커밋으로 되돌려서 해당 내역에 대해 commit, push 수행

--no-commit 플래그 꼭 해줘야함
안하면 돌아가는 하나의 커밋마다 전부 커밋 만듬.

merge 커밋을 되돌릴때는 -m
git revert -m {1 or 2} {merge commit id}

## branching models

- git flow

