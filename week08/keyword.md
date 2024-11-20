# Chapter 8 - Token
## ⚡️OAuth2 방식
- OAuth2란 무엇일까요?  
  : 비밀번호와 같은 민감한 정보를 요구하지 않고도 제3자 애플리케이션에게 안전하게 리소스에 접근 권한을 부여할 수 있는 인증 및 권한 부여 프레임워크

- 우리 주변에서 OAuth2 방식이 주로 사용되는 곳은 어디일까요? (Hint: 간편 로그인)  
  : Google, Facebook, Apple 등의 계정을 사용해 다른 웹사이트나 앱에 로그인하는 간편 로그인을 지원하는 서비스

- 토큰이란 무엇일까요?  
  : 사용자의 인증 및 권한을 나타내는 암호화된 문자열

- OAuth2에서 사용되는 토큰은 어떤 것이 있고, 각각 어떤 용도일까요?  
  - Access Token : 리소스 서버에 접근할 때 필요한 인증 수단으로 사용
  - Refresh Token : Access Token이 만료되었을 때 새로운 Access Token을 발급받기 위해 사용

- OAuth2 방식의 장점과 단점은 무엇일까요?  
  - 장점 : 보안성 강화, 간편한 인증 및 권한 관리, 재사용 가능, 확장성
  - 단점 : 구현의 복잡성, 취약점에 대한 위험성, 토큰 관리의 어려움, 서드파티 및 네트워크 의존성

## ⚡️Cookie와 Session
- Cookie란 무엇일까요?  
  : 웹사이트가 사용자의 웹 브라우저에 저장하는 작은 데이터 조각

- Cookie는 어떤 형식으로 이루어져 있나요?  
  : 키-값 쌍 형태의 데이터

- Session이란 무엇일까요?  
  : 웹 서버에서 사용자와의 상호작용 동안 생성된 임시 데이터 저장소

- Cookie와 Session을 사용하는 이유는 무엇일까요?  
  : Cookie와 Session을 사용하여 사용자의 정보를 저장하고, 이후 요청 시 이를 참조함으로써 로그인 상태나 사용자 정보를 지속하기 위함

- Cookie와 Session의 차이는 무엇일까요?  
  - Cookie : 설정된 만료 시간까지 유지되며 장바구니, 사용자 환경 설정, 자동 로그인 등에 사용
  - Session : 브라우저 종료 시 또는 일정 시간 이후 만료되며 로그인 세션, 사용자 상태 정보 유지 등에 사용

## ⚡️JWT 방식
- JWT (JSON Web Token)은 무엇일까요?  
  : JSON 형식으로 정보를 안전하게 주고받기 위한 토큰 기반 인증 방식

- JWT 방식의 토큰은 어떤 구조로 되어있고, 각각 어떤 용도로 사용되나요?  
  - Header : JWT의 유형과 서명 알고리즘 정보를 포함
  - Payload : 사용자 정보나 권한 등 토큰에 담을 실제 데이터를 포함
  - Signature : 토큰의 무결성을 보장하고, 이를 통해 데이터 변조 여부를 확인

- JWT 방식의 장점과 단점은 무엇일까요?  
  - 장점 : 안전한 데이터 전송, 신속한 인증
  - 단점 : 토큰 만료 관리 어려움, 보안 문제

## 📂실습 인증
강의 섹션 9까지 진행
[Github](https://github.com/MunJeongEun/practice-7th-android.git)