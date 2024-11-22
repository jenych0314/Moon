---
layout: post
comments: true
title: "[github.io] Github Blog 수정한 것들/할 것들"
excerpt: ""
date: 2024-11-22
last_modified_at: 
tags: [BLOG]
sitemap:
    changefreq: daily
    priority: 0.8
---

# Fixed
1. 2022-10-23-응용통계학 정리 클릭하면 2022-10-31-응용통계학 기댓값, 분산, 표준편차 포스트로 이동함.
    -> 파일 제목이 같으면 가장 최신 파일 쪽으로 이동하는 듯.
1. 포스트 만든 날짜, 수정 날짜 구분해서 올리고 싶음

# 수정할 것들
3. 글씨 보여지는 곳, 가운데 화면이차지하는 부분이 너무 적음. 양 옆 여백이 너무 넓음.
5. 게시판 기능 만들고 싶음
7. 조회수 표시하고 싶음
8. 포스트 만든 날짜, 수정 날짜가 창의 width가 줄어들면 updated date가 두 줄로 변하는 데 차라리 글씨 크기가 줄어들거나 created랑 updated가 가로로 나열되는 게 아니라 세로로 나열되게끔 바꾸고 싶음.
width < x:
    created, updated -> 세로로 나열
    or
    created, updated -> 폰트 사이즈 줄이기
9. last_modified_at을 xml과 동일하게 last_mod로 바꾸기
10. google search console에 적용이 끝나면 모든 포스트에다가 sitemap 적용시켜줘야 함
11. sitemap 수정하고 나서 post-list에서 이상하게 보임
<img src = "https://cdn.jsdelivr.net/gh/aliquis-facio/aliquis-facio.github.io@master/_image/2024-11-22-3.png?raw=true">
-> 근데 또 모든 포스트가 저리 보이는 건 아님
-> md 윗부분 ---로 감싸져있는 설정 부분이 제대로 돼있지 않는 포스트들이 그런가 하고 제대로 써봄.
-> google search 등록하기, github blog 수정한 것들/할 것들만 이상하게 나옴
-> excerpt 안 쓴 것들인가?
-> 아에 ---로 작성안 해놓은 것들은 파일 제목이랑 내용 첫 줄이 합져져서 표시됨
<img src = "https://cdn.jsdelivr.net/gh/aliquis-facio/aliquis-facio.github.io@master/_image/2024-11-22-4.png?raw=true">
-> --- 채워넣고 excerpt를 ""로 넣어봄