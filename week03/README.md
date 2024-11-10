> 과제는 `mission/w02basiclayout (branch:W03)` 을 참고해주세요

### 3주차 개발일지

> 결과 영상 및 수행항목 워크북 링크입니다

https://www.notion.so/makeus-challenge/Chapter-3-Essential-Widget-Compilation-9bb24f1577c143178d52dc196dd68e34

### 🎯 키워드 Essential

- TabLayout
  - TabLayout이란 무엇이고, 어떤 기능을 할까요?
    안드로이드에서 제공하는 UI 컴포넌트로, Tab 인터페이스를 구현하는데 사용됨.
    주요 기능으로 각 탭을 클릭하면 화면을 전환할 수 있는 기능을 제공하는데, 전환되는 화면으로 보통 ViewPager와 연동하여 화면이 전환된다.
    또한 탭의 아이템으로 텍스트 뿐 만 아니라, 아이콘도 등록하여 사용자가 직관적으로 항목을 인식하게 할 수 있다.
  - TabLayout이 사용된 예시에는 무엇이 있을까요?
    유튜브에서 채널의 콘텐츠를 모아볼 수 있게 하는 탭이 제공된다. (홈/동영상/Shorts/재생목록 등)
    삼성 뮤직에서 음악들을 모아볼 수 있게 해주는 기준을 제공하는 탭이 제공된다. (플레이리스트/곡/앨범/아티스트 등)
  - TabLayout에서 사용할 수 있는 속성들은 무엇이 있을까요?
    - `app:tabMode` 탭이 고정되거나 스크롤 가능한지 설정 (`fixed`, `scrollable` )
    - `app:tabGravity` 탭의 정렬 방식 설정 (`fill`, `center` )
    - `app:tabTextColor` 탭의 기본 텍스트 색상 설정
    - `app:tabSelectedTextColor` 선택된 텍스트 색상 설정
    - `app:tabIndicatorColor` 탭 인디케이터의 색상 설정
    - `app:tabIndicatorHeight` 탭 인디케이터의 높이 설정
    - `app:tabRippleColor` 탭 클릭 효과의 색상 설정
    - `app:tabIndicatorFullWidth` 탭 인디케이터의 가로길이 확장 여부 설정
    - `app:tabIndicatorPadding` 탭 인디케이터의 패딩(가로길이 내부 여백) 설정
- ViewPager2
  - ViewPager란 무엇이고, 어떤 기능을 할까요?
    안드로이드에서 여러 화면을 좌우로 스와이프하여 전환할 수 있도록 도와주는 화면 전환을 위한 뷰.
    TabLayout과 연동하여 사용할 수도 있음.
  - ViewPager가 사용된 예시에는 무엇이 있을까요?
    구글 플레이 스토어 홈 화면에서 앱을 가로로 소개하는 뷰
    유튜브 채널 뷰에서 여러 탭의 하단에서 가로로 스와이프 할 수 있는 뷰
    캘린더에서 달력을 가로로 스와이프 할 수 있는 뷰
  - ViewPager와 ViewPager2의 차이는 무엇일까요?
    ViewPager는 PageAdapter를 기반으로 동작하지만, ViewPager2는 RecyclerView를 기반으로 동작함.
    이에 따라 상태관리 측면에서 개선이 이루어졌고, 더 다양한 기능을 제공함. 예로 들어 수직 스와이프를 지원하거나, 페이지 전환 애니메이션을 커스텀하기 편해졌음.
    뿐만 아니라, RTL과 Nested Scroll을 완벽 지원하기에 사용자 경험 측면에서 좋아짐.
  - ViewPager2에서 사용할 수 있는 속성들은 무엇이 있을까요?
    - `android:orientation` 페이지 스크롤 방향 설정 (`horizontal`, `vertical` )
    - `app:offscreenPageLimit` 미리 로드할 주변 페이지의 수를 결정
    - `app:pageMargin` 페이지 간 간격 설정
    - `app:isUserInputEnabled` 스와이프 사용여부 설정
- ViewPager2 설정하기
  - ViewPager2를 이용하기 위해 어떤 라이브러리를 사용해야 할까요
    `"androidx.viewpager2:viewpager2:1.1.0"`
    - XML에 들어가야 하는 속성도 작성
      ```xml
      <androidx.viewpager2.widget.ViewPager2
          android:id="@+id/viewPager"
          android:layout_width="match_parent"
          android:layout_height="match_parent" />
      ```
  - ViewPager2에서 FragmentStateAdapter는 무엇이고 어떤 기능을 할까요?
    여러개의 Fragment를 동적으로 관리하고, 페이지 전환을 처리하는데 도움을 줌.
    페이지의 상태를 저장하고 복원하는 기능을 제공함.
    이를 위해 어댑터 클래스를 상속하여 작성할 때, `getItemCount`, `createFragment` 를 오버라이드 해야함.
- ViewPager2 Indicator 설정하기

  - Indicator란 무엇이고, 어떤 역할을 할까요?
    UI에서 현재의 상태나 진행상황을 시각적으로 나타태는 요소로, ViewPager와 함께 사용할 경우 사용자가 보고있는 현재 페이지와 전체 페이지 수를 인식할 수 있도록 도와줌.
  - ViewPager2에서 Indicator를 설정하려면 어떻게 해야할까요?’
    `TabLayoutMediator` 를 사용.

    ```kotlin
    class MainActivity : AppCompatActivity() {

        override fun onCreate(savedInstanceState: Bundle?) {
    		    ...

            val adapter = MyFragmentStateAdapter(this)
            viewPager.adapter = adapter

            // ViewPager2와 TabLayout(Indicator)을 연결
            TabLayoutMediator(tabLayout, viewPager) { tab, position ->
                tab.text = "Page ${position + 1}"  // 각 탭에 표시할 텍스트 설정
            }.attach()
        }
    }
    ```
