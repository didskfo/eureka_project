---
layout: post
title: Google Analytics
subtitle: Google Analytics 추가하기 
categories: etc
banner: "assets/images/banners/googleanalytics.png"
tags: etc
# comments: true
---

## Google Analytics 추가하기 

# 계정, 스트림 생성

[google_analytics](https://analytics.google.com/) 이 사이트에서 계정을 생성한다.
<img src='{{ "/assets/images/" | prepend: site.baseurl | append : "ga1.JPG"}}'>
이 사진의 톱니바퀴 모양을 누르면 
![ga2](assets/images/ga2.JPG) 
이 화면이 나타난다. 데이터 스트림을 클릭하고 웹 항목에 블로그 주소를 입력하여 스트림을 추가한다. 
그렇게 하면 측정 ID가 생성되는데 그 ID를 _config.yml 파일의 google_analytics: [Tracking ID] 부분을 
google_analytics: [G-6JCBQY7VL8] 로 수정한다. 

# 블로그에 붙이기 

측정 ID에는 두 가지 형식이 있는데

G-XXXXXXXX 형식 ⇒ Google 애널리틱스 4를 사용함

UA-XXXXXXXX-X 형식 ⇒ 유니버설 애널리틱스를 사용함

google-analytics.html 파일을 확인해 본 결과 유니버설 애널리틱스를 기준으로 하고 있는 것을 알게 되었다. 

그렇기 때문에 google-analytics.html 파일에 원래 있던 코드를 주석처리하고 
```
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6JCBQY7VL8"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6JCBQY7VL8');
</script>
``` 
이 코드를 추가하였다. 

잘 추가됐는지 확인하는 방법은 커밋한 후에 깃허브 페이지에서 개발자 도구를 켜고 gtag를 입력해본다. 
![ga3](assets/images/ga3.png)
이렇게 뜨면 설치가 되지 않은 것이고 
![ga4](assets/images/ga4.png)
이렇게 뜨면 잘 설치가 된 것이다. 