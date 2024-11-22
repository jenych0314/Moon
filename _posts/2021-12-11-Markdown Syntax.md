---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.5

title: "마크다운 문법(Markdown Syntax)"
excerpt: "내가 써먹자고 정리해둔 마크다운(Markdown)의 기본적인 문법들과 html, css, js 적용 방법들"

date: 2021-12-11
last_modified_at: 2024-11-13

tags: [BLOG, MARKDOWN]
---

<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>

# 0. 목차
* [1. 제목](#1-제목header)
* [2. 내용](#2-내용context)
* [3. 수평선](#3-수평선horizon)
* [4. 인용문](#4-인용문block-quote)
* [5. 목록](#5-목록list)
* [6. 링크](#6-링크link)
* [7. 코드](#7-코드code)
* [8. 표](#8-표table)
* [9. 수식](#9-수식)
* [10. 이미지](#10-이미지image)
* [11. 다이어그램](#11-다이어그램---mermaid)
* [12. HTML, CSS, JS](#12-html-css-js)
* [참고](#참고)

# 1. 제목(Header)
```
# h1
## h2
### h3
#### h4
##### h5
###### h6
```

# h1
## h2
### h3
#### h4
##### h5
###### h6

```

h1
===

h2
---

```

h1
===

h2
---

# 2. 내용(Context)
## 2.1. 강조(Emphasize)
```
이탤릭체: *이탤릭체*, _italic letters_, <i>이탤릭체</i>, <em>italic letters</em>  
두껍게: **두껍게**, __bold letters__ , <b>두껍게</b>, <strong>bold letters</strong>  
이탤릭체와 두껍게 같이: ***같이 사용하기***
취소선: ~~취소선~~ , <del>strikethrough</del>  
밑줄: <u>밑줄</u>, <ins>underline</ins>  
<acronym title="텍스트 가리키면 나오는 텍스트">텍스트</acronym>  
<abbr title="텍스트 가리키면 나오는 텍스트">줄 쳐진 텍스트</abbr>  
```

이탤릭체: *이탤릭체*, _italic letters_, <i>이탤릭체</i>, <em>italic letters</em>  
두껍게: **두껍게**, __bold letters__ , <b>두껍게</b>, <strong>bold letters</strong>  
굵은 이탤릭체: ***같이 사용하기***  
취소선: ~~취소선~~ , <del>strikethrough</del>  
밑줄: <u>밑줄</u>, <ins>underline</ins>  
<acronym title="텍스트 가리키면 나오는 텍스트">텍스트</acronym>  
<abbr title="텍스트 가리키면 나오는 텍스트">줄 쳐진 텍스트</abbr>  

## 2.2. 정렬
```
<center>중앙</center>  
<div style="text-align: center"> 중앙 </div>  
<div style="text-align: left"> 왼쪽 </div>  
<div style="text-align: right"> 오른쪽 </div> 
```

<center>중앙</center>  
<div style="text-align: center"> 중앙 </div>  
<div style="text-align: left"> 왼쪽 </div>  
<div style="text-align: right"> 오른쪽 </div>  

## 2.3. 첨자
```
텍스트<sup>윗첨자</sup>  
텍스트<sub>밑첨자</sub>  
```

텍스트<sup>윗첨자</sup>  
텍스트<sub>밑첨자</sub>  

## 2.4. 주석
`<!-- 주석 -->`

## 2.5. 다음 줄로 넘어가기(New Line)
```
C/C++  <!-- 스페이스 두 번 -->
JAVA  <!-- 스페이스 두 번 -->
PYTHON  <!-- 스페이스 두 번 -->
R  <!-- 스페이스 두 번 -->
JAVA SCRIPT<br>
HTML<br>
CSS<br>
GO<br>
```

C/C++  <!-- 스페이스 두 번 -->
JAVA  <!-- 스페이스 두 번 -->
PYTHON  <!-- 스페이스 두 번 -->
R  <!-- 스페이스 두 번 -->
JAVA SCRIPT<br>
HTML<br>
CSS<br>
GO<br>

# 3. 수평선(Horizon)
```
***
---
___
```

***
---
___

# 4. 인용문(Block Quote)
```
> text
>> text
>>> text
> # text
```

> text
>> text
>>> text
> * text

# 5. 목록(List)
```
* non-ordered list
    * 순서 없는 서브 목록
    + 순서 없는 서브 목록
    - 순서 없는 서브 목록
+ 순서 없는 목록
- 순서 없는 목록
```

* non-ordered list
    * 순서 없는 서브 목록
    + 순서 없는 서브 목록
    - 순서 없는 서브 목록
+ 순서 없는 목록
- 순서 없는 목록

```
1. ordered sub list
    1. 순서 있는 서브 목록
    2. 순서 있는 서브 목록
    3. 순서 있는 서브 목록
10. 순서 있는 목록 <!-순서가 차례대로 자동으로 매겨짐>
```

1. ordered sub list
    1. 순서 있는 서브 목록
    2. 순서 있는 서브 목록
    3. 순서 있는 서브 목록
10. 순서 있는 목록

# 6. 링크(Link)
```
[GOOGLE](https://google.com)  
[Youtube](https://www.youtube.com "유튜브")  
[상대적 참조](./2021-11-30-github%EB%B8%94%EB%A1%9C%EA%B7%B8_%EB%8A%90%EB%82%80%EC%A0%90.md)  
이렇게도 [링크]를 타고 갈 수 있다고 하네요.  
Naver: <http://www.naver.com>  
Google: https://google.com  
<a href="http://www.youtube.com">Youtube</a>  
<a href="http://www.youtube.com" title="Youtube">Youtube</a>  

[Naver Link]: https://www.naver.com/
[1]: https://github.com/
[Naver][Naver Link]
[Github][1]
[링크]: https://google.com "구글"
```

[GOOGLE](https://google.com)  
[Youtube](https://www.youtube.com "유튜브")  
[상대적 참조](./2021-11-30-github%EB%B8%94%EB%A1%9C%EA%B7%B8_%EB%8A%90%EB%82%80%EC%A0%90.md)  
이렇게도 [링크]를 타고 갈 수 있다고 하네요.  
[Naver][Naver Link]  
[Github][1]  
Naver: <http://www.naver.com>  
Google: https://google.com  
<a href="http://www.youtube.com">Youtube</a>  
<a href="http://www.youtube.com" title="Youtube">Youtube</a>  

[Naver Link]: https://www.naver.com/
[1]: https://github.com/
[링크]: https://google.com "구글"

## 6.1. 응용
```
* [1. 제목](#1-제목header)
* [2. 내용](#2-내용context)
* [3. 수평선](#3-수평선horizon)
* [4. 인용문](#4-인용문block-quote)
* [5. 목록](#5-목록list)
* [6. 링크](#6-링크link)
* [7. 코드](#7-코드code)
* [8. 표](#8-표table)
* [9. 수식](#9-수식)
* [10. 이미지](#10-이미지image)
* [11. HTML, CSS, JS](#11-html-css-js)
* [12. 참고](#12-참고)
```

* [1. 제목](#1-제목header)
* [2. 내용](#2-내용context)
* [3. 수평선](#3-수평선horizon)
* [4. 인용문](#4-인용문block-quote)
* [5. 목록](#5-목록list)
* [6. 링크](#6-링크link)
* [7. 코드](#7-코드code)
* [8. 표](#8-표table)
* [9. 수식](#9-수식)
* [10. 이미지](#10-이미지image)
* [11. HTML, CSS, JS](#11-html-css-js)
* [12. 참고](#12-참고)

# 7. 코드(Code)
## 7.1. 인라인(inline)
```
`print("Hello, World!")`
```

`print("Hello, World!")`

## 7.2. 블록(block)
````
``` python
while (True):
    print("마크다운 나 짜증나게 하지마")
```
````
  
``` python
while (True):
    print("마크다운 나 짜증나게 하지마")
```

---

````
``` java
public static void main(String[] args) {
    while (true) {
        System.out.println("마크다운 나 짜증나게 하지마");
    }
}
```
````

``` java
public static void main(String[] args) {
    while (true) {
        System.out.println("마크다운 나 짜증나게 하지마");
    }
}
```

---

````
``` c
#include <stdio.h>

for (int i = 0; i++; i>10) {
    printf("Hello World!");
}

return 0;
```
````

``` c
#include <stdio.h>

for (int i = 0; i++; i>10) {
    printf("Hello World!");
}

return 0;
```

# 8. 표(Table)
```
| 1st | 2nd | 3rd |
| --- | --- | --- |
| 한자 | 심리학 | 수치해석학 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |
```

| 1st | 2nd | 3rd |
| --- | --- | --- |
| 한자 | 심리학 | 수치해석학 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |

```
| 1st | 2nd | 3rd |
| :--- | ---: | :---: |
| 좌로 정렬 | 가운데 정렬 | 우로 정렬 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |
```

| 1st | 2nd | 3rd |
| :--- | ---: | :---: |
| 좌로 정렬 | 가운데 정렬 | 우로 정렬 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |

``` html
<table>
    <thead>
        <tr>
            <th>1st</th>
            <th>2nd</th>
            <th>3rd</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan = "2">2열 병합</td>
            <!-- <td>가운데 정렬</td> -->
            <td style = "text-align: right">우로 정렬</td>
        </tr>
        <tr>
            <td rowspan = "2">2행 병합</td>
            <td style = "text-align: center">가운데 정렬</td>
            <td style = "text-align: left">좌로 정렬</td>
        </tr>
        <tr>
            <!-- <td>컴퓨터 구조</td> -->
            <td>토익</td>
            <td>파이썬</td>
        </tr>
    </tbody>
</table>
```

<table>
    <thead>
        <tr>
            <th>1st</th>
            <th>2nd</th>
            <th>3rd</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan = "2">2열 병합</td>
            <!-- <td>가운데 정렬</td> -->
            <td style = "text-align: right">우로 정렬</td>
        </tr>
        <tr>
            <td rowspan = "2">2행 병합</td>
            <td style = "text-align: center">가운데 정렬</td>
            <td style = "text-align: left">좌로 정렬</td>
        </tr>
        <tr>
            <!-- <td>컴퓨터 구조</td> -->
            <td>토익</td>
            <td>파이썬</td>
        </tr>
    </tbody>
</table>

# 9. 수식
```
$$f(x)= if x < x_{min} : (x/x_{min})^a$$  
$$otherwise : 0$$  
$$P(w)=U(x/2)(7/5)/Z$$  
$$p_{\theta}(x) = \int p_{\theta}(2z)p_{\theta}(y\mid k)dz$$  
$$x = argmax_k((x_t-x_u+x_v)^T*x_m)/(||x_b-x_k+x_l||)$$  
```

$$f(x)= if x < x_{min} : (x/x_{min})^a$$  
$$otherwise : 0$$  
$$P(w)=U(x/2)(7/5)/Z$$  
$$p_{\theta}(x) = \int p_{\theta}(2z)p_{\theta}(y\mid k)dz$$  
$$x = argmax_k((x_t-x_u+x_v)^T*x_m)/(||x_b-x_k+x_l||)$$  

# 10. 이미지(Image)
```
![첫 번째 이미지](https://cdn.pixabay.com/photo/2023/01/25/08/59/bird-7742845_960_720.jpg "링크 설명(title)")
```

![첫 번째 이미지](https://cdn.pixabay.com/photo/2023/01/25/08/59/bird-7742845_960_720.jpg "링크 설명(title)")

```
![두 번째 이미지](https://cdn.pixabay.com/photo/2023/01/11/09/30/trees-7711283_960_720.jpg "두 번째 이미지")
```

![두 번째 이미지](https://cdn.pixabay.com/photo/2023/01/11/09/30/trees-7711283_960_720.jpg "두 번째 이미지")

```
![세 번째 이미지][이미지 링크]
```

![세 번째 이미지][이미지 링크]

```
<!-- 이 넘은 사진 클릭하면 링크 탐 -->
[![네 번째 이미지](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_2015_logo.svg/368px-Google_2015_logo.svg.png)](https://www.google.no/)
```

이 넘은 사진 클릭하면 링크 탐
[![네 번째 이미지](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_2015_logo.svg/368px-Google_2015_logo.svg.png)](https://www.google.no/)

```
<img src="https://cdn.pixabay.com/photo/2023/01/27/01/40/brothers-7747561_960_720.jpg" alt="이건 뭐시기냐" title="네 번째 이미지" />
```

<img src="https://cdn.pixabay.com/photo/2023/01/27/01/40/brothers-7747561_960_720.jpg" alt="이건 뭐시기냐" title="다섯 번째 이미지" />

```
[이미지 링크]: https://cdn.pixabay.com/photo/2023/01/14/18/17/hot-air-balloon-7718789_960_720.jpg  "세 번째 이미지"
```

[이미지 링크]: https://cdn.pixabay.com/photo/2023/01/14/18/17/hot-air-balloon-7718789_960_720.jpg  "세 번째 이미지"

# 11. 다이어그램 -> mermaid
Pages는 Mermaid가 적용되지 않아서 HTML 요소를 사용해서 처리해야 한다
그렇기 때문에 포스트 맨 위와
```HTML
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
```
맨 아래에
``` HTML
<script>
mermaid.initialize({startOnLoad:true});
window.mermaid.init(undefined, document.querySelectorAll('.language-mermaid'));
</script>
```
를 적용해줘야 한다

````
```mermaid
graph LR
A[Encoding/Decoding<br>인코딩/디코딩]
B(Encryption/Decryption<br>암호화/복호화) --> C(Hash<br>단방향 암호화)
B --> D(Encryption<br>양방향 암호화)
D --> E(대칭키)
D --> F(비대칭키)
```
````

```mermaid
graph LR
A[Encoding/Decoding<br>인코딩/디코딩]
B(Encryption/Decryption<br>암호화/복호화) --> C(Hash<br>단방향 암호화)
B --> D(Encryption<br>양방향 암호화)
D --> E(대칭키)
D --> F(비대칭키)
```

```
~~~ mermaid
graph LR
A[Encoding/Decoding<br>인코딩/디코딩]
B(Encryption/Decryption<br>암호화/복호화) --> C(Hash<br>단방향 암호화)
B --> D(Encryption<br>양방향 암호화)
D --> E(대칭키)
D --> F(비대칭키)
~~~
```

~~~ mermaid
graph LR
A[Encoding/Decoding<br>인코딩/디코딩]
B(Encryption/Decryption<br>암호화/복호화) --> C(Hash<br>단방향 암호화)
B --> D(Encryption<br>양방향 암호화)
D --> E(대칭키)
D --> F(비대칭키)
~~~

````
``` mermaid
pie title What Voldemort doesn't have?
         "FRIENDS" : 2
         "FAMILY" : 3
         "NOSE" : 45
```
````

``` mermaid
pie title What Voldemort doesn't have?
         "FRIENDS" : 2
         "FAMILY" : 3
         "NOSE" : 45
```

````
``` mermaid
sequenceDiagram
    Alice ->> Bob: Hello Bob, how are you?
    Bob-->>John: How about you John?
    Bob--x Alice: I am good thanks!
    Bob-x John: I am good thanks!
    Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

    Bob-->Alice: Checking with John...
    Alice->John: Yes... John, how are you?
```
````

``` mermaid
sequenceDiagram
    Alice ->> Bob: Hello Bob, how are you?
    Bob-->>John: How about you John?
    Bob--x Alice: I am good thanks!
    Bob-x John: I am good thanks!
    Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

    Bob-->Alice: Checking with John...
    Alice->John: Yes... John, how are you?
```

````
``` mermaid
graph LR
    A[Square Rect] -- Link text --> B((Circle))
    A --> C(Round Rect)
    B --> D{Rhombus}
    C --> D
```
````

``` mermaid
graph LR
    A[Square Rect] -- Link text --> B((Circle))
    A --> C(Round Rect)
    B --> D{Rhombus}
    C --> D
```

````
``` mermaid
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A
        od>Odd shape]-- Two line<br/>edge comment --> ro
        di{Diamond with <br/> line break} -.-> ro(Rounded<br>square<br>shape)
        di==>ro2(Rounded square shape)
    end

    %% Notice that no text in shape are added here instead that is appended further down
    e --> od3>Really long text with linebreak<br>in an Odd shape]

    %% Comments after double percent signs
    e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز)

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

     classDef green fill:#9f6,stroke:#333,stroke-width:2px;
     classDef orange fill:#f96,stroke:#333,stroke-width:4px;
     class sq,e green
     class di orange
```
````

``` mermaid
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A
        od>Odd shape]-- Two line<br/>edge comment --> ro
        di{Diamond with <br/> line break} -.-> ro(Rounded<br>square<br>shape)
        di==>ro2(Rounded square shape)
    end

    %% Notice that no text in shape are added here instead that is appended further down
    e --> od3>Really long text with linebreak<br>in an Odd shape]

    %% Comments after double percent signs
    e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز)

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

     classDef green fill:#9f6,stroke:#333,stroke-width:2px;
     classDef orange fill:#f96,stroke:#333,stroke-width:4px;
     class sq,e green
     class di orange
```
참고 사이트에 종류가 더 있으니 직접 확인하는 걸 추천한다

# 12. HTML, CSS, JS
마크다운에 HTML, CSS, JS 문법을 적용시킬 수 있다고 한다.
assets/css/main.css의 css들 좌표가 찍혀있다.
-> _sass/*.scss 중에서 하나를 수정을 하던가, _sass 밑으로 css 파일 하나 더 만들어서 main.css의 좌표를 더 찍어넣기.
-> _sass/normalize.scss에서 h1 발견함. 여기서 코드 수정하면 될 듯.
- h5 이상, h5, h6일 때는 글자 크기가 너무 작아짐. 최소치를 정해둬야겠음.

# 참고
* [Markdown Syntax 1](http://taewan.kim/post/markdown/#comment)
* [Markdown Syntax 2](https://cizz3007.github.io/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4/%EB%AC%B8%EB%B2%95/markdown/2018/04/08/markdown/)
* [Markdown Syntax 3](https://gist.github.com/ihoneymon/652be052a0727ad59601)
* [Markdown Syntax 4](https://theorydb.github.io/envops/2019/05/22/envops-blog-how-to-use-md/)
* [Markdown Syntax 5](https://heropy.blog/2017/09/30/markdown/)
* [Markdown Syntax 6](https://theorydb.github.io/envops/2019/05/22/envops-blog-how-to-use-md/)
* [Markdown Syntax 7](https://www.heropy.dev/p/B74sNE)
* [Markdown Syntax(RAW HTML) 8](https://raw.githubusercontent.com/TaylanTatli/Moon/master/_posts/2016-03-20-markdown-syntax.md)
* [Markdown 각주, 미주](https://lynmp.com/ko/article/nu86c16d8f09c9fbd8)
* [Markdown Mermaid(Diagram)](https://mystria.github.io/archivers/apply-mermaid-diagram-to-github-pages)
* [Mermaid(Diagram) Syntax](https://mermaid.js.org/syntax/examples.html)
* [HTML table 병합](https://hianna.tistory.com/442)
* [HTML <table>, <tr>, <th>, <td>](https://jinnnkcoding.tistory.com/106)
* [HTML <th>](https://www.tcpschool.com/html-tags/th)
* [HTML <li>](https://tcpschool.com/html-tag-attrs/li-value)

<script>
mermaid.initialize({startOnLoad:true});
window.mermaid.init(undefined, document.querySelectorAll('.language-mermaid'));
</script>