> 과제는 `mission/w02basiclayout (branch:W02)` 을 참고해주세요

### 2주차 개발일지

> 결과 영상 및 수행항목 워크북 링크입니다

https://www.notion.so/makeus-challenge/Chapter-2-Activity-Fragment-1a367286c818499caab5225b46445317?pvs=4#111b57f4596b81c2970aeb09921bc9ba

### 🎯 키워드 Essential

- Activity
  - Activity란 무엇인가요?
    안드로이드 애플리케이션에서 UI를 담당하는 기본 컴포넌트로 각각의 액티비티는 하나의 화면을 나타내며, 특정 액티비티는 앱의 진입점 역할을 수행하기도 함.
  - 새로운 Activity를 만들기 위해선 어떻게 해야 할까요?
    앱루트 폴더에서 우클릭 > New > Activity > Empty Views Activity를 선택해여 생성
    (xml, kotlin 파일이 자동 생성되며, 자동으로 Manifest 파일에도 액티비티가 등록됨)
  - AppcompatActivity란 무엇인가요?
    래거시인 Activity를 확장한 클래스로, AndroidX 라이브러이에 포함된 컴포넌트.
    이전 안드로이드 버전에서도 최신 기능을 사용할 수 있도록 하며, ActionBar와 같은 최신 UI(Material Design) 요소를 호환성 있게 제공함.
    특히 Fragment를 사용하는 앱에서 필수적으로 사용해야 함.
- Activity-Layout 결합

  - findViewById
    - findViewById 사용법
      ```kotlin
      findViewById<Type>(R.id.id_string)
      ```
  - ViewBinding

    - ViewBinding 사용법
      우선 앱 수준의 build.gradle 파일에서 다음과 같은 설정을 추가한다

      ```kotlin
      viewBinding {
      		enabled = true
      }
      ```

      - Activity

        ```kotlin
        private lateinit var binding: ActivityNameBinding

        onCreate() {
        	binding = ActivityNameBinding.inflate(layoutInflator)
        	setContentView(binding.root)
        }
        ```

      - Fragment

        ```kotlin
        private var _binding: FragmentNameBinding? = null
        private val binding get() = _binding!!

        override fun onCreateView(
        	inflater: LayoutInflator,
        	container: ViewGroup?,
        	savedInstanceState: Bundle?
        ): View? {
        	_binding = FragmentNameBinding.inflate(inflater, container, false
        	return binding.root
        }
        ```

  - findViewById보다 ViewBinding이 권장되는 이유
    - findViewById의 단점
      - 여러 컴포넌트에 존재하는 같은 id를 동시에 가져오게 되어 잘못된 컨트롤을 유발할 수 있다
      - id를 가져오고나서 타입검사가 진행되기 때문에 잘못된 타입의 변수에 할당 시 에러가 발생한다
    - ViewBinding의 장점
      - 바인딩된 뷰에서의 id만 자동완성되어 사용할 수 있기에 실수의 여지가 없다
      - 타입 추론이 가능하여 변수에 지정할 때 에러가 발생할 여지가 없다

- 새로운 Activity를 띄우는 방법
  - Intent란 무엇일까요?
    안드로이드에서 컴포넌트 간 통신을 담당하는 메세지 객체로, 액티비티를 비롯해 서비스, 브로드캐스트 리시버 등의 앱 컴포넌트간 데이터를 주고받는데 사용한다.
  - Intent를 사용하여 Activity 간 데이터를 전달하려면 어떻게 해야할까요?
    Intent 객체에 putExtra 메서드를 호출하는 방식으로 인텐트에 key-value 형태로 데이터를 담을 수 있음.
    ```kotlin
    val intent = Intent(this, SecondActivity::class.java)
    intent.putExtra("username", "Woong")
    intent.putExtra("age", 25)
    startActivity(intent)
    ```
    이렇게 넘긴 데이터는 intent를 통해 가져올 수 있다.
    ```kotlin
    val username = intent.getStringExtra("username")
    val age = intent.getIntExtra("age", 0)
    ```
