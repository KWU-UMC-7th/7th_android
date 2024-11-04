> 과제는 `mission/w02basiclayout, mission/w04coroutine (branch:W04)` 을 참고해주세요

### 3주차 개발일지

> 결과 영상 및 수행항목 워크북 링크입니다

https://www.notion.so/makeus-challenge/Chapter-4-Thread-Coroutine-d806fb4a1c444c51a2376469443636c2

## 🎯 키워드 Essential

- Thread
  - Thread란 무엇일까요?
    프로세스 내에서 실행되는 작업의 단위 (코드의 실행 흐름).
    하나의 프로세스가 여러 작업을 병렬로 처리하기 위해 여러 개의 스레드를 가질 수 있는데, 보통 스레드는 공유 메모리 영역에서 독립적으로 실행되지만, 메모리(데이터)를 공유함.
  - Thread를 사용하는 예시는 무엇이 있을까요?
    웹서버: Nginx와 같이 다수의 사용자가 요청을 보낼 때 별도의 스레드를 생성하여 요청을 처리
    게임: 그래픽 랜더링, 사용자 입력, 네트워크 동기화 등 여러 작업을 병렬적으로 처리
    앱의 백그라운드 작업: 네트워크 요청, 데이터 다운로드 등 백그라운드에서 실행될 수 있는 작업
- Main Thread와 Worker Thread
  - View Control을 담당하는 Thread는 무엇일까요?
    앱에서 UI를 제어하고 업데이트하는 메인 스레드로, 지연되지 않고 빠르게 동작하도록 관리하는 것이 핵심
  - Worker Thread는 어떤 작업을 담당할까요?
    무거운 연산(큰 json 파일 역직렬화, 데이터 전처리 등), 네트워크 통신과 같이 UI 빌드를 대기하게 하는 요소를 처리
- Single Thread와 Multi Thread
  - Single-Thread란 무엇일까요?
    한번에 하나의 작업만 처리하는 기법으로, 작업이 순차적으로 실행됨.
    다만, 비동기 처리를 이용하여 코드의 실행 흐름을 제어할 수는 있으나, 무거운 동기 작업의 경우에는 사용자 경험이 떨어질 수 있음.
  - Multi-Thread란 무엇일까요?
    한번에 여러 작업을 병렬적으로 처리하는 기법으로, 작업이 비순차적으로 실행됨.
    사용자 경험은 극대되지만, 스레드간 동기화 문제나, 리소스를 많이 할당될 수 있기에, 작업에 노력이 필요함
- 동기와 비동기
  - 동기란 무엇일까요?
    여러 작업이 동일한 시간이나 순서에 맞게 실행되도록 조정하는 것.
  - 비동기란 무엇일까요?
    여러 작업이 실행할 때, 특정 작업의 완료를 대기하지 않고, 다른 작업을 동시에 진행할 수 있는 방법.
  - 동기와 비동기 각각의 장단점은 무엇이 있을까요?
    동기 작업의 경우 데이터를 추적하기 쉬워 일관성있게 유지하기가 쉽고, 동기화를 신경 쓸 필요가 없다. 하지만, 하나의 작업을 처리하기 위해 다른 모든 작업이 정지되기 때문에 응답성이 떨어진다.
    비동기 작업의 경우 병렬적으로 요청을 처리할 수 있기 때문에 대기 시간이 줄어들고, 리소스를 극한으로 활용할 수 있다. 하지만, 데이터의 변화 시점을 추적하기 까다롭고, 예외처리를 더욱 신경써야 하기 때문에 개발 난이도가 높다.
  - 동기와 비동기를 사용하는 예시에는 무엇이 있을까요?
    동기 - DB 트랜젝션, 파일 I/O, 데이터 처리
    비동기 - API 호출, 타이머, 이벤트 처리
