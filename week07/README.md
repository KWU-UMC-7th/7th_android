> 과제는 `mission/udemy_android_flo (branch:W06,07)` 을 참고해주세요

### 7주차 개발일지

> 결과 영상 및 수행항목 워크북 링크입니다
> https://www.notion.so/makeus-challenge/Chapter-7-Database-c91b80aa614243be9d3eeb1cafadc30d

## 🎯 키워드 Essential

- Database (DB)
  - Database의 정의는 무엇일까요?
    데이터를 일관성 있게 저장, 빠르게 검색, 변경, 삭제할 수 있게 해주는 소프트웨어 시스템
  - Database는 어디서 주로 사용될까요?
    데이터를 보관해야 하는 분야에서는 필수로 활용됨.
    전자 상거래, 소셜 미디어, 은행 및 금융 시스템 등등등
- Database Management System (DBMS)

  - DBMS란 무엇일까요?
    데이터베이스를 관리하고 운영하는 소프트웨어 시스템으로 데이터를 정의하고 저장 및 조회, 수정, 삭제 를 비롯해서, 트랜잭션, 보안, 백업 등등 많은 작업을 수행하는 데이터베이스 관리 시스템
  - 대표적인 DBMS는 무엇이 있을까요?
    관계형 DBMS: MySQL, PostgreSQL, SQLite
    비관계형 DBMS: MongoDB, Cassandra, Radis
    객체지향 DBMS: ObjectDB
  - 관계형 저장 방식은 무엇일까요?
    데이터를 테이블 형식으로 저장하고 관리하는 방식.
    여기에 테이블 사에 관계를 맺어 테이블에 분산된 데이터를 유연하게 관리 및 제공할 수 있음.
  - 관계형이 아닌 저장 방식에는 무엇이 있을까요?
    - Key-Value store: 데이터(Value)와 그 위치(Key) 쌍으로 저장
    - Document store: Json 과 같은 방식으로 데이터를 저장
    - Graph store: 노드-엣지-속성을 사용하여 데이터를 저장
  - SQL이란 무엇일까요?

    1. DDL(Data Definition Language)

       데이터베이스 구조나 스키마를 정의하는 데 사용 → 데이터의 내용이 아닌 구조를 정의

       (데이터베이스에 저장되는 테이블, 뷰, 인덱스 등과 같은 객체를 생성, 수정, 삭제)

    2. DML(Data Manipulation Language)

       데이터베이스에 저장된 **데이터**를 **조작**하는 데 사용되는 명령어 집합 → 쿼리문

    3. ~~DCL(Data Control Language)~~

- Key-Value 구조
  - Java나 Kotlin에서 Key-Value를 사용하는 대표적인 자료 구조는 무엇인가요?
    - HashMap
    - TreeMap
    - LinkedHashMap (kt only)
  - 해당 구조의 특징에는 무엇이 있을까요?
    | Map 종류 | 조회/삽입 성능 | 순서 보장 | Null 키/값 지원 | 주요 용도 |
    | ----------------- | -------------- | -------------- | --------------- | ------------------------------- |
    | **HashMap** | O(1) | 보장 안 됨 | Null 키/값 허용 | 빠른 데이터 검색 및 캐시 시스템 |
    | **TreeMap** | O(log N) | 정렬된 순서 | Null 키 불가 | 정렬된 데이터 처리, 범위 검색 |
    | **LinkedHashMap** | O(1) | 삽입 순서 보장 | Null 키/값 허용 | 입력 순서 보장, 캐시 시스템 |
  - 배열이나 리스트가 아닌 경우 하나의 Key에 여러 값을 넣을 수 있을까요?
    Map 자료 구조에 컬렉션(리스트, 셋 등)을 값으로 사용하는 방법이나, 커스텀 객체를 사용하는 방법을 사용하여 여러 값을 넣을 수 있음.
- SharedPreferences
  - 하나의 Key에 여러 값을 넣는 방법이 있을까요? (Hint: JSON)
    Json을 직렬화하여 값으로 넣으면 가능.
- RoomDB
  - RoomDB는 무엇일까요?
    Android에서 제공하는 객체 지향적인 데이터베이스로, SQLite를 보다 쉽게 사용할 수 있도록 래핑(wrapping)한 라이브러리
  - RoomDB 개발 이전에 사용하였고, 현재 RoomDB의 기반인 DBMS는 무엇일까요?
    SQLite
  - RoomDB는 어떤 방식으로 값을 저장할까요?
    객체 지향적인 방식으로 값을 저장.
    → 자바 객체를 SQLite 데이터베이스 테이블에 매핑하여 데이터를 저장하고 조회하는 방식을 사용
- Firebase
  - Firebase는 무엇이고 왜 사용할까요?
    Google이 제공하는 모바일 및 웹 애플리케이션 개발 플랫폼으로, 애플리케이션 개발자가 서버 측 코드나 인프라를 관리하지 않고도 다양한 백엔드 서비스를 손쉽게 통합할 수 있게 도와주는 서비스라 사용함.
  - Firebase에서 제공해주는 기능은 어떤 것이 있나요?
    - Firebase Authentication
    - Firebase Realtime Database
    - Cloud Firestore
    - FCM
    - Firebase Hosting
    - Firebase Analytics
    - Firebase Cloud Function
