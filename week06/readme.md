- ListView
    - ListView란 무엇일까요?
        - 리스트 형태의 데이터를 보여주는 위젯
    - ListView에 들어갈 아이템들은 어떻게 저장해야 할까요?
        - List, ArrayList 등 List 자료구조에 저장해야 함
    - ListView는 어떤 구성요소로 되어있을까요?
        - 리스트 아이템을 구성하는 layout, Data, Adapter
- Adapter
    - Android에서 사용되는 Adapter란 무엇일까요?
        - 데이터 테이블을 목록 형태로 보여주기 위해 사용되는 것으로 데이터를 다양한 형식의 리스트 형식을 보여주기 위해서 데이터와 리스트 뷰 사이에 존재하는 객체이다.
    - Adapter는 주로 어떤 역할을 할까요?
        - 데이터와 리스트 뷰 사이의 통신을 위한 다리 역할을 한다.
    - ListView의 Adapter는 어떤 구성 요소를 가지고 있을까요?
        - ArrayAdapter(Context context, int resource, T[] objects)
            - context : 안드로이드 시스템에서 제공되는 어플리케이션 전역 환경 정보에 대한 인터페이스
            - resource : View로 매핑될 Resource Id "android.R.layout.simple_list_item_1"은 TextView 위젯으로 구성된 ListView 아이템 리소스 Id
            - objects : 배열로 선언된 데이터
- RecyclerView
    - RecyclerView란 무엇일까요?
        - 수많은 데이터의 집합을 지정된 영역 내에서 유연하게 표시되도록 만들어주는 위젯
    - RecyclerView와 ListView는 어떤 차이점이 있을까요?
        - ListView
            - 아래로 스크롤 하는 경우 제일 위의 아이템이 안보이게 되면, 해당 아이템을 삭제하고 가장 아래에 새로운 아이템을 추가
            - 수직 방향으로만 구현 가능 (수평도 가능하지만 ListView 재구현 해야함)
        - RecyclerView
            - 아이템이 화면에서 사라진 경우 View를 재활용하여 맨 밑으로 옮긴다. 즉 View 객체를 재생성하지 않는다.
            - 다양한 layout 지원 (수직, 수평, grid 등등..)
    - RecyclerView Adapter는 어떤 구성 요소를 가지고 있을까요?
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/1769b850-18f1-4af9-911c-db4c98fee449/Untitled.png)
        
    - RecyclerView를 설정할 때 주의해야 하는 점은 무엇이 있을까요?
    - ViewPager2 에서 사용했던 FragmentStateAdapter와 RecyclerView.Adapter는 어떤 차이가 있을까요?
        - FragmentStateAdapter는 기본적으로 ReyclerView.Adapter를 상속하고 있어서 기본적인 ViewHolder 패턴은 같음. 또한 RecyclerView.Adapter에 있는 추상 메서드를 하위 클래스에서 오버라이딩 해야 함.
        - 하지만  RecyclerView.Adapter의onCreateViewHolder(), onBindViewHolder()뿐만 아니라 RecyclerView.Adapter에 정의된 여러 콜백함수인 onViewRecycled(리사이클러뷰가 재활용할 ViewHolder를 가져온 시점에 콜백), onAttachedToWindow(아이템 뷰를 리사이클러뷰에 attach한 시점에 호출되는 콜백)등을 FragmentStateAdapter가 직접 오버라이딩하고 있기 때문에 따로 오버라이딩 할 필요가 없음.
- foreground service
    
    Service → 사용자 인터페이스(UI) 없이 앱의 백그라운드에서 긴 시간이 걸리는 작업을 수행하는 컴포넌트 (Android 4대 컴포넌트 중 하나)
    
    - foreground service란 무엇일까요?
        - 포그라운드 서비스는 [상태 표시줄 알림](https://developer.android.com/develop/ui/views/notifications?hl=ko)을 표시하여 앱이 포그라운드에서 작업을 실행하고 시스템 리소스를 소비하고 있음을 사용자에게 알림.
        - 한 마디로 서비스의 동작을 사용자가 인지할 수 있음
    - foreground service를 사용하는 이유는 무엇일까요?
        - 사용자가 앱과 직접 상호작용하지 않을 때도 앱에서 사용자가 인지할 수 있는 작업을 실행해야 할 때만 포그라운드 서비스를 사용.
        - 활성화된 액티비티와 동급의 우선순위를 갖기 때문에 시스템에 의해 종료되지 않음
    - foreground service 사용 시 주의사항은 무엇이 있을까요?
        - 사용자가 서비스의 동작을 인지할 수 있도록 반드시 알림을 제공해야 함
- background service
    - background service란 무엇일까요?
        - 사용자에게 보이지 않고 묵시적으로 실행
    - background service를 사용하는 이유는 무엇일까요?
        - 백그라운드에서 실행되지만 유저에게 특별히 진행상황이나 결과에 대한 메세지를 전달할 필요가 없는 경우에 사용
    - background service 사용 시 주의사항은 무엇이 있을까요?
        - 백그라운드에서 돌고있는 앱이 시스템의 리소스를 많이 잡아먹으면 유저가 다른 앱을 사용하고 있을 때도 좋지못한 사용자 경험을 제공할 수 있기 때문에 시스템에 의해 종료될 가능성이 있음


    실습
    https://github.com/sojung0628/android_flo/tree/main