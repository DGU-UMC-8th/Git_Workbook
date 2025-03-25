- 플랫폼
    
     여러 기능을 제공하는 공통 실행환경을 말한다. 예를 들어, Java라는 언어를 기반으로 프로그램의 개발 및 실행을 할 수 있다는 점에서 Java는 플랫폼이라고 할 수 있다. Android 또한 해당 환경을 기반으로 다양한 기능을 제공하기에 플랫폼이라고 이해할 수 있다.
    
- Android OS
    - 정의: 리눅스를 기반으로 한 모바일 장치용 운영체제
    - 특징
        1. 오픈소스 소프트웨어로 구성되어 있어 많은 정보가 공개되어 있다
        2. Java 언어를 이용한다
        3. 모바일 뿐만 아니라 네비게이션, PMP 등의 타 기기에도 쉽게 적용할 수 있어 이식성이 우월하다
        4. 리눅스 커널을 기반으로 하고 있다
- Android의 Architecture
    - 안드로이드의 권장 아키텍쳐는 무엇일까요?
        
        Android 앱에는 최소한 UI 레이어와 데이터 레이어가 있어야 한다. 추가적으로 두 레이어 간의 상호작용을 단순화하고 재사용하기 위한 도메인 레이어를 추가할 수 있다.
        
        - UI 레이어 : 화면에 애플리케이션 데이터를 표시하는 역할을 한다. 사용자 상호작용과 외부입력(예: 네트워크 응답)으로 인해 데이터가 변할 때마다 UI가 업데이트 되어야 한다. UI 레이어는 화면에 데이터를 렌더링하는 UI 요소(UI elements)와 데이터를 받고 이를 UI에 노출하며 로직을 정리하는 State holders로 구성된다.
        - 데이터 레이어 : 0개부터 여러 개의 데이터 소스를 각각 포함할 수 있는 저장소로 구성된다. 처리하는 데이터의 종류별로 저장소 클래스를 만들어야 한다. 저장소 클래스에서는 (1) 데이터를 노출시키고, (2) 데이터의 변경 사항을 한 곳에 집중시키고, (3) 데이터 소스 간의 충돌을 해결하고, (4) 앱의 다른 부분에서 데이터 소스를 추상화하며, (5) 비즈니스 로직을 포함한다.
        - 도메인 레이어 : UI 레이어와 데이터 레이어 사이에 선택적으로 있을 수 있는 레이어이다. 복잡하거나 재사용되는 비즈니스 로직의 캡슐화를 담당한다.
        
        <aside>
        💡
        
        - State holders : 데이터 레이어와 UI 요소 사이에서 로직이 필요한 경우 중개자 역할을 한다. 필요한 로직에 대한 데이터 소스의 액세스 권한을 제공하는 방식을 취한다. 모든 UI 요소는 상응하는 state holders와 일대일 대응 관계를 갖는다.
        - 비즈니스 로직 : 앱에 가치를 부여하는 요소로, 앱의 데이터 생성, 저장, 변경 방식을 경정하는 규칙
        </aside>
        
    - 안드로이드 아키텍쳐 컴포넌트 (AAC)는 무엇일까요?
        - Android Architecture Components. 안드로이드 내의 여러 컴포넌트들을 부드럽게 연결하기 위해 구글에서 안드로이드 앱을 위한 아키텍처를 정의했고, 이를 구현하기 위해 제공한 라이브러리들을 이르는 말.
        - 구성 라이브러리
        1. DataBing
        2. LifeCycle
        3. Navigation
        4. Room
        5. Paging
        6. WorkManager
        7. Livedata
        8. ViewModel
