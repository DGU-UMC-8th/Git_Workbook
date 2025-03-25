***< git, github 세미나 >***

**1.  git이란?**

    git = 버전 관리 시스템
    github = git 저장소의 클라우드

    <<git을 사용하는 이유>>

    1. 여러 사람이 동시에 작업 가능
    2. 항상 최신버전으로 작업을 유지

    >>Git은 협업을 편하게 하기 위한 도구<<

**2. git 명령어**
 
    - clone (url) : 레포와 폴더 연결
    - ignore : 파일을 추적 받지 않게 함
    - add : 스테이징 영역 이동
    - commit : 깃 버전 저장
    - mkdir : 파일 생성
    - branch : 브랜치 생성
    - init : git 저장소 초기화
    - merge : 브랜치 병함
    - pull : 원격 저장소 -> 로컬 저장소
    - push : 로컬 저장소 -> 원격 저장소

**3. git을 관리하는 구조**

*
    untracked<br>로컬 저장소 -> *git init* ->
*
    untracked -> staged<br>작업공간 -> *git add* -> staging 구역
*
    staged -> modified<br> add된 폴더 -> *git commit* -> 깃 버전 저장
*
    staged -> github<br> staged된 파일 -> *git push* -> 원격 저장소에 업로드

>> add, commit, push를 이용해 로컬 저장소에서 원격 저장소로 파일을 업로드하는 구조!

**4. 결론**

    처음으로 git의 구조와 작동원리를 배웠는데 이전에 사용할 때는 아무 생각 없이 습관적으로 사용하던 부분들을 기초부터 이해할 수 있었다. 또한 아직 git 사용 중 미숙한 부분, 잘 이해하지 못한 부분을 알 수 있었고 앞으로 협업과정에서 git을 반드시 사용하는 만큼 프로젝트 시작 전 git에 익숙해져야 할 것 같다.