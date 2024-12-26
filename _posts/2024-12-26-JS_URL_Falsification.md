---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.5

title: "[JS] JS로 페이지 갱신 없이 URL 변경하기"
excerpt: "모의해킹 취업반 스터디 7기 11주차"

date: 2024-12-26
last_modified_at: 

tags: [JS]
---

# 주소창 변조하기
## Syntax
```js
pushState(state, unused)
pushState(state, unused, url)
```

## Parameters
* state: 
* unused: 더 이상 사용되지 않는데 생략이 불가하다고 한다.
* url: 

## Return Value
None

## Example Code
<script>history.pushState(null, null, 'test')</script>

```js
history.pushState(null, null, 'test') // domain 변경은 안 되지만
```

# 참고
* [History: pushState() method](https://developer.mozilla.org/en-US/docs/Web/API/History/pushState)
* [[JavaScript] history.pushState() - 페이지 갱신없이 주소URL 변경하기](https://mine-it-record.tistory.com/439)
* [JavaScript를 사용하여 동적으로 URL 변경](https://www.tempmail.us.com/ko/javascript/%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A5%BC-%EB%8B%A4%EC%8B%9C-%EB%A1%9C%EB%93%9C%ED%95%98%EC%A7%80-%EC%95%8A%EA%B3%A0-javascript%EC%97%90%EC%84%9C-url-%EC%88%98%EC%A0%95)