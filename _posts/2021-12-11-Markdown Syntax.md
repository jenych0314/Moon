---
layout: post
title: "마크다운(Markdown) 사용기"
date: 2021-12-11
excerpt: "마크다운(Markdown)의 기본적인 문법들과 html, css, js 적용 방법들"
tags: [Sample, Post, Test]
comments: true
---

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

# 2. 강조
```
이탤릭체: *이탤릭체*, _italic letters_, <i>이탤릭체</i>, <em>italic letters</em>  
두껍게: **두껍게**, __bold letters__ , <b>두껍게</b>, <strong>bold letters</strong>  
이탤릭체와 두껍게 같이: ***같이 사용하기***
취소선: ~~취소선~~ , <del>strikethrough</del>  
밑줄: <u>밑줄</u>, <ins>underline</ins>  
```
이탤릭체: *이탤릭체*, _italic letters_, <i>이탤릭체</i>, <em>italic letters</em>  
두껍게: **두껍게**, __bold letters__ , <b>두껍게</b>, <strong>bold letters</strong>  
굵은 이탤릭체: ***같이 사용하기***  
취소선: ~~취소선~~ , <del>strikethrough</del>  
밑줄: <u>밑줄</u>, <ins>underline</ins>  

# 3. 수평선
```
***
---
___
```
***
---
___

# 4. 블록 문구
```
> text
>> text
>>> text
> # text
```
> text
>> text
>>> text
> # text

```
    > text
    > text
    > text
```

    > text
    > text
    > text

# 5. 목록
```
* non-ordered list
    * 순서 없는 서브 목록
    + 순서 없는 서브 목록
    - 순서 없는 서브 목록
+ 순서 없는 목록
- 순서 없는 목록
1. ordered sub list
    1. 순서 있는 서브 목록
    2. 순서 있는 서브 목록
    3. 순서 있는 서브 목록
10. 순서 있는 목록
```
* non-ordered list
    * 순서 없는 서브 목록
    + 순서 없는 서브 목록
    - 순서 없는 서브 목록
+ 순서 없는 목록
- 순서 없는 목록
1. ordered sub list
    1. 순서 있는 서브 목록
    2. 순서 있는 서브 목록
    3. 순서 있는 서브 목록
10. 순서 있는 목록

# 7. 링크
[youtube](https://www.youtube.com)

<a href="http://www.youtube.com">youtube</a>

[youtube](https://www.youtube.com "유튜브")

<a href="http://www.youtube.com" title="유튜브">youtube</a>

[구글][1]
[1]: https://www.google.com

<http://www.naver.com>

<a href="https://www.naver.com">http://www.naver.com</a>

` print("Hello, World!")`

# 6. 표
```
| 1st | 2nd | 3rd |
| --- | --- | --- |
| 1 | 2 | 3 |
```

| 1st | 2nd | 3rd |
| --- | --- | --- |
| 1 | 2 | 3 |

```
| 1st | 2nd | 3rd |
| :--- | ---: | :---: |
| 1 | 2 | 3 |

```
| 1st | 2nd | 3rd |
| :--- | ---: | :---: |
| 1 | 2 | 3 |


### 테이블 구성
  * [1장](#chapter-1)
  * [2장](#chapter-2)
  * [3장](#chapter-3)

![Minion](http://octodex.github.com/images/minion.png)

![Alt text](http://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

<img src="http://octodex.github.com/images/stormtroopocat.jpg" alt="Alt text" title="The Stormtroopocat" />

![Alt text][10]
[10]: http://octodex.github.com/images/dojocat.jpg  "The Dojocat"

<!-- 주석 -->

최근 스칼라는 매우 인기가 높은 언어이다.[^scala]
[^scala]: 스칼라는 마틴 오더시크가 개발한 함수형 언어이다.

### 정렬
<center>중앙</center>  
<div style="text-align: left"> 왼쪽 </div>  
<div style="text-align: right"> 오른쪽 </div>  

### 첨자
<sup>윗첨자</sup>  
<sub>밑첨자</sub>  
<acronym title="텍스트 가리키면 나오는 텍스트">텍스트</acronym>  
<abbr title="텍스트 가리키면 나오는 텍스트">줄 쳐진 텍스트</abbr>  

### html, css


### 참고
1. <https://raw.githubusercontent.com/TaylanTatli/Moon/master/_posts/2016-03-20-markdown-syntax.md>
2. <http://taewan.kim/post/markdown/#comment>
3. <https://cizz3007.github.io/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4/%EB%AC%B8%EB%B2%95/markdown/2018/04/08/markdown/>
4. https://gist.github.com/ihoneymon/652be052a0727ad59601
5. https://theorydb.github.io/envops/2019/05/22/envops-blog-how-to-use-md/
6. https://lynmp.com/ko/article/nu86c16d8f09c9fbd8