# 1주차에 배운 내용 정리하기

### Git을 사용하는 이유
- 파일의 변경 사항 추적
- 여러 사용자 간 파일 작업 조율

### Git 공간 구분
- Working Directory: 내가 작업하고 있는 공간
- Staging Area: commit 전 변경할 작업을 선택하는 공간
- Local Repository: commit 후 작업이 기록되는 공간

### .gitignore
- Working Directory 내에서 추적되지 않아야할 파일들을 기록하는 파일
- 토큰, 서버 BaseURL, 사용자 간 공유하지 않는 파일 등이 포함

### 브랜치
- 내가 작업하는 독립적인 영역
- 브랜치 생성
```
git branch <branch name>
```
- 브랜치 이동
```
git switch <branch name>
```

### 깃 명령어
- 모든 파일 add
```
git add *
```
- 커밋 하기
```
git commit -m "commit message"
```
- 푸쉬 하기
```
git push
```