- Manifest의 주요 속성
    
    <manifest>는 AndroidManifest.xml 파일의 루트 요소이다. <application> 요소를 반드시 포함해야 하고, xmlns:android 및 package 속성을 지정한다. 다음은 주요 속성들이다.
    
    1. xmlns:android
    Android 네임스페이스를 정의한다.
    2. package
    Android 앱의 패키지 이름을 나타내고, 이는 앱의 고유한 애플리케이션 ID이다. com.example.프로젝트명의 형식으로 package의 이름이 결정된다.
    3. android:targetSandboxVersion
    앱에서 사용할 샌드박스의 버전을 지정한다. 샌드박스 버전 번호가 높을수록 보안 수준이 높다. 기본값은 1이며, 2로도 설정 가능하다.
    
    레벨 2 샌드박스에서는 네트워크 보안 구성에서는 usesCleartextTraffic의 기본값이 false이고(1), UID 공유는 허용되지 않는다(2). 앱이 설치된 후에는 타겟 샌드박스 값을 더 높은 값으로만 업데이트할 수 있다.
    4. android:versionCode
    앱의 버전을 나타내는 정수이다. 이는 버전끼리 최신인지 비교할 때만 사용되며, 사용자에게 표시되는 버전 번호가 아니다.
    5. android:versionName
    앱의 배포 버전을 나타내는 문자열이다. 사용자에게 공개된다.
    6. android:installLocation
    앱의 기본 설치 위치이다.
- Manifest의 4대 컴포넌트
    
    Manifest의 4대 컴포넌트는 정확히 모르겠어서, Android의 4대 컴포넌트에 관해 공부하고 정리했다.
    
    - 컴포넌트(Component)란, Android 앱에 있어 필수적인 구성 요소를 의미한다. 각 컴포넌트는 고유한 용도와 수명주기를 갖는다. 또한, 시스템이나 사용자가 앱에 진입할 수 있는 진입점이 된다. 어떤 컴포넌트는 다른 컴포넌트에 종속되기도 한다.
    - Android의 4대 컴포넌트
    1. 액티비티 (Activities)
     사용자와 상호작용하는 단일 화면을 나타낸다. 각 액티비티는 독립적으로 작동하여, 앱이 다른 앱의 액티비티를 실행하는 등의 작업도 가능하다.
     액티비티는 시스템과 앱 간의 상호작용을 돕는데, 보고 있는 화면을 유지하도록 시스템이 해당 프로세스를 계속 실행하게 하고, 프로세스 종료 시 이전 상태를 복원해 사용자 경험을 유지하도록 돕는 것이 이에 해당한다. 또한, 종료된 프로세스 중 다시 실행될 가능성이 높은 액티비티의 우선도를 높이고, 앱 간 사용자 흐름을 구현하고 시스템이 이를 조율하는 기능을 제공한다.
    2. 서비스 (Service)
    백그라운드 작업을 수행하는 컴포넌트로, 사용자 인터페이스 없이 장시간 작업이나 원격 프로세스를 처리한다. Started Services와 Bound Services, 두 가지 유형으로 나눌 수 있다.
        - Started Services
        작업이 완료될 때까지 서비스를 계속 실행하도록 시스템에 지시한다. 이때, 사용자가 인지하는 작업(예. 음악 재생)은 끊기지 않고 프로세스가 실행되지만, 사용자가 인지하지 못하는 작업(예. 데이터 동기화)은 시스템이 필요에 따라 종료 후 다시 시작하는 등 자유롭게 관리한다.
        - Bound Services
        다른 앱이나 시스템의 요청으로 실행되는 서비스로, 다른 프로세스에 API를 제공하고 종속성이 형성된다. 이러한 종속성을 기반으로 프로세스가 실행된다.
    3. 브로드캐스트 리시버 (Broadcast Receivers)
    시스템이 앱에 이벤트를 전달하여 앱이 응답할 수 있도록 하는 컴포넌트이다. 이때, 이벤트란 화면에서의 사용자 이벤트가 아닌, 배터리 부족 알람과 같은 시스템에서 발생하는 특정 상황을 말한다.
    4. 콘텐츠 프로바이더 (Content providers)
    앱 간 데이터 공유를 위한 컴포넌트로, 중앙 저장소로의 데이터 액세스를 관리한다. 다른 앱은 콘텐츠 프로바이더를 통해 데이터를 쿼리하거나, 콘텐츠 프로바이더가 허용할 경우에는 수정도 가능하다.
