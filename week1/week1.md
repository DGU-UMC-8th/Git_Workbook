## Github 실습

#### [week1 - 메이/백지은]

### 1. github란? 
:  git 저장소를 관리하는 클라우드 기반 호스팅 서비스

### 2. git command 명령어

- `git add` : staging area로 작업 변경 사항을 이동

- `git branch` : 저장소 내에 격리된 개발 환경 생성

- `git checkout` : 특정 커밋 혹은 브랜치로 이동

- `git clean` : add 하지 않은 파일 제거

- `git commit --amend` : 가장 최근 커밋 수정

- `git config` : git 설치에 대한 구성 옵션 변경

- `git fetch` : 원격 저장소의 브랜치와 파일을 최신 버전으로 업데이트

- `git log` : 해당 브랜치에 대한 커밋 기록 탐색

- `git merge` : 분기된 브랜치의 변경사항 통합

- `gut rebase` : 브랜치를 이동하여 병합 커밋 없이 새 커밋 히스토리 생성

- `git reset` : 작업 디렉토리 파일의 변경 사항 취소

- `git revert ` : 잘못된 커밋 취소

- `git status` : 작업 디렉토리와 스테이징된 스냅샷 상태 표시


### 3. Git Flow

1. `git add` : working directory -> staging area

2. `git commit` : staging area -> localrepo

3. `git push` : localrepo -> remote repo

4. `git pull` : remote repo -> localrepo

5. `git checkout` : localrepo -> working directory

6. `git merge` : localrepo -> working directory
