---
layout: post
comments: true
sitemap:
    changefreq: daily
    priority: 0.8

title: "[github.io] Github Blog 운영 기록"
excerpt: "블로그 깔끔하게 꾸미고 싶다~"

date: 2024-11-22
last_modified_at: 2024-11-24

tags: [BLOG]
---

# Modified
1. 2022-10-23-응용통계학 정리 클릭하면 2022-10-31-응용통계학 기댓값, 분산, 표준편차 포스트로 이동함.
    -> 파일 제목이 같으면 가장 최신 파일 쪽으로 이동하는 듯.
1. [포스트 만든 날짜, 수정 날짜 구분해서 올리고 싶음](/Header_Date_Format_변경하기)
1. [github.io 블로그 구글 검색에 개시하기](/github_google_search_등록)
1. [sitemap 수정하고 나서 post-list에서 이상하게 보임](/github_blog_post_list_layout_fix)
1. google search console에 적용이 끝나면 모든 포스트에다가 sitemap 적용시켜줘야 함

# 수정할 것들
## 기능
1. 카테고리 기능 만들고 싶음
1. 조회수 표시하고 싶음
    간단하게 조사하니 hits 뭐시기 있다는데 이거 말고
    구글 애널리틱스 사용해보고 싶음
1. pagination 적용하기
1. last_modified_at을 xml과 동일하게 last_mod로 바꾸기

## 디자인
1. 글씨 보여지는 곳, 가운데 화면이차지하는 부분이 너무 적음. 양 옆 여백이 너무 넓음.
1. 포스트 만든 날짜, 수정 날짜가 창의 width가 줄어들면 updated date가 두 줄로 변하는 데 차라리 글씨 크기가 줄어들거나 created랑 updated가 가로로 나열되는 게 아니라 세로로 나열되게끔 바꾸고 싶음.
width < x:
    created, updated -> 세로로 나열
    or
    created, updated -> 폰트 사이즈 줄이기
1. h1 ... h6 태그 글자 최소 크기 설정하기
1. page animation 제거할까?