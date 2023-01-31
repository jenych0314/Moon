---
layout: post
title: "마크다운(Markdown) 사용기"
date: 2021-12-11
excerpt: "마크다운(Markdown)의 기본적인 문법들과 html, css, js 적용 방법들"
tags: [Sample, Post, Test]
comments: true
---

### 목차
* [1. 제목](#1-제목header)
* [2. ](#2-강조)
* [3. 목록](#3-목록)
* [4. 블록 문구](#4-인용문block-quote)
* [5. 수평선](#5-수평선)
* [6. 링크](#6-링크)
* [7. ]()
* [8. ]()
* [9. ]()

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

# 2. 강조(Emphasize)
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

```
    > text
    > text
    > text
```

    > text
    > text
    > text

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
10. 순서 있는 목록
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

## 응용
```
### 목차
* [1. 제목](#1-제목header)
* [2. 강조](#2-강조)
* [3. 수평선](#3-수평선)
```

### 목차
* [1. 제목](#1-제목header)
* [](#2-링크)
* [](#3-목록)
* [](#4-블록-문구)
* [](#5-수평선)
* [](#6-링크)
* []()
* []()
* []()

# 7. 코드(Code) 강조
## 7.1. 인라인(inline) 코드 강조
`print("Hello, World!")`
print("Hello, World!")
## 7.2. 블록(block) 코드 강조
``` python
while (True):
    print("마크다운 나 짜증나게 하지마")
```
``` java
public static void main(String[] args) {
    while (true) {
        System.out.println("마크다운 나 짜증나게 하지마");
    }
}
```
```
public static void main(String[] args) {
    while (true) {
        System.out.println("마크다운 나 짜증나게 하지마");
    }
}
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
| 좌로 정렬 | 가운데 정렬 | 우로 정렬 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |

```
| 1st | 2nd | 3rd |
| :--- | ---: | :---: |
| 한자 | 심리학 | 수치해석학 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |
```

| 1st | 2nd | 3rd |
| :--- | ---: | :---: |
| 한자 | 심리학 | 수치해석학 |
| 선형대수학 | 통계학 | 이산수학 |
| 컴퓨터 구조 | 토익 | 파이썬 |

# 9. 이미지(Image)
![첫 번째 이미지](_image\2021-12-01-CheshireCat2.png)

![두 번째 이미지](_image\2021-12-01-CheshireCat1.jpg "2nd image")

![세 번째 이미지][이미지 링크]

<img src="_image\2021-12-01-CheshireCat2.png" alt="Alt text" title="The Stormtroopocat" />

[이미지 링크]: _image\2021-12-01-CheshireCat1.jpg  "The Dojocat"

<!-- 주석 -->

최근 스칼라는 매우 인기가 높은 언어이다.[^scala]
[^scala]: 스칼라는 마틴 오더시크가 개발한 함수형 언어이다.

# 정렬
<center>중앙</center>  
<div style="text-align: left"> 왼쪽 </div>  
<div style="text-align: right"> 오른쪽 </div>  

# 첨자
텍스트<sup>윗첨자</sup>  
텍스트<sub>밑첨자</sub>  
<acronym title="텍스트 가리키면 나오는 텍스트">텍스트</acronym>  
<abbr title="텍스트 가리키면 나오는 텍스트">줄 쳐진 텍스트</abbr>  

# html, css


### 참고
1. <https://raw.githubusercontent.com/TaylanTatli/Moon/master/_posts/2016-03-20-markdown-syntax.md>
2. <http://taewan.kim/post/markdown/#comment>
3. <https://cizz3007.github.io/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4/%EB%AC%B8%EB%B2%95/markdown/2018/04/08/markdown/>
4. https://gist.github.com/ihoneymon/652be052a0727ad59601
5. https://theorydb.github.io/envops/2019/05/22/envops-blog-how-to-use-md/
6. https://lynmp.com/ko/article/nu86c16d8f09c9fbd8