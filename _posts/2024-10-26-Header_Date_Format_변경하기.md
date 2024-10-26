---
layout: post
title: "Header Date Format 변경하기"
date: 2024-10-26
last_modified_at:
excerpt: ""
tags: [Post]
comments: true
---

# 1. date 문구 추적
scripts.html
compress.html
post.html
3군데에서 date랑 관련된 부분이 나옴

`git push --set-upstream origin header`

# 2. scripts.html 추적
home.html
page.html
post-list.html
post.html
project.html
5군데에서 나옴

# 3. post.html
블로그 글이랑 가장 직접적인 연관이 많은 post.html 먼저 수정해보기로 함.
date 관련된 code
원본: `<h4>Date: {{ page.date | date_to_string }}</h4>`

-> `<h4>Date: {{ page.date | %Y.%m.%d }}</h4>`
결과: Date: 2024-10-17 00:00:00 +0000

-> `<h4>Date: {{ page.date | "%Y.%m.%d" }}</h4>`
결과: Date: 2024-10-17 00:00:00 +0000

-> `<h4>Date: {{ page.date | %Y %m %d %a }}</h4>`
결과: Date: 2024-10-17 00:00:00 +0000

-> `<h4>Date: {{ page.date | date: "%Y %m %d %a" }}</h4>`
결과: Date: 2024 10 17 Thu

* 참고
https://learn.customer.io/personalization/easy-date-formatting-with-liquid
https://shopify.github.io/liquid/filters/date/

# 4. 지금 있는 건 created date니까 updated date를 추가하기로 함
참고: https://moeun2.github.io/blog/jekyll-last-modified-at

-1. 각각의 파일에 코드 추가
Gemfile
```
group :jekyll_plugins do
  gem "jekyll-last-modified-at"
end
```

_config.yml
```
plugins:
  - jekyll-last-modified-at

# Optional. The default date format, used if none is specified in the tag.

last-modified-at:
​    date-format: '%d-%b-%y' #(like "04-Jan-14").
```

post.html
`<h4>Updated: {{ page.last_modified_at | date: "%Y.%m.%d %a" }}</h4>`

결과
Created: 2024.10.17 Thu
Updated:

* 참고
https://tomkadwill.com/adding-last-modified-date-to-jekyll
-> 이 분은 손수 수작업으로 변경하시는 듯

나는 last_modified_at 부분이 있다하면 둘이 같이 나오는 거고
없으면 작성 날짜만 있는거고

post.html
수정
`<h4>Updated: {{ page.last_modified_at | date: "%Y.%m.%d %a" }}</h4>`
->
```
{%- if page.last_modified_at -%}
	<h4>Updated: {{ page.last_modified_at | date: "%Y.%m.%d %a" }}</h4>
{%- endif -%}
```

2024-10-23.md
추가
`last_modified_at: 2024-10-24`

결과
Created: 2024.10.17 Thu
Updated: 2024.10.24 Thu