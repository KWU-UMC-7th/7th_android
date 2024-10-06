- Activity
    - Activity란 무엇인가요?
    사용자에게 보여지는 앱의 화면이다. Kotlin(Java) 클래스 파일과 레이아웃 XML파일로 구성되고, XML파일에서는 액티비티의 UI를 자유롭게 만들 수 있다. 액티비티를 생성하고 View에 동작을 추가하는 코드는 클래스 파일에 정의해야 한다.
    - 새로운 Activity를 만들기 위해선 어떻게 해야 할까요?
    Android Studio에서 **New > Activity**를 만들면 클래스 파일과 XML 파일이 자동으로 생성된다.
    - AppcompatActivity란 무엇인가요?
    Activity의 자식의 자식의 자식의 자식 class
    특정 버전부터 지원되는 ActionBar를 이하 버전에도 적용가능하게 해주는 Activity.
- Activity-Layout 결합
    - findViewById
        - findViewById 사용법
        `findViewById(R.id.viewId)`를 사용하여 XML 레이아웃 파일에서 뷰를 찾아 Activity/Fragment에 연결
    - ViewBinding
        - ViewBinding 사용법
        `activity_main.xml`을 사용할 경우, 자동으로 생성된 `ActivityMainBinding` 클래스를 통해 뷰에 접근. `binding = ActivityMainBinding.inflate(layoutInflater)`로 초기화 후, `binding.viewId` 형태로 뷰 접근 가능
    - findViewById보다 ViewBinding이 권장되는 이유
        - findViewById의 단점 
        뷰 ID를 잘못 참조할 가능성이 있어 컴파일 타임 에러가 발생하지 않음
        - ViewBinding의 장점
        타입 안정성 보장, null 안전성 증가, 불필요한 `findViewById` 호출을 줄여 코드 가독성 향상
- 새로운 Activity를 띄우는 방법
    - Intent란 무엇일까요?
        - 인텐트는 메시징 객체 이다. 메시징 객체는 통신을 위한 객체이다. 즉, 인텐트를 통해서 다른 앱 구성요소로 메시지를 통해 요청을 전달할 수 있다. 인텐트로 통신을 할 수 있는 구성요소는 위에 정리한 4대 컴포넌트 중 콘텐츠 프로바이더를 제외한 액티비티, 서비스, 브로드 캐스트 리시버이다.
    - Intent를 사용하여 Activity 간 데이터를 전달하려면 어떻게 해야할까요?
        - A Activity에서 Intent에 Bundle 객체를 담아서 B Activity 호출. B Activity에서 Intent 인스턴스 이용하여 Intent.getString(key) 로 데이터 전달받아서 사용
- 명시적 Intent와 암시적 Intent
    - 명시적 Intent란 무엇일까요?
    특정 컴포넌트를 명시하여 실행하는 인텐트
    - 암시적 Intent란 무엇일까요?
    특정 구성요소의 이름을 지정하지 않는 대신 실행할 일반 작업을 선언하여 다른 앱의 구성요소가 처리할 수 있도록 하는 인텐트
    - 두 Intent를 사용하는 예시에는 각각 무엇이 있을까요?
    명시적 Intent → 다른 Activity로 전환
    암시적 Intent → 메일 보내는 앱으로 전환
- Fragment
    - Framgent의 정의는 무엇일까요?
    앱 UI의 재사용 가능한 부분
    - Fragment를 사용하는 이유는 무엇일까요?
    런타임시 UI 모습을 사용자와 상호작용하면서 실시간으로 수정 가능
    - 새 Fragment는 어떻게 만들 수 있을까요?
    Android Studio에서 **New > Fragment** 를 만들면 클래스 파일과 XML 파일이 자동으로 생성된다.
        - Fragment
    - Fragment는 어떻게 화면에 보이게 할 수 있을까요?
    Fragment는 Activity와 달리 독립적으로 존재 불가.  반드시 Activity나 다른 프래그먼트에 호스팅 되어야함.
