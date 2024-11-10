> 과제는 7주차 mission 에 서브모듈로 달아두겠습니다.

### 6주차 개발일지

> 수행항목 워크북 링크입니다
> https://www.notion.so/makeus-challenge/Chapter-6-RecyclerView-Adapter-c7f7f3d0fadf42a985d3bdbe929e542b

## 🎯 키워드 Essential

- ListView
  - ListView란 무엇일까요?
    리스트 형식으로 데이터를 표시할 때 사용하는 UI 컴포넌트
  - ListView에 들어갈 아이템들은 어떻게 저장해야 할까요?
    ArrayList, List, Array 와 같은 컬렉션을 이용하여 데이터를 저장하고, 이를 Adapter에 연결하여 리스트 뷰에 표시
  - ListView는 어떤 구성요소로 되어있을까요?
    - ListView: UI 컴포넌트
    - Adapter: 리스트 뷰에 표시될 데이터를 제공하며, 데이터를 뷰로 변환해주는 역할을 수행. (`ArrayAdapter`, `CustomAdapter` )
    - View (Item Layout): 각 아이템에 해당하는 개별 뷰
    - ViewHolder 패턴: 뷰를 재사용하고 성능 개선을 위해, 각 아이템 뷰의 구성요소를 한 번만 찾아 저장해두고 재사용하는 패턴
- Adapter
  - Android에서 사용되는 Adapter란 무엇일까요?
    데이터와 UI 컴포넌트를 연결하는 역할을 수행하는 중간 매개체
  - Adapter는 주로 어떤 역할을 할까요?
    - 데이터 공급: 데이터를 관리하고, 각 아이템을 화면에 표시할 수 있는 형식으로 변환
    - 아이템 생성 및 배치: 데이터를 UI 요소로 변환하여 화면에 배치
    - 재사용 최적화: 스크롤 시 뷰를 재사용하여 메모리 사용량 최적화
  - ListView의 Adapter는 어떤 구성 요소를 가지고 있을까요?
    - 데이터 소스: 어댑터에 전달되는 데이터로 리스트 형식의 데이터 컬렉션 형식
    - getView: 리스트 뷰의 각 아이템을 위한 뷰를 반환하는 메서드
    - getCount: 어댑터에 있는 아이템 항목의 총 개수를 반환하는 메서드
    - getItem: 특정 위치의 데이터를 반환하는 메서드
    - getItemId: 각 아이템의 고유 ID를 반환하는 메서드
    - ViewHolder 패턴: 스크롤 성능 최적화를 위해 뷰를 재사용하는 패턴
- RecyclerView
  - RecyclerView란 무엇일까요?
    스크롤 가능한 대량의 데이터를 효율적으로 화면에 표시하기 위해 설계된 UI 컴포넌트
  - RecyclerView와 ListView는 어떤 차이점이 있을까요?
    위에서 언급했던 재사용을 위한 ViewHolder 패턴이 기본적으로 내장되어 있음.
    또한, 다양한 레이아웃 배치를 지원하고 애니메이션 및 데코레이션도 편하게 적용할 수 있음.
  - RecyclerView Adapter는 어떤 구성 요소를 가지고 있을까요?
    - ViewHolder 클래스: 개별 아이템 뷰에 대한 참조를 유지하는 역할을 하는 내부 클래스 (재사용을 위한)
    - onCreateViewHolder: 새로운 ViewHolder 객체를 생성하는 메서드
    - onBindViewHolder: 특정 위치의 데이터를 ViewHolder에 바인딩하는 메서드
    - getItemCount: 리사이클러 뷰의 총 아이템 개수를 반환하는 메서드
    - 데이터 소스: 어댑터에 의해 전달되는 데이터
  - RecyclerView를 설정할 때 주의해야 하는 점은 무엇이 있을까요?
    뷰를 재활용하기 때문에 ViewHolder를 올바르게 구현해야 하며,
    특정 위치(화면에 보이는)의 데이터만 갱신하여 성능 최적화를 해야 한다. (notifyDataSetChanged() 대신 notifyItemInserted, Removed, Changed() 를 사용)
  - ViewPager2 에서 사용했던 FragmentStateAdapter와 RecyclerView.Adapter는 어떤 차이가 있을까요?
    기본적으로 관리 대상이 Fragment 인지, View 인지에 차이가 있음.
    그에 따라 생명 주기 관리 방식, 재사용 여부와 같은 내부 로직도 완전히 다름.
- foreground service
  - foreground service란 무엇일까요?
    사용자가 명확하게 인식할 수 있는 방식으로 실행되는 서비스로, 일반적으로 Notification을 통해 알려줘야 함. (음악재생, 위치 추적, 업/다운로드 등)
  - foreground service를 사용하는 이유는 무엇일까요?
    운영체제에 의해 강제적으로 서비스가 종료될 확률이 늦으며, 사용자가 앱을 종료하더라도 서비스가 계속 백그라운드에서 작업을 실행할 수 있음.
  - foreground service 사용 시 주의사항은 무엇이 있을까요?
    Notification을 필수로 사용해야 하며, 베터리와 메모리 및 리소스 관리에 신경써야 함.
- background service
  - background service란 무엇일까요?
    사용자가 앱을 사용하지 않더라도 앱 내에서 지속적으로 실행되는 서비스로, 알림도 필요없음. (데이터 동기화, 위치 추적, 업/다운로드 등)
  - background service를 사용하는 이유는 무엇일까요?
    사용자가 인식할 수 없는 곳에서 장기적/정기적으로 실행되어야 할 작업을 앱이 종료된 상태에서도 수행할 수 있기 때문.
  - background service 사용 시 주의사항은 무엇이 있을까요?
    베터리와 메모리 및 리소스 관리에 신경써야 하며, 사용자 권한에 따른 사용 제한과 운영체제에 의해 서비스가 종료될 수 있다는 점을 고려해야 함.
