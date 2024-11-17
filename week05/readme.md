- Lifecycle
    - Lifecycle이란 무엇일까요?
    
    한글로 생명주기라 부름, 특정한 순서대로 실행되는 함수들을 지칭
    
    - Lifecycle은 왜 등장하게 되었을까요?
    
    작은 디스플레이에 의해 생겼다.
    
    이벤트 발생에 의한 화면 전환 발생 시 기존의 프로세스를 일시중지하는 등의 작업이 필요했기 때문
    
- Activity의 Lifecycle
    - Activity의 대표적인 Lifecycle은 어떤게 있을까요?
    
    생성 → onCreate → onStart → onResume → 액티비티 실행 → onPause → onStop → onDestroy → 액티비티 소멸
    
    이 외에도 onRestart 등 존재
    
    - 각 Lifecycle을 활용하는 실제 예시들은 어떤게 있을까요?
    
    onCreate : FPS 게임에서 총알생성 시 앞으로 직진하는 속도 초기화를 실행
    
    onStart : UI 관리 코드 초기화
    
    onResume : 다른 화면에서 전환됐을 때 일시정지에서 풀리는 화면
    
    onPause : 다른 화면으로 일시적으로 전환될 때 일시정지 화면
    
    onStop : 다른 이벤트로 아예 전환될 때 생기는 화면, 보통 DB 저장
    
    onDestroy : FPS 게임에서 총알 소멸
    
- MediaPlayer
    - MediaPlayer는 언제 사용할까요?
    
    음악을 재생하고 싶을 때
    
    - MediaPlayer에서 사용할 수 있는 함수들은 무엇이 있으며, 어떤 기능을할까요? (ex create, pause, …)
    
    create : 음성파일 객체 생성
    
    start(): 재생 시작
    
    stop(): 정지
    
    prepare(): 준비
    
    pause(): 일시 정지
    
    release(): 메모리 해제
    
    seekTo(): 재생 위치 지정
    
    getCurrentPosition(): 재생 위치
    
    getDuration(): 재생 시간
    
    getVideoHeight():영상 높이값
    
    getVideoWidth():영상 너비값
    
    setLooping():반복 설정
    
    setVolumn():볼륨 설정
    
- SharedPreferences
    - SharedPreference란 무엇일까요?
    
    간단한 값을 앱이 꺼져도 내부 저장소에 저장하는 것
    
    - SharedPreference는 어떤 방식으로 값을 저장할까요?
    
    ```kotlin
    // (방식1) Intent 를 통하여 전달하는 방식
                i.putExtra("name",name);
                i.putExtra("age",age);
                i.putExtra("b_day",b_day);
    
    ```
    
    ```java
    // (방식2) Bundle 를 통하여 전달하는 방식 (현업에서는 bundle방식 선호, 하지만 큰차이는 없음.)
    
                Bundle bundle = new Bundle();
                bundle.putString("name",name);
                bundle.putString("age",age);
                bundle.putString("b_day",b_day);
    ```
    
    - JSON과 GSON이란 무엇일까요?
    
    JSON : 데이터 format의 일종
    
    GSON : 자바객체 ↔ JSON format 변형하게 해주는 라이브러리


    실습
    https://github.com/sojung0628/android_flo/tree/main