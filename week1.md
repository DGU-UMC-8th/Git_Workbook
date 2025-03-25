<!-- week1.md 파일입니다. -->
## 1주차에 배운 내용 정리

### 플랫폼
플렛폼은 여러 분야에서 사용되는데 개발 분야에서는 소프트웨어가 실행될 수 있는 환경으로 윈도우, 맥OS,리눅스 안드로이드 등이 있다.

### Android OS
- 정의: 구글에서 운영하고 있는 운영체제로 리눅스 커널 기반이다.
- 특징: 오픈소스이며 스마트폰, 태블릿, 웨어러블 기기, TV, XR 등 여러 곳에서 사용된다.

### Android의 Architecture

#### 안드로이드의 권장 아키텍쳐
    
안드로이드의 권장 아키텍쳐는 UI Layer → Domain Layer (optional) → Data Layer로 이루어져 있다. 

- UI Layer는 화면에 데이터를 표시하는 역할을 한다. 사용자 입력으로 인해 데이터가 변할 때마다 변경사항을 반영하도록 UI를 업데이트해야한다.
- Data Layer는 0개부터 여러 개의 데이터소스를 각각 포함할 수 있는 저장소로 구성된다.
- Domain Layer는 복잡한 비즈니스 로직이나 여러 ViewModel에서 재사용되는 간단한 비즈니스 로직의 캡슐화를 담당한다.

#### 안드로이드 아키텍쳐 컴포넌트 (AAC)

테스트와 유지보수가 쉬운 앱을 디자인할 수 있도록 돕는 라이브러리 모음이다.

총 8개의 구성 요소로 Lifecycles, LiveData, ViewModel, Room, Paging, Databinding, Navigation, WorkManager이다.

1. Lifecycles : 앱 컴포넌트의 라이프사이클을 관리하기 위한 라이브러리
2. LiveData : 수명주기 인식, UI 갱신 도움
3. ViewModel : UI 관련 데이터의 저장과 관리를 담당
4. Room : SQLite 기반의 데이터베이스 엑세스 라이브러리 
5. Paging : 대량의 데이터를 페이지로 나누어 로드하고 표시하는데 사용
6. Databinding : 선언형 형식, Data를 UI에 바인딩하는 라이브러리
7. Navigation : 화면 간의 전환과 탐색을 관리하는 라이브러리
8. WorkManager : 안드로이드 앱에서 백그라운드에서 실행되는 작업을 예약하고 관리하기 위한 라이브러리

### Manifest의 주요 속성

- **`<manifest>`**: 앱의 패키지명과 전체적인 설정을 정의
- **`<application>`**: 모든 구성요소에 영향을 줄 수 있는 속성을 가짐
- **`<activity>`**: 앱의 시각적 사용자 인터페이스 요소를 구현하는 활동을 선언
- **`<intent-filter>`**: 활동, 서비스, broadcast receiver가 응답할 수 있는 인텐트의 유형을 지정
- **`<action>`**: 인텐트 필터에 작업을 추가
- **`<category>`**: 인텐트 필터에 카테고리 이름을 추가
- **`<permission>`**: 이 앱이나 다른 앱의 특정 구성요소 또는 기능에 대한 액세스를 제한하거나 보안 권한 선언
- **`<provider>`**: 콘텐츠 제공자 구성요소를 선언
- **`<receiver>`**: broadcast receiver를 애플리케이션의 구성요소 중 하나로 선언
- **`<service>`**: 서비스를 앱의 구성요소 중 하나로 선언

### Manifest의 4대 컴포넌트

activity : 화면을 구성하는 컴포넌트  
service : 백그라운드에서 작업하는 컴포넌트  
contents provider : 앱의 데이터를 가져오는 컴포넌트  
broadcast receiver : 안드로이드에서 발생하는 이벤트가 발생할 때 실행되는 컴포넌트  

### Intent

- Intent의 역할  
    일종의 메시지 객체이며 4대 컴포넌트를 실행하기 위해 시스템과 의사소통을 하기 위한 용도
    
- 명시적 Intent와 암시적 Intent의 차이  

    명시적 Intent : 실행하고자 하는 컴포넌트가 명확할 때 사용
    암시적 Intent : 호출할 대상이 달라질 수 있는 경우에 사용

### Android Layout

1. TextView : 화면에 텍스트를 표시
2. Button : 클릭할 수 있는 버튼
3. ImageView : 이미지를 표시
4. RecyclerView : 스크롤 가능한 목록을 표시
5. ScrollView : 세로 방형으로 스크롤 가능한 컨테이너
6. NestedScrollView : 스크롤 가능한 뷰를 함께 사용할 때 필요
7. BottomNavigationView : 앱 하단에 네비게이션 바를 표시
8. TabLayout :  탭 형식의 네비게이션을 제고하는 Layout
9. FloatingActionButton : 화면에 떠 있는 버튼
10. margin : View 외부의 여백
11. padding : View 내부의 여백
12. chainStyle : ConstraintLayout에서 여러 뷰를 체인으로 연결
13. id 네이밍 : View의 id로 일관성있고 가독성이 높게 지어야 함


