> 과제는 `mission/w01basiclayout` 을 참고해주세요

### Q.2

> LinearLayout, ConstraintLayout등 본인이 적절하다고 판단되는 것으로 화면을 구현하고나서 어떤 Layout이 더 효율적인지 정리해보기

LinearLayout은 특정 Axis 방향으로 일관된 스타일을 적용하여 배치하는데 특화되어 있다고 생각함.

예로 들어 유튜브 홈 화면의 리스트와 같은 화면에서 유리할 수 있음 (성능 고려 X).

ConstraintLayout은 여러 컴포넌트간 상대적인 위치를 커스텀 하는데 특화되어 있다고 생각함.

예로 들어 회원가입 화면에서의 입력 폼과 같은 화면에서 유리할 수 있음.

이러한 관점에서 1주차의 화면은 여러 컴포넌트를 배치하는 작업이라 판단하여 ConstraintLayout이 더 효율적이라 생각됨.