- 명시적 Intent와 암시적 Intent

  - 명시적 Intent란 무엇일까요?
    앱 내부의 특정 컴포넌트를 직접 호출할 때 사용하는 인텐트로, 목적지의 컴포넌트가 명시적으로 지정되어 있음.
  - 암시적 Intent란 무엇일까요?
    앱 외부의 다른 앱이나, 시스템 컴포넌트에 작업을 요청할 때 사용하는 인텐트로, 목적지의 컴포넌트가 명시적으로 지정되어 있지 않아 안드로이드 시스템이 해당 작업을 처리할 수 있는 앱을 찾아 실행함.
  - 두 Intent를 사용하는 예시에는 각각 무엇이 있을까요?

    ```kotlin
    // 명시: 새 액티비티 실행
    val intent = Intent(this, SecondActivity::class.java)
    startActivity(intent)
    ```

    ```kotlin
    // 암시: 웹페이지 열기
    val intent = Intent(Intent.ACTION_VIEW)
    intent.data = Uri.parse("https://google.com")
    startActivity(intent)

    // 암시: 카메라 실행
    val intent = Intent(MediaStore.ACTION_IMAGE_CAPTURE)
    startActivity(intent)
    ```

- Fragment

  - Framgent의 정의는 무엇일까요?
    안드로이드에서 UI와 동작을 모듈화할 수 있는 구성요소로, 액티비티 안에서 하나의 화면을 여러 개의 부분화된 화면으로 나누거나, 동적으로 UI를 변경하거나, 반응형 디자인으로 위젯을 배치할 때 사용함.
  - Fragment를 사용하는 이유는 무엇일까요?
    - 화면의 모듈화 및 재사용: 하나의 프래그먼트를 잘 모듈화를 한다면 여러 액티비티에서 재활용 할 수 있다.
    - 반응형 디자인: 화면 크기와 방향에 맞추어 동적으로 UI를 조정 가능.
    - Activity 관리 용이: 복잡한 UI를 액티비티 하나에서 관리하는 것 보다 여러개의 프래그먼트로 나누어 관리하는게 더 편함.
    - 동일 액티비티 내에서 여러 화면 관리: 하나의 액티비티에서 여러 프래그먼트를 이용해 화면을 보여주면 성능과 사용자 경험에서 유리할 수 있음.
  - 새 Fragment는 어떻게 만들 수 있을까요?
    앱루트 폴더에서 우클릭 > New > Fragment > Fragment (Blank)를 선택해여 생성
  - Fragment는 어떻게 화면에 보이게 할 수 있을까요?

    - 정적 등록: xml 에서 정적으로 등록
      ```xml
      <fragment
          android:id="@+id/blankFragment"
          android:name="com.example.app.BlankFragment"
          android:layout_width="match_parent"
          android:layout_height="match_parent" />
      ```
    - 동적 등록: kotlin 코드에서 동적으로 등록

      ```kotlin
      val fragment = BlankFragment()

      supportFragmentManager.beginTransaction()
      		.add(binding.fragment_container, fragment)
      		.commit()
      ```

- Bundle
  - Bundle은 무엇일까요?
    안드로이드에서 데이터를 저장하고 전달하기 위한 일종의 Map 객체로, put*()으로 저장, get*()으로 불러온다. (\*Primitive type)
  - Intent와 Bundle을 결합하는 방법은 무엇일까요?
    bundle은 intent의 extra의 형태로 포함되어 있다. 하지만, bundle 객체를 intent의 putExtras 메서드의 인자로 전달하는 방식으로 결합할 수도 있다.
    다른 액티비티에서도 수신할 때 `intent.extras` 로 bundle을 가져올 수 있다.
- FragmentManager
  - FragmentManager란 무엇일까요?
    안드로이드에서 Fragment의 추가, 제거, 교체 등의 생명주기를 관리하는 클래스로 액티비티와 프래그먼트 간의 상호작용을 관리함.
    `.beginTranstaction()` 과 `.commit()` 사이에 메서드를 호출하여 프래그먼트를 관리한다.
  - FragmentManager는 언제 사용해야 될까요?
    - 여러 프래그먼트를 관리해야 할 경우
    - 여러 프래그먼트간 서로 상호작용을 해야 할 경우
    - 화면 회전과 같이 앱 상태가 변경될 때 프래그먼트의 상태를 유지해야 할 경우
    - 프래그먼트의 동적생성 및 삭제할 경우
