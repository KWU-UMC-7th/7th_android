> 과제는 `mission/udemy_android_flo, mission/w05lifecycle (branch:W05)` 을 참고해주세요

### 5주차 개발일지

> 결과 영상 및 수행항목 워크북 링크입니다
> https://www.notion.so/makeus-challenge/Chapter-5-LifeCycle-6c85b97b1506402d9474581d5a4bab2d

## 🎯 키워드 Essential

- Lifecycle
  - Lifecycle이란 무엇일까요?
    객체나 컴포넌트가 생성되고 소멸되는 과정을 정의하는 일련의 상태와 이벤트를 나타냄.
  - Lifecycle은 왜 등장하게 되었을까요?
    안드로이드 앱에서 복잡한 생명주기를 단순화하고, 리소스 관리 및 사용자 경험을 향상시키기 위함.
    이에 대한 배경으로 다양한 화면 전환, 사용자 인터렉션, 시스템 리소스 상태 변화 등 여러 복합적인 요소의 고도화에 있음.
- Activity의 Lifecycle
  - Activity의 대표적인 Lifecycle은 어떤게 있을까요?
    - onCreate: 액티비티가 생성될 때 호출 - 레이아웃 설정이냐 뷰 요소를 초기화, 리소스 준비 등
    - onStart: 액티비티가 사용자에게 보일 때 호출. 단, 상호작용은 불가
    - onResume: 액티비티가 활성화되어 사용자와 상호작용이 가능할 때 호출 - 사용자 입력 수신, 애니메이션과 같은 UI 관련 작업
    - onPause: 다른 액티비티가 포커스를 가질 때 호출. 호출된 액티비티는 이 시점을 기해 상호작용 불가
    - onStop: 다른 액티비티가 앞에 나와 가릴 때 호출. 호출된 액티비티는 이 시점을 기해 UI로 그려지지 않고 일부 리소스가 해제됨
    - onRestart: onStop 이후 onStart가 호출되기 전에 호출. 액티비티 재 실행 전에 필요한 사전 준비
    - onDestroy: 액티비티가 완전히 소멸할 때 호출. 메모리 누수 방지를 위한 로직 수행
  - 각 Lifecycle을 활용하는 실제 예시들은 어떤게 있을까요?
    ```kotlin
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        // UI 요소 초기화
        val myButton: Button = findViewById(R.id.my_button)
        myButton.setOnClickListener {
            // 버튼 클릭 이벤트 처리
        }
        // 데이터 로딩
        loadData()
    }
    ```
    ```kotlin
    override fun onStart() {
        super.onStart()
        // Activity가 시작될 때 필요한 작업
        // 예: 시작 상태에 따라 UI 업데이트
        updateUI()
    }
    ```
    ```kotlin
    override fun onResume() {
        super.onResume()
        // UI와 관련된 업데이트 및 애니메이션 시작
        startAnimation()
        // 사용자 입력 수신 준비
        enableUserInput()
    }
    ```
    ```kotlin
    override fun onPause() {
        super.onPause()
        // UI 업데이트 중지
        stopAnimation()
        // 현재 데이터 저장
        saveCurrentState()
    }
    ```
    ```kotlin
    override fun onStop() {
        super.onStop()
        // 데이터베이스 연결 해제
        database.close()
        // 백그라운드 작업 중지
        stopLongRunningTask()
    }
    ```
    ```kotlin
    override fun onRestart() {
        super.onRestart()
        // Activity가 다시 시작될 때 필요한 작업
        // 예: 데이터 새로고침
        refreshData()
    }
    ```
    ```kotlin
    override fun onDestroy() {
        super.onDestroy()
        // 메모리 누수를 방지하기 위한 정리 작업
        releaseResources()
        // 종료 시 알림 또는 로그 기록
        Log.d("ActivityLifecycle", "Activity destroyed")
    }
    ```
- MediaPlayer
  - MediaPlayer는 언제 사용할까요?
    안드로이드에서 오디오 및 비디오 콘텐츠를 재생하는데 사용하는 클래스.
  - MediaPlayer에서 사용할 수 있는 함수들은 무엇이 있으며, 어떤 기능을할까요? (ex create, pause, …)
    ```kotlin
    // 오디오 재생
    val mediaPlayer = MediaPlayer.create(this, R.raw.sample_music)
    mediaPlayer.start()
    mediaPlayer.pause() // 일시 정지
    mediaPlayer.seekTo(position) // 특정 위치로 이동
    ```
    ```kotlin
    // 비디오 재생
    val mediaPlayer = MediaPlayer.create(this, R.raw.sample_video)
    mediaPlayer.start()
    ```
    ```kotlin
    // 스트리밍 콘텐츠 재생
    val mediaPlayer = MediaPlayer()
    mediaPlayer.setDataSource("https://example.com/audio/stream")
    mediaPlayer.prepareAsync()
    mediaPlayer.setOnPreparedListener {
        mediaPlayer.start()
    }
    ```
- SharedPreferences
  - SharedPreference란 무엇일까요?
    안드로이드에서 간단한 데이터를 저장하고 관리하는 방법을 제공하는 클래스.
  - SharedPreference는 어떤 방식으로 값을 저장할까요?
    앱 설정, 사용자 정보, 상태 등 작은 데이터 파일을 Key-Value 형식으로 저장.
  - JSON과 GSON이란 무엇일까요?
    JSON: JavaScript Object Notation - 데이터를 구조화한 형식으로 사람이 읽기 쉬우며 기계도 파악하기 쉬운 텍스트 기반 포멧으로, 보통 클라이언트와 서버간 통신에서 사용됨.
    GSON: Google’s JSON - 구글에서 제공하는 자바 라이브러리로, json 데이터와 자바 객체간 직렬화 및 역직렬화 하는 기능을 제공.