- Intent
    - Intent의 역할은 무엇일까요?
    콘텐츠 프로바이더를 제외한, 컴포넌트 간에 작업을 요청하는 데 사용하는 메시지 객체이다.
    - 명시적 Intent와 암시적 Intent의 차이는 무엇일까요?
     intent의 이용에 있어 데이터를 받을 컴포넌트를 명시하는 경우를 **명시적 intent**, 그렇지 않은 경우를 **암시적 intent**라고 한다.
     때문에, 명시적 intent는 한 컴포넌트에서 어떤 컴포넌트로 작업을 요청하는지가 명시가 된 반면, 암시적 intent는 대상이 되는 컴포넌트를 지정하지 않고 특정한 작업을 지정하여 이를 수행할 수 있는 컴포넌트를 호출한다. 이때, 하나가 아닌 여러 개가 호출될 수도 있다. 특정한 작업을 지정한 intent를 가지고 이를 실행할 수 있는 함수를 호출하면, Android 시스템이 intent의 조건을 만족하는 컴포넌트에 intent를 전달하고 실행시킨다.
- Android Layout
    1. TextView
        
        사용자에게 텍스트를 표시하는 뷰 요소.
        
        - 앱 실행 중 텍스트 변경: setText(TextView 객체)
    2. Button
        
        사용자의 클릭 이벤트를 처리하는 기능을 하는 텍스트 또는 이미지의 뷰 요소.
        
        - 클릭 이벤트 처리
        
        ```xml
        Button객체.setOnClickListener(new View.OnClickListener()) {
        	public void OnClick(View view객체) {수행할 작업}
        }
        ```
        
    3. ImageView
        
        사용자에게 이미지를 표시하는 뷰 요소. src 속성을 통해 이미지가 있는 경로를 지정.
        
        - 앱 실행 중 텍스트 변경: setImageResource(R….이미지 경로)사용자에게 이미지를 표시하는 뷰 요소. src 속성을 통해 이미지가 있는 경로를 지정.
        - 앱 실행 중 텍스트 변경: setImageResource(R….이미지 경로)
    4. RecyclerView
        
        제한된 영역에서 같은 형식을 가진 여러 개의 뷰를 표시할 때, 영역에서 사라진 뷰를 내용만 바꾸어서 재사용하는 경우 사용할 수 있는 뷰 요소.
        
        - 뷰의 재활용이 없는 ListView는 스크롤 시 뷰가 계속해서 생성되지만, RecyclerView는 스크롤 과정에서 사라진 뷰의 내용만 바꾸어서 화면에 표시하는 게 가능하다.
         이는 전체 아이템 수에 기반하여 (화면에 표시되는 아이템 수)+(버퍼와 같은 여분 아이템의 수)의 ViewHolder를 미리 생성하고, 화면에 표시되지 않는 뷰를 재사용하는 것이기 때문에, 이전 데이터가 초기화되지 않고 남아있는 문제가 생길 수 있다.
    5. ScrollView
        
         화면의 크기를 초과하는 긴 콘텐츠를 표시할 때 사용한다.
         단 1개의 자식만을 가지고, 뷰의 크기는 자식의 크기만큼 늘어난다. 여러 개의 콘텐츠를 표시해야 한다면, 이를 감싸는 레이아웃이 필요하고 이것을 다시 ScrollView가 감싸는 형식으로 이용한다.
        
        - android:fillViewport=”true”
        자식 뷰가 ScrollView의 크기에 맞춰 빈 공간을 채우는 속성
    6. NestedScrollView
        
         ScrollView와 같다. 하지만, RecyclerView와 함께 사용하는 경우 차이가 있다.
        
         스크롤되는 화면이 여러 개인 경우, 필요에 따라 ScrollView와 RecyclerView를 함께 사용한다. 이러한 경우, RecylcerView가 모든 아이템을 표시해 더 이상 스크롤할 수 없을 때 ScrollView가 스크롤되는 문제가 발생한다. 하지만, NestedScrollView를 사용하면 화면에 표시된 뷰들이 하나의 그룹이 된 것처럼 스크롤되게 할 수 있다.
        
        - NestedScrollView를 사용함으로써 RecyclerView를 자식 뷰로 구성하게 되면, 스크롤 과정에서의 문제는 해결할 수 있으나 뷰를 재사용하는 RecyclerView의 기능은 사용할 수 없게 된다. 때문에, 아이템이 많아 뷰의 재사용이 필요한 경우에는 NestedScrollView의 사용을 지양해야 한다.
            
            아이템의 사용이 많은 경우, RecyclerView에서 각 뷰 요소를 분리해 하나의 ViewHolder와 매칭시켜 관리해주어야 한다. 이러한 작업은 RecyclerView의 Adapter 클래스(.kt)에서
            
            1. getItemViewType(position: Int): Int 함수를 통해 각 아이템에 인덱스를 매칭하고,
            2. onCreateViewHolder(parent: ViewGroup, viewType: Int): RecyclerView.ViewHolder 함수에서 인덱스에 대응되는 적절한 layout을 객체화시킨 후, ViewHolder를 생성해서 리턴하고
            3. onBindViewHolder(holder: RecyclerView.ViewHolder, position: Int) 함수에서 인덱스에 따라 ViewHolder에 데이터를 설정하는 방식으로 이루어진다.
    7. BottomNavigationView
        
        화면 하단의 네비게이션 역할을 하는 버튼 모음이다. 각각의 버튼을 눌렀을 때 화면의 전환이 이루어지는데, 이 화면은 Fragment로 구성한다. 이때, 선택된 페이지에 대한 레이아웃은 FrameLayout으로 구현하고, 뷰인 만큼 특정 레이아웃 안(예. ConstraintLayout 등)에 작성한다.
        
        - Fragment란?
        앱의 UI 중에 재사용 가능한 것을 잘라 독립적인 수명주기를 가진 ‘**레이아웃**’. 자체 입력 이벤트를 처리할 수는 있지만, 독립적으로 존재할 수 없고 액티비티 위에서 존재해야 한다.
    8. TabLayout
        
        화면에 탭을 만드는 레이아웃이다. 레이아웃과 아이템의 생성에 필요한 태그는 다음과 같다.
        
        - com.google.android.material.tabs.TabLayout 혹은 TabItem
        
        생성할 항목의 개수만큼 TabItem 블록을 생성하고 text 속성을 통해 이름을 설정한다.
         이때, 항목이 많아져 스크롤이 필요한 경우 다음 속성을 추가한다.
        
        - app:tabMode=”scrollable”
    9. FloatingActionButton
        
        화면의 움직임과 별개로 고정된 위치에서 간단한 메뉴를 제공하는 버튼(플로팅 버튼)이다. 다음 태그를 통해 위젯을 추가할 수 있고, 버튼의 이벤트 처리 방식은 Button에서와 동일하다.
        
        - <android.support.design.widget.FloatingActionButton> 태그를 통해 추가할 수 있다.
    10. margin
        
        뷰 요소 테두리로부터 부모 레이아웃 테두리까지의 여백
        
    11. padding
        
        뷰 요소 테두리와 뷰 안의 내용 사이의 여백
        
    12. chainStyle
        
        ConstraintLayout에서 뷰 간의 상호 참조 연결을 할 때, 뷰들을 어떤 방식으로 연결시켜 표현할 지를 나타내는 속성.
        
        chain에서의 뷰들 중 왼쪽과 위쪽이 우선 순위를 갖고 이를 **chain head**라고 부른다. 이때, chain head의 블록에 다음과 같이 기술하여 chainStyle을 지정할 수 있다. 사용 가능한 값은 spread, spread_inside, packed가 있다.
        
        ```xml
        app:layout_constraintHorizontal_chainStyle=””/app:layout_constraintHorizontal_chainStyle=””
        ```
        
        - spread : 뷰들을 골고루 펼친다.
        - spread_inside : spread와 비슷하지만, 가장 외곽의 뷰들은 부모 뷰와 여백이 없는 상태로 골고루 펼쳐진다.
        - packed : 뷰들이 뭉치게 되고, 부모 뷰로부터의 여백을 같게 한다.
    13. id 네이밍
        
        id 지정 방식 : android:id=”@+id/아이디”