- Handler
  - Android에서 Handler란 무엇일까요?
    스레드간 메세지 전당 및 작업 실행을 관리하는 클래스로, 주로 메인(UI)스레드에서 작업을 처리하기 위해 사용.
  - Handler를 사용하는 이유는 무엇일까요?
    메인 스레드와 워커 스레드간 안전한 통신과 비동기 작업 처리를 효과적으로 수행하기 위해 사용함.
    - 워커 스레드에서 UI를 업데이트 할 수 없기에 handler로 업데이트 요청
    - 비동기 처리의 결과를 메인 스레드로 전달
    - 지연 작업을 메세지 큐에 등록하여 작업을 예약
    - 워커 스레드간 통신
  - Handler의 Message란 무엇일까요?
    안드로이드에서 스레드 간 통신을 위해 사용하는 데이터구조.
    ```kotlin
    // 생성
    Message message = handler.obtainMessage();
    message.what = 1; // 작업 유형 설정
    message.obj = data; // 추가 데이터 설정
    ```
    ```kotlin
    // 전달
    handler.sendMessage(message);
    ```
    ```kotlin
    // 수신
    @Override
    public void handleMessage(Message msg) {
        switch (msg.what) {
            case 1:
                // 메시지에 따라 작업 수행
                Object data = msg.obj; // 전달된 데이터
                break;
            // 다른 case 문
        }
    }
    ```
  - Handler를 사용하는 예시에는 무엇이 있을까요?
    UI 업데이트, 지연 실행, 반복 작업, 메세지 전송, 스레드 간 상태 전달 등
- Looper
  - Android에서 Looper란 무엇일까요?
    스레드와 관련된 메세지 큐를 관리하는 클래스.
    여러개의 메세지를 처리하기 위해 들어오는 메세지는 큐에 저장되며, 루퍼가 동작할 때 마다 메세지를 하나씩 꺼내어 처리하는 방식.
  - Looper를 활용하는 예시는 무엇이 있을까요?
    UI 업데이트, 정기적인 작업 실행 (핸들러와 같이 사용되는 듯)
- Coroutine
  - Coroutine이란 무엇일까요?
    비동기 프로그래밍을 간편하게 처리할 수 있도록 지원하는 구조.
    일반적인 스레드와 달리 코루틴은 경량화된 실행단위와 함께 자체 메커니즘을 제공.
  - Coroutine은 언제 사용할까요?
    ```kotlin
    // 비동기 작업 처리
    GlobalScope.launch {
        val result = fetchDataFromApi()
        // UI 업데이트는 메인 스레드에서 해야 함
        withContext(Dispatchers.Main) {
            updateUI(result)
        }
    }
    ```
    ```kotlin
    // UI 업데이트
    launch(Dispatchers.Main) {
        val data = fetchData()
        updateUI(data)
    }
    ```
    ```kotlin
    // 타이머 (주기적인 작업)
    launch {
        while (true) {
            // 작업 수행
            delay(1000) // 1초 간격
            performPeriodicTask()
        }
    }
    ```
    ```kotlin
    // 병렬 작업 및 동기화
    val result1 = async { fetchDataFromApi1() }
    val result2 = async { fetchDataFromApi2() }

    // 두 작업의 결과를 동시에 기다림
    val combinedResult = result1.await() + result2.await()
    ```
    ```kotlin
    // 연쇄적 비동기 작업
    launch {
        val step1 = performStep1()
        val step2 = performStep2(step1)
        val result = performStep3(step2)
        updateUI(result)
    }
    ```
  - Coroutine의 Dispatcher란 무엇일까요?
    코루틴의 실행 컨텍스트를 지정하는 요소로, 코루틴이 어떤 스레드에서 실행될지를 결정.
    디스패쳐는 스레드 풀을 관리하며 코루틴의 작업을 적절한 스레드에서 수행할 수 있도록 함.
  - Dispatcher의 종류에는 무엇이 있을까요?
    - Dispatchers.Main: UI 작업을 처리하기 위한 디스패쳐, 메인 스레드에서 코루틴을 사용할 때 사용.
    - Dispatchers.IO: 파일 입출력, 네트워크 요청에 최적화된 디스패쳐.
    - Dispatchers.Default: CPU의 집약적인 작업을 처리하기 위한 디스패쳐, 스레드 수가 CPU 코어 수에 맞게 자동으로 조정되며, 계산이나 데이터 처리화 같은 CPU 사용량이 많은 작업을 처리.
    - Dispatchers.Unconfined: 특정 스레드에 국한되지 않는 경량 작업을 처리.
