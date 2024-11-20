# Chapter 6 - RecyclerView & Adapter
## ⚡️ListView
- ListView란 무엇일까요?  
  : 여러 개의 데이터를 스크롤 가능한 목록 형태로 표시하는 UI 컴포넌트

- ListView에 들어갈 아이템들은 어떻게 저장해야 할까요?  
  : 데이터 소스를 받아서 ListView의 각 항목을 View로 변환하여 화면에 표시하는 Adapter를 통해 관리

- ListView는 어떤 구성요소로 되어있을까요?  
  : ListView, Adapter, Item Layout

## ⚡️Adapter
- Android에서 사용되는 Adapter란 무엇일까요?  
  : UI 컴포넌트와 데이터 소스를 연결하는 중간 역할을 하는 객체

- Adapter는 주로 어떤 역할을 할까요?  
  : 데이터 변환, 아이템 View 관리

- ListView의 Adapter는 어떤 구성 요소를 가지고 있을까요?  
  : 데이터 소스, getView() 메서드, Item Layout

## ⚡️RecyclerView
- RecyclerView란 무엇일까요?  
  : 대용량 데이터를 효율적으로 화면에 표시하기 위해 사용되는 뷰 그룹, 재사용 가능한 리스트 아이템 뷰와 Layout Manager를 통해 스크롤 성능을 최적화

- RecyclerView와 ListView는 어떤 차이점이 있을까요?  
  - ListView : 레이아웃 옵션이 세로 방향으로 제한적이고, 기본적으로 애니메이션을 제공하지 않음
  - RecyclerView : 다양한 레이아웃 옵션과 디폴트 애니메이션 및 사용자 정의 애니메이션을 지원함

- RecyclerView Adapter는 어떤 구성 요소를 가지고 있을까요?  
  : ViewHolder, onCreateViewHolder(), onBindViewHolder(), getItemCount()

- RecyclerView를 설정할 때 주의해야 하는 점은 무엇이 있을까요?  
  : ViewHolder 패턴을 활용하여 메모리를 절약하고 성능을 최적화, Layout Manager를 설정하여 데이터가 표시될 방식을 명확하게 정의

- ViewPager2 에서 사용했던 FragmentStateAdapter와 RecyclerView.Adapter는 어떤 차이가 있을까요?  
  - FragmentStateAdapter : 프래그먼트를 관리하는 뷰페이저로 프래그먼트의 생성과 상태를 자동으로 관리
  - RecyclerView.Adapter : 데이터 목록을 관리하는 리스트로 직접 ViewHolder 생성 및 해제 관리

## ⚡️foreground service
- foreground service란 무엇일까요?  
  : 사용자가 인식할 수 있는 방식으로 실행되는 서비스

- foreground service를 사용하는 이유는 무엇일까요?  
  : 음악 재생, 운동 기록 등과 같이 사용자가 명확히 알고 있어야 하는 오래 실행되는 작업을 위해 사용

- foreground service 사용 시 주의사항은 무엇이 있을까요?  
  : 알림 필수 제공, 백그라운드 작업 제한

## ⚡️background service
- background service란 무엇일까요?  
  : 사용자가 직접 앱을 사용하지 않아도 백그라운드에서 특정 작업을 수행하는 서비스

- background service를 사용하는 이유는 무엇일까요?  
  : 데이터 동기화 및 업데이트, 주기적인 데이터 수집

- background service 사용 시 주의사항은 무엇이 있을까요?  
  : 배터리 최적화 제한, 작업 주기 및 간격 최적화

## 📂실습 인증
강의 섹션 7까지 진행
[Github](https://github.com/MunJeongEun/practice-7th-android.git)