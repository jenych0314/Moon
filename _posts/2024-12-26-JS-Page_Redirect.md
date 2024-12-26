---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.5

title: "[JS] JS로 웹페이지 리다이렉트하는 법"
excerpt: "모의해킹 취업반 스터디 7기 11주차"

date: 2024-12-26
last_modified_at: 

tags: [JS]
---

# Page Redirect
JS를 이용해 다른 웹페이지로 리다이렉트하는 방법은 두 가지 있다.  
`location.href`와 `location.replace`이다.  

```js
// Stimulate a Mouse Click
location.href = "example.com"; // 뒤로 가기 가능

// Stimulate an HTTP Redirect
location.replace("example.com"); // 뒤로 가기 불가능
```

**`replace`는 웹페이지 기록에서 현재 문서의 URL을 지우기 때문에 이전 페이지로 뒤로가기가 불가능하다.**

# 참고
* [How TO - Redirect to Another Webpage](https://www.w3schools.com/howto/howto_js_redirect_webpage.asp)