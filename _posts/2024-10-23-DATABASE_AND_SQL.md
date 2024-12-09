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

# 데이터베이스와 DBMS
* 데이터베이스: 데이터를 효율적으로 관리하기 위해 구조화한 데이터 집합
* DBMS(Data Base Management System): 데이터베이스를 운영 및 관리. 계층형, 망형, 관계형 등 다양한 종류의 DBMS가 존재하며 대부분 관계형 DBMS(RDMBS)의 형태로 사용되고 있다. RDBMS의 데이터베이스는 하나 이상의 행(row)과 열(column)로 이루어진 테이블 형식을 데이터를 제공한다.

예시를 들면  
Database -> Excel File  
Table -> Excel Sheet  
  
아래는 데이터베이스 테이블 구조 예시
![alt text](image.png)

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