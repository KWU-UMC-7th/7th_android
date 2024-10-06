# Chapter 2 - Activity와 Fragment
## ⚡️Activity
- Activity란 무엇인가요?  
  : 안드로이드 애플리케이션의 구성 요소 중 하나로 사용자와 상호작용하는 UI를 제공, 각 Activity는 화면을 나타내며 사용자가 특정 작업을 수행할 수 있는 공간

- 새로운 Activity를 만들기 위해선 어떻게 해야 할까요?  
  : File > New > Activity > Empty Activity

- AppCompatActivity란 무엇인가요?  
  : 구형 기기에서도 최신 UI 기능을 지원하는 기본 Activity 클래스

## ⚡️Activity-Layout 결합
- findViewById  
  : XML 레이아웃 파일에서 정의된 View에 접근하기 위해 사용되는 메소드

- findViewById 사용법  
  : XML 레이아웃 파일에서 원하는 View의 id 속성을 지정 -> Activity의 onCreate 메소드 내에서 setContentView로 레이아웃을 설정한 후, findViewById를 사용하여 View에 접근  

- ViewBinding  
  : 안드로이드에서 View에 안전하게 접근할 수 있도록 돕는 기능, XML 레이아웃 파일에 대해 자동으로 생성된 바인딩 클래스를 사용하여 findViewById 대신 사용

- ViewBinding 사용법  
  : build.gradle 파일에 ViewBinding을 활성화 -> Activity에서 ViewBinding을 사용

- findViewById보다 ViewBinding이 권장되는 이유  
  : 전통적인 방식인 findViewById의 단점을 보완한 현대적인 접근 방식이기 때문

- findViewById의 단점  
  : 타입 캐스팅 필요, 런타임 오류, 많은 반복 코드

- ViewBinding의 장점  
  : 타입 안정성(자동 생성), NULL 안정성, 코드 간결성

## ⚡️새로운 Activity를 띄우는 방법
- Intent란 무엇일까요?  
  : 안드로이드에서 컴포넌트 간의 상호작용을 나타내는 메시지 객체, 이를 통해 한 Activity에서 다른 Activity를 시작하거나 서비스 및 브로드캐스트 수신자와 같은 다른 컴포넌트에 정보를 전달

- Intent를 사용하여 Activity 간 데이터를 전달하려면 어떻게 해야할까요?  
  : Intent에 추가 데이터를 putExtra() 메소드를 사용하여 저장하고, 수신 Activity에서는 getIntent()와 getExtras() 메소드를 사용하여 데이터를 읽어옴

- 명시적 Intent란 무엇일까요?  
  : 특정 컴포넌트를 명시적으로 지정하여 해당 컴포넌트를 시작하는 Intent, 보통 같은 애플리케이션 내의 다른 Activity를 시작할 때 사용  

- 암시적 Intent란 무엇일까요?  
  : 특정 컴포넌트를 명시하지 않고, 원하는 작업에 대한 정보를 포함하여 해당 작업을 수행할 수 있는 컴포넌트를 찾도록 시스템에 요청하는 Intent, 시스템은 해당 작업을 처리할 수 있는 모든 컴포넌트를 찾아 실행

- 두 Intent를 사용하는 예시에는 각각 무엇이 있을까요?  
  : (명시) 사용자가 버튼을 클릭하면 SecondActivity를 시작하는 경우, (암시) 웹사이트를 열기 위해 브라우저를 선택할 수 있게 하는 경우  

## ⚡️Fragment
- Fragment의 정의는 무엇일까요?  
  : 안드로이드 애플리케이션에서 UI의 일부를 나타내는 독립적인 모듈

- Fragment를 사용하는 이유는 무엇일까요?  
  : 재사용성, 유연한 UI, 독립적인 생명주기 관리, 백 스택 관리

- 새 Fragment는 어떻게 만들 수 있을까요?  
  : 새 Fragment 클래스 생성 -> 레이아웃 XML 파일 생성 -> Fragment에서 레이아웃 인플레이트

- Fragment는 어떻게 화면에 보이게 할 수 있을까요?  
  : Activity에서 FragmentTransaction을 사용하여 Fragment를 추가하거나 교체, 일반적으로 FragmentManager를 사용하여 Fragment를 관리

## ⚡️Bundle
- Bundle은 무엇일까요?  
  : 안드로이드에서 데이터를 키-값 쌍으로 저장할 수 있는 데이터 구조

- Intent와 Bundle을 결합하는 방법은 무엇일까요?  
  : Bundle 객체 생성 -> 데이터 추가 -> Intent에 Bundle 추가 -> 대상 Activity에서 데이터 추출  

- FragmentManager  
  : 안드로이드에서 Fragment의 추가, 제거, 대체 및 상태 관리를 담당하는 클래스, FragmentManager는 Fragment의 생명주기를 관리하고, FragmentTransaction을 통해 Fragment를 조작할 수 있는 API를 제공

- FragmentManager는 언제 사용해야 될까요?  
  : UI의 특정 부분을 동적으로 변경하고 싶을 때, 사용자가 앱의 UI에서 돌아갈 수 있는 기능을 제공하고 싶을 때, 여러 Fragment가 상호작용해야 할 때 등

## ⚡️BottomNavigationView란?
- BottomNavigationView란 무엇이고, 어떤 기능을 할까요?  
  : 안드로이드에서 하단에 위치하는 네비게이션 바로, 주로 3~5개의 주요 화면을 빠르게 이동할 수 있도록 하는 UI 컴포넌트

- BottomNavigationView가 사용된 예시에는 무엇이 있을까요?  
  : 소셜 네트워크 앱, 쇼핑 앱, 음악 스트리밍 서비스 등

## ⚡️BottomNavigationView의 구성 요소
- BottomNavigationView를 사용하려면 레이아웃에 추가를 해야합니다. 이 때 어떤 값들이 필수적으로 지정되어야 할까요?  
  : 아이템 메뉴, 레이아웃 속성, 아이템 색상, labelVisibilityMode, 아이콘 크기 및 스타일

- menu 태그는 무엇일까요?  
  : 안드로이드에서 메뉴 항목을 정의하는 데 사용되는 태그  

- item 태그는 무엇일까요?  
  : 메뉴 항목 하나를 정의하는 태그

- item 태그에 설정할 수 있는 항목에는 무엇이 있을까요?  
  : android:id, android:title, android:icon, android:orderInCategory, android:enabled, android:visible, android:showAsAction, android:onClick

- 왼쪽의 예시 화면에서 (A)와 (B)에 해당하는 각각의 알맞은 화면 구성 요소를 선택해주세요!  
  : (A) = Activity, (B) = Fragment

- 왼쪽 화면을 구성하기 위해서 일반적으로 몇 개의 Fragment가 필요한가요??  
  : 3개

## ⚡️BottomNavigationView 설정하기
- 각 Item을 클릭했을 때 나타나는 이벤트 설정하기  
  : setOnItemSelectedListener() 메서드를 사용하여 클릭 리스너를 설정

- BottomNavigationView의 주요 속성들을 정리해 주세요!  
  : app:menu, app:itemIconTint, app:itemTextColor, app:labelVisibilityMode, app:itemBackground, android:elevation, android:layout_gravity

## 📂실습 인증
워크북 페이지 내 동영상 첨부  
[Notion](https://www.notion.so/makeus-challenge/Chapter-2-Activity-Fragment-92cd7ae582a74a7eb7c0633975c9b40b?pvs=4)