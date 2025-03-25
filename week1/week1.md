## Git 기본 개념 정리

---

### 🗂 Working Directory
개발자가 작업하는 공간, 작업 폴더

---

### 🧺 Staging Area
`git add`를 통해 변경사항이 1차로 저장되는 공간

---

### 📦 Local Repository
- 1차로 변경된 사항들이 `git commit`을 통해 최종적으로 저장되는 공간  
- Local repository에 있는 commit들이 `git push`를 통해 remote repository로 이동됨  
- `.git` 폴더에 staging area에 있는 파일들이 하나의 버전으로 저장됨

---

### 🌐 Remote Repository
네트워크 상의 다른 위치에 존재하며 여러 사람이 함께 공유할 수 있는 공간

---

## Git 작업 흐름 (Fork 기반 협업)

1. 사용자는 먼저 **Upstream Repository**를 본인의 GitHub 계정으로 **Fork**한다.
2. 이 Fork된 저장소는 내 GitHub 계정에 위치하며 **Origin Repository**가 된다.
3. 이후 이 Origin Repository를 로컬 컴퓨터로 `git clone`하여 작업한다.
4. 로컬에서 변경한 사항은 `git add`, `git commit`을 거쳐 Local Repository에 저장된다.
5. `git push` 명령어로 변경사항을 Origin Repository로 반영한다.
6. 변경사항을 **Upstream Repository**로 반영하고 싶다면 **Pull Request**를 보낸다.
7. PR(Pull Request)이 완료된 후, Upstream의 최신 내용을 반영하고 싶을 때 `git pull upstream main` 등을 사용한다.

---

## Remote 설정 방법

### 기본 구조
- `git clone`을 하면 클론한 저장소는 자동으로 `origin`으로 등록된다.
- 원본 저장소인 `upstream`은 직접 추가해줘야 한다.

### Upstream 등록 명령어

```bash
git remote add upstream https://github.com/원본-저장소주소.git