- BottomNavigationView란?
  - BottomNavigationView란 무엇이고, 어떤 기능을 할까요?
    안드로이드의 하단 내비게이션을 제공하는 UI 컴포넌트로, 사용자에게 앱의 주요 화면 간 탐색하는 방법을 제공함.
    FragmentManager와 함께 사용하여 선택된 아이템에 따라 다른 프래그먼트를 보여주며, 프래그먼트 백스택을 관리하여 뒤로가기 버튼 탭 시 이전 화면으로 돌아가는 기능을 제공할 수도 있음.
  - BottomNavigationView가 사용된 예시에는 무엇이 있을까요?
    유튜브, 인스타그램, 구글맵스 등 여러 기능을 제공하는 대부분의 앱에서 사용 중
- BottomNavigationView의 구성 요소
  - BottomNavigationView를 사용하려면 레이아웃에 추가를 해야합니다. 이 때 어떤 값들이 필수적으로 지정되어야 할까요?
    - android:layout_width/height: 모든 컴포넌트의 필수 constraint
    - app:menu: 내비게이션에 표시될 메뉴 항목을 정의한 메뉴 리소스 파일(xml)을 지정
  - Menu 리소스 XML
    - \<menu\> 태그는 무엇일까요?
      안드로이드에서 사용자 인터페이스의 메뉴 항목을 정의하는 xml 태그로, 옵션, 컨텍스트(long tap), 하단 내비게이션 등 다양한 메뉴 리소스를 구성할 때 사용함.
    - \<item\> 태그는 무엇일까요?
      xml 메뉴 리소스 파일 내에서 개별 메뉴 항목을 정의하는데 사용되는 태그로, menu 태그 내부에 포함되어 각 항목의 속성을 설정함.
    - \<item\> 태그에 설정할 수 있는 항목에는 무엇이 있을까요?
      - android:id: 아이디
      - android:title: 메뉴 항목에 표시될 텍스트
      - android:icon: 메뉴 항목에 표시될 아이콘
      - android:showAsAction: 표시 방식 (always, ifRoom, never)
  - 화면 구성
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/3cf80661-4cea-48b2-b1b8-a432b34028db/Untitled.png)
    1. 왼쪽의 예시 화면에서 (A)와 (B)에 해당하는 각각의 알맞은 **화면 구성 요소**를 선택해주세요!
       - (A) = `Activity` / Fragment
       - (B) = Activity / `Fragment`
    2. 왼쪽 화면을 구성하기 위해서 일반적으로 몇 개의 Fragment가 필요한가요??
       - 정답 ) 3 개
- BottomNavigationView 설정하기

  - 각 Item을 클릭했을 때 나타나는 이벤트 설정하기

    ```kotlin
    binding.myNavigation.run {
    	setOnNavigationItemSelectedListener {
    		when (it.itemId) {
    			binding.homeItem.id -> {
    				changeFragment(HomeFragment())
    			}
    			binding.searchItem.id -> {
    				changeFragment(SearchFragment())
    			}
    			binding.accountItem.id -> {
    				changeFragment(AccountFragment())
    			}
    		}
    		true
    	}
    	selectedItemId = binding.homeItem.id
    }

    fun changeFragment(fragment: Fragment) {
    	supportFragmentManager
    			.beginTransaction()
    			.replace(binding.mainContent.id, fragment)
    			.commit()
    }
    ```

  - BottomNavigationView의 주요 속성들을 정리해 주세요!
    [BottomNavigationView를 사용하려면 레이아웃에 추가를 해야합니다. 이 때 어떤 값들이 필수적으로 지정되어야 할까요?](https://www.notion.so/BottomNavigationView-111b57f4596b815c9542f65604bc450a?pvs=21)
    - 각 Item을 클릭했을 때 나타나는 이벤트 설정 방법은 꼭 정리하기 **[필수]**
      [각 Item을 클릭했을 때 나타나는 이벤트 설정하기](https://www.notion.so/Item-111b57f4596b813faea8e7cc444e4451?pvs=21)
