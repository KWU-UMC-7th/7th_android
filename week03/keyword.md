# Chapter 3 - Essential Widget Compilation
## ⚡️TabLayout
- TabLayout이란 무엇이고, 어떤 기능을 할까요?  
  : 화면에 탭을 표시하는 UI 구성 요소로, 여러 페이지를 탭으로 구분하여 사용자가 손쉽게 페이지를 전환할 수 있도록 도와줌  
  : 탭 관리, ViewPager와의 연동, 커스터마이즈 기능

- TabLayout이 사용된 예시에는 무엇이 있을까요?  
  : 앱 내 섹션 구분, 다중 화면 전환

- TabLayout에서 사용할 수 있는 속성들은 무엇이 있을까요?  
  - app:tabGravity : 탭의 위치를 결정
  - app:tabMode : 탭을 스크롤할 수 있는지, 또는 화면에 맞게 압축할지를 결정
  - app:tabTextColor : 기본 탭 텍스트 색상을 지정
  - app:tabSelectedTextColor : 선택된 탭의 텍스트 색상을 지정
  - app:tabIndicatorColor : 선택된 탭 하단의 인디케이터 색상을 지정
  - app:tabIndicatorHeight : 선택된 탭 하단의 인디케이터 높이를 설정
  - app:tabPaddingStart : 탭의 시작에 패딩을 추가
  - app:tabPaddingEnd : 탭의 끝에 패딩을 추가
  - app:tabContentStart : 탭의 콘텐츠 시작 위치를 조정
  - app:tabBackground : 탭의 배경을 설정
  - app:tabIndicatorFullWidth : 선택된 탭의 인디케이터가 탭 전체에 걸칠지 여부를 결정
  - app:tabIconTint : 탭 아이콘의 색상을 설정
  - app:tabRippleColor : 탭을 클릭할 때 나타나는 물결 효과(ripple effect)의 색상을 지정

## ⚡️ViewPager2
- ViewPager란 무엇이고, 어떤 기능을 할까요?  
  : 여러 화면을 좌우로 스와이프하여 넘길 수 있도록 하는 UI 컴포넌트  
  : 페이지 전환 기능, 프래그먼트 및 TabLayout와의 연동, 페이지 간 애니메이션, 동적 페이지 관리

- ViewPager가 사용된 예시에는 무엇이 있을까요?  
  : 이미지 슬라이더, 앱 튜토리얼 화면, 탭과 결합한 콘텐츠 표시

- ViewPager와 ViewPager2의 차이는 무엇일까요?  
  : ViewPager2는 RecyclerView를 기반으로 더 유연하고 성능이 좋으며, 수직 스크롤, RTL 지원, 데이터 변경에 대한 더 세밀한 처리 등을 제공

- ViewPager2에서 사용할 수 있는 속성들은 무엇이 있을까요?  
  - setOrientation(int orientation) : ViewPager2의 스크롤 방향을 코드에서 설정
  - setUserInputEnabled(boolean enabled) : 사용자 스와이프를 통한 페이지 전환을 허용할지 여부를 설정
  - setOffscreenPageLimit(int limit) : ViewPager2가 미리 로드할 페이지 수를 설정
  - registerOnPageChangeCallback(ViewPager2.OnPageChangeCallback callback) : 페이지 전환 이벤트를 수신하는 콜백을 등록
  - setCurrentItem(int position, boolean smoothScroll) : 코드에서 특정 페이지로 전환할 수 있으며, 부드러운 스크롤 여부를 설정
  - setPageTransformer(ViewPager2.PageTransformer transformer) : 페이지 전환 시 애니메이션 효과를 설정

## ⚡️ViewPager2 설정하기
- ViewPager2를 이용하기 위해 어떤 라이브러리를 사용해야 할까요?  
  : Android Jetpack의 일부분으로 제공되는 ViewPager2 라이브러리  
  - android:orientation : 페이지를 스크롤하는 방향을 설정
  - android:layout_width / android:layout_height : 크기를 설정
  - android:clipToPadding : 패딩 영역을 스크롤 가능한 콘텐츠로 사용
  - android:clipChildren : 여러 페이지를 살짝 보여주는 애니메이션을 구현
  - android:paddingStart / android:paddingEnd / android:paddingTop / android:paddingBottom : 각 방향에 패딩을 추가

- ViewPager2에서 FragmentStateAdapter는 무엇이고 어떤 기능을 할까요?  
  : ViewPager2에서 프래그먼트를 페이지로 관리할 때 사용하는 어댑터  
  : 프래그먼트 상태 관리 및 재생성, 효율적인 메모리 관리

## ⚡️ViewPager2 Indicator 설정하기
- Indicator란 무엇이고, 어떤 역할을 할까요?  
  : 사용자가 현재 보고 있는 페이지나 콘텐츠의 위치를 시각적으로 알려주는 UI 요소  
  : 현재 페이지 시각화, 페이지 간의 탐색 안내, 페이지 전환 기능

- ViewPager2에서 Indicator를 설정하려면 어떻게 해야할까요?  
  : TabLayout이나 Dots Indicator와 같은 컴포넌트를 사용

## 📂실습 인증
강의 섹션 4까지 진행 
[Github](https://github.com/MunJeongEun/practice-7th-android.git)