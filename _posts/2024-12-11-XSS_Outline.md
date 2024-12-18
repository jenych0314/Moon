---
layout: post
comments: true
sitemap:
    changefreq: daily

title: "[WEB HACKING] XSS"
excerpt: "모의해킹 취업반 스터디 7기 9주차"

date: 2024-12-13
last_modified_at: 

tags: [TIL, WEB, DATABASE, SECURITY]
---

# 목차
* [1. 개요](#1-개요)
* [](#2-xss-공격-방식)
* []()
* []()
* []()

# XSS(Cross Site Scripting)란?
## 1. 개요
**XSS(Cross Site Scripting)** 공격은 `웹 사이트에 악성 스크립트를 삽입하는 공격`이다.
보통 클라이언트 측에서 악성코드를 사용하여 다른 이용자를 공격한다.  
* 클라이언트 스크립트: 이용자 브라우저에서 실행되는 스크립트 -> HTML, CSS, JS
* 공격 방식: 스크립트를 삽입해 이용자의 브라우저에서 실행되게 만든다

## 2. XSS 공격 방식
XSS 공격 방식으로는 `Cookie Sniffing`, `스크립트 암호화 및 우회`, `악성 스크립트 유포`, `Key Logger`, `Mouse Sniffer`, `거짓 정보추가` 등이 있다.

## 3. XSS 공격 유형
1. Reflected XSS
1. Stored XSS
1. DOM Based SCC

### 3.1. Reflected XSS: 서버의 에코 기능을 이용하자
사용자에게 입력 받은 값을 서버에서 되돌려주는 곳에서 발생한다.  
e.g. 에러 메시지, 검색 결과 창, 아이디 중복 체크 등

공격자가 악성 스크립트를 클라이언트에게 직접 전달해 공격하는 방식이다.

특히 URL에 스크립트를 포함시켜 공격하는 경우가 대표적이다.
URL이 길면 클라이언트가 의심을 가질 수 있기 때문에 Shorten URL (URL 단축)을 이용해 짧은 URL로 만들어 공격하기도 한다.

서버에 스크립트를 저장하지 않기 때문에 서버에서 이뤄지는 필터링을 피할 수 있다.

흔적이 안 남음, 타겟팅 공격 가능  

---

1. 파라미터 데이터가 서버 응답에 삽입되어 오는가?  
burp, param check, response에 같은 값 있나?  
-> 삽입과 출력 위치가 같다  
1. 특수문자 체크
1. change request method가 가능하냐?
    1. get method 이용
1. 링크를 전달 공격

### 3.2. Stored XSS: 악성 스크립트를 서버에 저장하자
공격자가 악성 스크립트를 서버에 저장시킨 다음 클라이언트의 요청/응답 과정을 통해 공격하는 방식이다.

데이터가 저장되고, 출력(화면에 나오는 곳)되는 곳에서 발생한다.  
e.g. 데이터베이스, 댓글창, 방문 로그, 회원가입 페이지, 게시판 글 작성 페이지 등  
삽입한 게시물을 클릭 -> 실행  
광범위 공격, 흔적 남음

---

1. 작성한 데이터가 화면에 응답되는 거 확인  
-> 저장하는 곳과 출력되는 곳이 다를 수 있음
2. 특수문자 체크  
-> `<'">`
3. 스크립트 입력하기  
-> `<script>___<script>`

글자 수 제한이 있을 수 있다

### 3.3. DOM Based XSS
**문서 객체 모델(DOM: Document Object Model)**: 웹페이지를 여는 즉시 생성되어 사용자가 서버와 상호 작용하지 않고도 페이지의 모든 콘텐츠에 엑세스할 수 있도록 돕는 프로그래밍 인터페이스이다.

피해자의 브라우저가 HTML 페이지를 분석해 DOM을 생성할 때 악성 스크립트가 DOM의 일부로 구성되어 생성되는 공격이다.

서버의 응답 내에서 악성 스크립트가 포함되지 않지만 브라우저의 응답 페이지에 정상적인 스크립트가 실행되면서 악성 스크립트가 추가되어 실행된다.

## 4. 공격 구문 예시
**POC(Proof of Concept)**: 클라이언트측에서 코드가 실행되었음을 알려주는 코드  
e.g.
* `<script>alert(1);<script>`
* `<script>prompt(1);<script>`
* `<script>confirm(1);<script>`
* `<script>console.log(1);<script>`

---

1. 기본 구문  
`<script>alert(1)</script>`

1. `<script>` 태그 필터링  
`<scr<script>ipt>alert(1);</scr</script>ipt>`  
-> script 태그가 필터링되면 갈라져있던 script 태그가 결합되면서 구문 실행

1. `onmouseover` 이용  
`<a onmouseover="alert(1)">`  
-> onmouseover 이벤트를 통해 공격 실행  

1. `onerror` 이용  
`<img src=# onerror="alert(1)">`  
-> 고의적으로 src 주소를 지정 후 onerror 이벤트를 통해 공격 실행  

1. `onload` 이용  
`<body onload=alert(1)>`  

1. XSS Using Script Via Encoded URI Schemes  
`<IMG SRC=j&#X41vascript:alert(1)>`  
-> 필터링을 피하기 위해서 인코딩된 글자를 사용한다.  

1. XSS Using Code Encoding  
`<META HTTP-EQUIV="refresh" CONTENT="0;url=data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg">`  
-> `PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg` = `alert(1)`을 base64로 인코딩했다  
-> META 태그 안에 base64로 인코딩한 스크립트를 집어넣어 `alert()`의 원형을 완전히 숨길 수 있다.  

1. 흔히 사용하지 않는 태그 이용  
`<ruby onmouseover="alert(1)"></ruby>`  
-> 해당 태그가 필터에서 누락된 경우 공격 실행  

# 참고
* [Cross Site Scripting](https://owasp.org/www-community/attacks/xss/)
* [XSS란?](https://tibetsandfox.tistory.com/5)
* [크로스 사이트 스크립팅의 정의 및 공격 유형](https://nordvpn.com/ko/blog/xss-attack/)
* [XSS Filter Evasion Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet.html)
* [DOM-based XSS 1](https://portswigger.net/web-security/cross-site-scripting/dom-based)
* [DOM-based XSS 2](https://owasp.org/www-community/attacks/DOM_Based_XSS)