# Chapter 3 - LifeCycle
## ⚡️Lifecycle
- Lifecycle이란 무엇일까요?  
  : Activity나 Fragment가 생성부터 종료까지 겪는 상태 변화의 주기

- Lifecycle은 왜 등장하게 되었을까요?  
  : 효율적인 자원 관리, 상태 유지와 복원, 비동기 작업 관리

## ⚡️Activity의 Lifecycle
- Activity의 대표적인 Lifecycle은 어떤게 있을까요?  
  - onCreate() : Activity가 처음 생성될 때 호출
  - onStart() : Activity가 화면에 표시될 준비가 되면 호출
  - onResume() : Activity가 사용자와 상호작용을 시작할 준비가 되면 호출
  - onPause() : Activity가 일부 가려지거나, 다른 Activity가 올라올 때 호출
  - onStop() : Activity가 완전히 화면에서 사라질 때 호출
  - onDestroy() : Activity가 완전히 종료되기 전에 호출

- 각 Lifecycle을 활용하는 실제 예시들은 어떤게 있을까요?  
  : 전화를 받을 때 게임 앱의 해당 콜백 메소드가 호출되어 게임의 진행 상태를 저장

## ⚡️MediaPlayer
- MediaPlayer는 언제 사용할까요?  
  : 음악 및 비디오 재생, 스트리밍 재생

- MediaPlayer에서 사용할 수 있는 함수들은 무엇이 있으며, 어떤 기능을할까요? (ex create, pause, …)  
  - create() : MediaPlayer 객체를 생성하여 사용할 리소스를 초기화
  - start() : 재생 시작
  - pause() : 재생 일시 중지
  - stop() : 재생 중지
  - release() : MediaPlayer가 사용하는 리소스를 해제하고 객체를 완전히 제거
  - reset() : MediaPlayer 객체를 초기 상태로 재설정
  - isPlaying() : MediaPlayer가 재생 중인지 여부를 반환

## ⚡️SharedPreferences
- SharedPreference란 무엇일까요?  
  : 간단한 데이터를 영구적으로 저장하기 위해 제공하는 경량의 저장소, 앱이 종료된 후에도 데이터를 유지하므로 로그인 정보, 설정값, 사용자 선호도 등의 정보를 저장하기에 적합

- SharedPreference는 어떤 방식으로 값을 저장할까요?  
  : 데이터를 내부적으로 XML 파일 형태와 key-value 쌍으로 저장

- JSON과 GSON이란 무엇일까요?  
  - JSON : 데이터를 교환하기 위해 널리 사용되는 경량의 데이터 형식
  - GSON : Google에서 만든 JSON 파싱 및 변환 라이브러리로, JSON 데이터를 자바 객체로 변환

## 📂실습 인증
강의 섹션 6까지 진행
[Github](https://github.com/MunJeongEun/practice-7th-android.git)