## 첫번째 도전
https://blog.naver.com/jenych0314/222556824348

## 두번째 도전
<https://taylantatli.github.io/Moon/about/>
에 나와있는 setup guide를 따라 함.  
-> 나눔고딕 폰트 적용까지 성공해서 한글 입력까지 가능했지만 댓글 기능에서 막혀서 레포지토리 지움.  

## 세번재 도전
똑같이 setup guide를 따라해서 댓글 기능부터 추가했음.  
-> 나눔고딕 폰트에 관한 코드를 똑같은 위치에 입력함.  
-> 로컬 레포지토리를 변경해도 github.io에 변경이 늦게되는 듯함.  

## 네번째 도전
favicon image 변경  
둥글고 어두운 분위기를 생각하다가 이상한 나라의 앨리스에서 나오는 체셔캣이 생각남.  
검정톤 깔끔한 분위기의 이미지로 고름.  
이제 원래 있던 이미지 파일들을 전부 찾아서 이미지 크기와 이름들을 똑같이 맞춰서 찾은 이미지를 변경함.  
아직 남은 이미지가 하나 있지만 원하는 분위기의 이미지를 선택했으나 적용하지 않음.  
실제로 적용시키니까 맘에 들지 않아서 다른 체셔캣 이미지로 바꾸면서 시도하는 중.  
뒤에 깔리는 이미지 변경 중.  

## 다섯번째 도전
#### 참고
    1. <http://loustler.io/etc/github_pages_blog_google_analytics/>
    2. <https://velog.io/@eona1301/Github-Blog-%EB%B0%A9%EB%AC%B8%EC%9E%90-%ED%86%B5%EA%B3%84Analytics%ED%95%98%EA%B8%B0>
    3. <https://nicecarrot2.tistory.com/34>
    4. <https://analyticsmarketing.co.kr/digital-analytics/google-analytics/1850/>

google analytics 추가
google analytics 가입 후 tracking id 챙겨서 config.yml에
"google:
    analytics: tracking_id"
tracking_id 부분에 추가함.

기존에 있던 구글 애널리틱스에 관한 코드를 변경함.  
### 전
```html
<!-- Asynchronous Google Analytics snippet -->
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
    (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');
  ga('create', '{{ site.google.analytics }}', 'auto');  
  ga('require', 'linkid', 'linkid.js');
  ga('send', 'pageview');
</script>
```

### 후
```html
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-QE0BFF2TLD"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-QE0BFF2TLD');
</script>
```

기존에 있던 코드일 때는 구글 애널리틱스 보고서에서 사용자가 counting되지 않았는데, 구글 애널리틱스에서 제공하는 코드로 변경하고 나서는 사용자가 잘 counting되는 모습을 보여줌.
