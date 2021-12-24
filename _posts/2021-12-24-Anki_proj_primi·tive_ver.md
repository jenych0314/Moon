---
layout: post
title: "making Anki_proj part2"
date: 2021-12-24
excerpt: "Anki project is automatic search program (if you enter a word)
Word, pronounce, meaning, and example sentences are ouput using Kor/Eng Dictionary(from naver)."
tags: [post]
comments: true
---

~~지난번에 이어서 내 게으른 생활을 위한 프로그램이다.~~

크롤링을 위한 모듈, 크롤링한 단어, 발음, 뜻/예문을 Anki에 입력하기 위한 텍스트 포맷틀에 맞추어 바꾸는 모듈, 그리고 앞에 두 모듈을 더해 텍스트 파일을 생성하고 TUI 기반 display를 제공하는 main 모듈 총 3가지를 만들었다.

1. [AutomaticSearch](https://github.com/jenych0314/Python/blob/af007d0568f6dc1541eccf60d3f3da4b737b2b91/Anki_proj/automatic_search.py)
    1. init부분에서 'headless'라는 option을 추가해서 웹페이지가 따로 켜지지 않도록 했다.
    2. set_word에서 영단어를 설정한다.
    3. get_word에서는 받은 영단어를 토대로
        1. 네이버 영어사전 사이트에서 영단어를 검색한다.
        2. 첫번째로 나오는 영단어를 선택한다.
        3. 발음과, 뜻, 밑에 있는 예문을 하나 챙겨오도록 했다.
        4. 단어, 발음, 뜻, 예문을 하나의 리스트로 반환하도록 했다.
        5. 혹시 이 과정에서 오류가 발생할 경우, 그 오류가 무엇인지 출력하게끔 했다.
2. [Formatter](https://github.com/jenych0314/Python/blob/af007d0568f6dc1541eccf60d3f3da4b737b2b91/Anki_proj/string_format.py)
    1. 크롤링해서 받은 리스트를 분류별(단어, 발음, 뜻, 예문)로 정리하고 Anki에서는 tag가 추가로 적용되기 때문에 tag리스트를 따로 만들었다.
    2. utf-8로 인코딩을 해야하기 때문에 그 과정에서 깨지는 글자들은 broken_char_in_utf8로 정리해두었다.
        1. 이를 이용해 replace_broken_char에서 깨지는 문자들과 비슷한 문자들로 바꾸는 역할을 한다.
    3. format_pronounce에서는 '발음 미국/영국'에서 '미국/영국'으로 바꾸게끔 해두었다.
    4. format_meaning
        1. 품사별로 나눌 수 있게끔
            ```
            명사
            뜻

            동사
            뜻
            ```
        2. other_lst에 있는 친구들은
            ```
            문형: ~
            유의어: ~
            ```
        3. 뜻 설명과 뜻이 두 줄에 걸쳐서 나뉘어져 있는 경우  
        `뜻 설명//뜻`
    5. format_ex_sentence
        1. 예문에서는
        ```
        영어 예문
        발음 듣기
        반복 듣기
        영어 해석
        영어 예문 출처
        ```
        에서
        ```
        영어 예문
        영어 해석
        ```
    6. format_tag
        1. meaning에서 나와있는 품사들을 #을 붙여서 tag 형식으로 만들어서 리스트에 추가
        2. 숙어에 경우는 위에 있는 품사들이 적용되지 않으므로 따로 #숙어로 만들어서 리스트에 추가
3. [TUI main](https://github.com/jenych0314/Python/blob/af007d0568f6dc1541eccf60d3f3da4b737b2b91/Anki_proj/Anki_Proj_TUI.py)
    1. file_write
        1. 파일명은 '날짜-Engword.txt'로 정했고
        2. 기존의 파일이 있을 경우에는 덧붙여 쓰고 없을 경우에는 새 파일을 만들게끔 했다.
    2. 프로그램을 시작하면
    ```
    Enter the English word
    (If you want to quit then pls enter the \'quit\'.)
    -> 
    ```
    을 볼 수 있고, quit을 입력하면 종료한다.  
    영어 글자가 아닐 경우(숙어일 경우를 대비해서 스페이스바는 내버려두게끔 했다.) 다시 입력하라는 문구와 함께 다시 Enter~가 보이고, 그 외에는 잘 입력되는 모습이 보였다.  
    입력된 부분을 직접 텍스트 파일을 열어서 확인할 수도 있지만, 입력된 부분이 어떻게 되어있는지 출력되기에 바로 확인할 수 있다.  

4. 당장 생각나는 개선점
    1. 경로를 절대 경로에서 상대 경로로 바꿔야 하지 않을까
    2. tag 부분이 8품사와 숙어 말고 다른 것도 필요하지 않을까
    3. format하는 부분, 좀 더 시간복잡도를 줄일 수 있지 않을까