- Bundle
    - Bundle은 무엇일까요?
    Key-value 형식의 데이터 저장 객체
    - Intent와 Bundle을 결합하는 방법은 무엇일까요?
    Intent 객체를 생성 후 객체에 putExtra(key, value) 형식으로 Bundle 데이터 결합
- FragmentManager
    - FragmentManager란 무엇일까요?
    앱 프래그먼트에서 프래그먼트를 추가, 삭제 또는 교체하고 백 스택에 추가하는 등의 작업을 실행하는 클래스
    - FragmentManager는 언제 사용해야 될까요?
    Kotlin에선 supportFragmentManager로 접근
    container에 Fragment 교체할 때
    container 내의 현재 프래그먼트의 참조를 가져올 때
- BottomNavigationView란?
    - BottomNavigationView란 무엇이고, 어떤 기능을 할까요?
    화면 제일 하단에 있는 네비게이션 역할을 하는 버튼 모음으로, 각각의 버튼을 눌렀을 때 FrameLayout(Container)에 fragment를 붙일 수 있다.
    - BottomNavigationView가 사용된 예시에는 무엇이 있을까요?
    카카오톡, 당근마켓 등 전반적인 App의 홈 화면
- BottomNavigationView의 구성 요소
    - BottomNavigationView를 사용하려면 레이아웃에 추가를 해야합니다. 이 때 어떤 값들이 필수적으로 지정되어야 할까요?
    id, width, height, menu
    - Menu 리소스 XML
        - <menu> 태그는 무엇일까요?
        <item>, <group>을 하위 요소로 가지는 메뉴 항목의 컨테이너
        - <item> 태그는 무엇일까요?
        Menu 내 단일 요소
        - <item> 태그에 설정할 수 있는 항목에는 무엇이 있을까요?
        id : item의 고유의 id값으로 요소를 구분할 때 사용
        showAsAction : v3.x 이상을 사용하며, 메뉴를 ActionBar나 ToolBar에 보여줄지 여부를 지정(ifRoom, always, never, withText)
        menuCategory : menu category를 정의하는 데 사용
        title : menu에 보여줄 이름 문자열
        titleCondensed : 이름 문자열이 너무 길었을 때 사용하는 문자열
        icon : drawable icon
    - 화면 구성
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/3cf80661-4cea-48b2-b1b8-a432b34028db/Untitled.png)
        
        1. 왼쪽의 예시 화면에서 (A)와 (B)에 해당하는 각각의 알맞은 **화면 구성 요소**를 선택해주세요!
            - (A) = Activity
            - (B) = Fragment
        2. 왼쪽 화면을 구성하기 위해서 일반적으로 몇 개의 Fragment가 필요한가요??
            - 정답 )3 개
- BottomNavigationView 설정하기
    - 각 Item을 클릭했을 때 나타나는 이벤트 설정하기
    - BottomNavigationView의 주요 속성들을 정리해 주세요!
        - 각 Item을 클릭했을 때 나타나는 이벤트 설정 방법은 꼭 정리하기 **[필수]**
        - `app:itemActiveIndicatorStyle="@android:color/transparent"` → 아이콘 선택시 뒷 배경 설정
        - `app:itemIconSize="24dp"` → 아이콘 사이즈 설정
        - `app:itemIconTint="@drawable/bottom_navigation_color"`  → 아이콘 색상 설정 (selector 생성하여 선택될 경우와 선택되지 않았을 경우 설정 가능)
        - `app:itemTextColor="@drawable/bottom_navigation_color"` → 텍스트 색상 설정
            
            (selector 생성하여 선택될 경우와 선택되지 않았을 경우 설정 가능)
            
        - `app:labelVisibilityMode="labeled"` → 텍스트(라벨)를 항상 표시할지/ 선택시에만 표시할지 등 라벨 속성 지정