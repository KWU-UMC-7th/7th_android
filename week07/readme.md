- Database (DB)
    - Database의 정의는 무엇일까요?
        - 체계화된 데이터의 모임으로써 검색과 구조화 같은 작업을 보다 쉽게 하기 위해 조직화된 데이터를 수직하는 저장 시스템
    - Database는 어디서 주로 사용될까요?
        - SQLite, Room Persistence LIbrary, Realm, Firestone, etc…
- Database Management System (DBMS)
    - DBMS란 무엇일까요?
        - 데이터베이스를 조작하는 프로그램
    - 대표적인 DBMS는 무엇이 있을까요?
        - Oracle, MySQL, MSSQL, MariaDB, Tiber
    - 관계형 저장 방식은 무엇일까요?
        - 데이터를 행과 열이 있는 데이블 형식으로 저장해주는 것
    - 관계형이 아닌 저장 방식에는 무엇이 있을까요?
        - 비관형 저장 방식
    - SQL이란 무엇일까요?
        1. DDL(Data Definition Language)
            - 데이터베이스를 정의하는 언어이며 데이터를 생성, 수정, 삭제하는 등의 데이터의 전체의 골격을 결정하는 역할을 하는 언어
        2. DML(Data Manipulation Language)
            - 정의된 데이터베이스에 입력된 레코드를 조회하거나 수정하거나 삭제하는 등의 역할을 하는 언어
        3. ~~DCL(Data Control Language)~~
- Key-Value 구조
    - Java나 Kotlin에서 Key-Value를 사용하는 대표적인 자료 구조는 무엇인가요?
        - Map 인터페이스
    - 해당 구조의 특징에는 무엇이 있을까요?
        - Key-value 쌍 저장이 가능하고 key를 사용하여 값을 빠르게 검색할 수 있다. 또한 모든 키는 유일해야한다.
    - 배열이나 리스트가 아닌 경우 하나의 Key에 여러 값을 넣을 수 있을까요?
        - 네
- SharedPreferences
    - 하나의 Key에 여러 값을 넣는 방법이 있을까요? (Hint: JSON)
        - 
- RoomDB
    - RoomDB는 무엇일까요?
        - SQLite 데이터데이스를 사용하기 쉽게 해주는 ORM라이브러리이다.
    - RoomDB 개발 이전에 사용하였고, 현재 RoomDB의 기반인 DBMS는 무엇일까요?
        - 데이터베이스를 정의, 생성, 유지 관리 및 제어하는 소프트웨어 시스템이다.
    - RoomDB는 어떤 방식으로 값을 저장할까요?
        - ORM라입러리 형식으로 값을 저장한다.
- Firebase
    - Firebase는 무엇이고 왜 사용할까요?
        - Google이 제공하는 클라우드 기반 개발 플랫폼으로 모바일 및 웹 애플리케이션을 개발, 개선 및 성장시키기 위한 다양한 도구와 서비스를 제공하기 때문에 애플리케이션을 더 쉽고 빠르게 개발하기 위해 사용한다.
    - Firebase에서 제공해주는 기능은 어떤 것이 있나요?
        - Firebase Realtime DB, Cloud Firestore, Firebase Authentication, etc…


    실습
    https://github.com/sojung0628/android_flo/tree/main