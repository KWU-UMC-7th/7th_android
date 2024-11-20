# Chapter 7 - Database
## ⚡️Database (DB)
- Database의 정의는 무엇일까요?  
  : 데이터를 체계적으로 저장하고 관리하는 구조화된 저장 공간

- Database는 어디서 주로 사용될까요?  
  : 소셜 네트워크, 전자상거래 사이트, 채팅 애플리케이션

## ⚡️Database Management System (DBMS)
- DBMS란 무엇일까요?  
  : 데이터베이스를 관리하고 조작하는 소프트웨어 시스템

- 대표적인 DBMS는 무엇이 있을까요?  
  : Oracle Database, MySQL, MongoDB

- 관계형 저장 방식은 무엇일까요?  
  : 데이터를 테이블 형식으로 저장하며 데이터 간의 관계를 정의하고 관리하는 방식, 각 테이블은 행(Row)과 열(Column)로 구성되며 행 하나가 하나의 데이터 레코드를 나타냄, 테이블 간의 관계는 기본 키와 외래 키를 통해 연결

- 관계형이 아닌 저장 방식에는 무엇이 있을까요?  
  : 문서 지향(Document-Oriented), 컬럼 지향(Column-Family)

- SQL이란 무엇일까요?  
  - DDL(Data Definition Language) : 데이터베이스 객체(테이블, 인덱스, 스키마 등)를 정의하거나 구조를 변경하는 명령어
    - CREATE(생성) / ALTER(수정) / DROP(삭제) / TRUNCATE(테이블 구조를 유지하면서 데이터만 삭제)
  - DML(Data Manipulation Language) : 데이터베이스 내 데이터를 조작하는 데 사용
    - INSERT(삽입) / UPDATE(수정) / DELETE(삭제) / SELECT(검색)

## ⚡️Key-Value 구조
- Java나 Kotlin에서 Key-Value를 사용하는 대표적인 자료 구조는 무엇인가요?  
  : Map

- 해당 구조의 특징에는 무엇이 있을까요?  
  : Key-Value 페어 저장, Key의 중복 불허, 빠른 검색

- 배열이나 리스트가 아닌 경우 하나의 Key에 여러 값을 넣을 수 있을까요?  
  : 하나의 Key에 여러 값을 넣기 위해 List나 Set과 같은 컬렉션을 Value로 설정할 수 있음

## ⚡️SharedPreferences
- 하나의 Key에 여러 값을 넣는 방법이 있을까요? (Hint: JSON)  
  : JSON 형식으로 데이터를 변환하여 문자열(String)로 저장하는 방법

## ⚡️RoomDB
- RoomDB는 무엇일까요?  
  : Android에서 SQLite를 쉽게 사용할 수 있도록 도와주는 추상화된 데이터베이스 라이브러리

- RoomDB 개발 이전에 사용하였고, 현재 RoomDB의 기반인 DBMS는 무엇일까요?  
  : SQLite

- RoomDB는 어떤 방식으로 값을 저장할까요?  
  : 엔터티(Entity)를 데이터베이스의 테이블로 매핑하여 데이터를 저장

## ⚡️Firebase
- Firebase는 무엇이고 왜 사용할까요?  
  : Google에서 제공하는 클라우드 기반 백엔드 서비스 플랫폼, 백엔드 인프라를 관리할 필요 없이 다양한 기능을 쉽게 사용할 수 있도록 도와줌

- Firebase에서 제공해주는 기능은 어떤 것이 있나요?  
  - Firebase Authentication : 이메일/비밀번호, 전화번호, 소셜 로그인을 통한 인증을 지원
  - Firebase Realtime Database & Firestore : 클라우드 기반 데이터베이스로 실시간 데이터 동기화를 지원
  - Firebase Cloud Storage : 대용량 파일을 저장할 수 있는 클라우드 스토리지로, 이미지, 동영상, 오디오 파일 등을 쉽게 저장하고 가져올 수 있음
  - Firebase Hosting : 정적 콘텐츠와 웹 애플리케이션을 호스팅할 수 있는 빠르고 안전한 웹 호스팅 서비스
  - Firebase Cloud Messaging (FCM) : 푸시 알림을 보낼 수 있는 서비스

## 📂실습 인증
강의 섹션 8까지 진행
[Github](https://github.com/MunJeongEun/practice-7th-android.git)