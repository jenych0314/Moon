---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.5

title: "[MySQL] DATABASE란? 간단한 SQL Query문"
excerpt: "모의해킹 취업반 스터디 7기 2주차"

date: 2024-10-23
last_modified_at: 2024-11-22

tags: [WEB, DATABASE]
---

# Database
DB, Database는 데이터를 저장하고 관리할 수 있는 도구다.  
예시를 들면  
Database -> Excel File  
Table -> Excel Sheet  
  
아래는 Costomers라는 table 예시다
<table>
    <thead>
        <tr>
            <th>아이디</th>
            <th>고객명</th>
            <th>관리인</th>
            <th>주소</th>
            <th>도시</th>
            <th>코드</th>
            <th>국가</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>임꺽정</td>
            <td>명종</td>
            <td>양주시 유양동</td>
            <td>경기도</td>
            <td>12209</td>
            <td>조선</td>
        </tr>
        <tr>
            <td>2</td>
            <td>장길산</td>
            <td>숙종</td>
            <td>양덕현</td>
            <td>평안도</td>
            <td>05021</td>
            <td>조선</td>
        </tr>
        <tr>
            <td>3</td>
            <td>홍길동</td>
            <td>홍판서</td>
            <td>장성현 아곡리 아치실 마을</td>
            <td>전라도</td>
            <td>05023</td>
            <td>율도국</td>
        </tr>
        <tr>
            <td>4</td>
            <td>전우치</td>
            <td>초랭이</td>
            <td>무녀의 집</td>
            <td>서화담 상생</td>
            <td>강동원</td>
            <td>조선</td>
        </tr>
        <tr>
            <td>5</td>
            <td>또치</td>
            <td>고길동</td>
            <td>도봉구 쌍문동</td>
            <td>서울</td>
            <td>보물섬</td>
            <td>아프리카</td>
        </tr>
    </tbody>
</table>
  
Column: 열, 데이터 종류, 카테고리, 세로  
위 예시에서 column 개수는 7개이고,  
Row: 행, 가로 데이터  
위 예시에서 row 개수는 5개이다.  

<!-- http://192.168.219.197:1018/phpmyadmin/
admin
student1234 -->
utf8_generalci
variable character =/=? text
auto increament
primary

# SQL(Structed Query Language)
SQL: 관계형 데이터베이스 관리 시스템(RDBMS)의 데이터를 관리하기 위해 설계한 특수 목적의 프로그래밍 언어이다.  
~~WAS가 DB한테 Query를 통해 명령을 알아서 하도록 만든다.~~

## 주요 SQL 명령어
* SELECT: DB에서 데이터를 추출한다
* UPDATE: DB의 데이터를 갱신한다
* DELETE: DB의 데이터를 삭제한다
* INSERT INTO: DB에 새로운 데이터를 삽입한다
* CREATE DATABASE: 새로운 DB를 만든다
* ALTER DATABASE: DB를 수정한다
* DROP TABLE: Table을 삭제한다
* CREATE INDEX: <abbr title = "더 빠르게 찾을 수 있도록 도와주는 키값">Index</abbr>를 만든다
* DROP INDEX: Index를 삭제한다

### SELECT: 데이터를 가져온다
SELECT [col] FROM [table]
e.g. SELECT id FROM test
SELECT [col1, col2] FROM [table]
SELECT [*] FROM [table]

### INSERT INTO: 데이터를 넣는다
INSERT INTO [table] (col) VALUE (VALUE)
e.g. INSERT INTO test (id) ('hong')
INSERT INTO [table] (col) VALUE (VALUE)
e.g. INSERT INTO test (id, int) ('hong', 7)
e.g. INSERT INTO test VALUE (NULL, '')

### WHERE: 조건에 맞는 데이터를 가져온다
SELECT [col] FROM [table] WHERE [조건]
e.g. SELECT name FROM test WHERE name='hong'
e.g. SELECT name,pass FROM test WHERE name='hong' AND pass='1234'
e.g. SELECT name,pass FROM test WHERE name='hong' OR pass='1234'

# 참고
* [SQL이란?](https://ko.wikipedia.org/wiki/SQL)
* [What is an index in SQL?](https://stackoverflow.com/questions/2955459/what-is-an-index-in-sql)
* []()
* []()
* []()