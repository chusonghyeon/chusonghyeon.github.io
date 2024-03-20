---
layout: single
title:  "Django Project - (4)"
categories: "Coding"
tags: [Python, Djnago]
author_profile: false

---

# Django Project - (4)

- Djnago 프로젝트 (인프런 강의 도움)
- Extends/Include/Block를 활용하여 HTML 구축

## 개발 Settings
- IDE: VScode
- OS: Mac OS M1
- Python: 3.12.2
- Django: 5.0.3

# Extends/Include/Block 활용
   - 하나의 html에 모든 내용을 적는것이 아닌 각 층을 구별하여 생성한다.
   - 또한 App폴더 아래에 템플릿을 추가하여 특정 부분만 html로 수정한다.

   1. Template 폴더 밑에 3개의 .html 파일(head, header, footer)과 base.html를 수정한다.


```
<-- base.html 수정 -->
<!DOCTYPE html>
<html lang="ko">

{% include 'head.html' %}

<body>

    {% include 'header.html' %}

    {% block content %}

    {% endblock %}
   
    {% include 'footer.html' %}

</body>
</html>
```

```
<-- head.html -->
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{타이틀 이름 지정}</title>
</head>
```

```
<-- header.html -->
<div style="height: 10rem; background-color: #38df81; border-radius: 1rem; margin: 2rem;">

</div>
```

```
<--  footer.html -->
<div style="height: 10rem; background-color: #38df81; border-radius: 1rem; margin: 2rem;">
        
</div>
```

   2. 결과 

![image-20240320193110107](/images/2024-02-20-Django_Infleran_4/image-20240320193110107.png)


# App 폴더 View 수정
   - 호출하는 부분이 기존에 설정한 base.html이 아닌 프로젝트 폴더 안의 html호출해서 보여준다.
   - Extends를 활용하여 메인 html를 불러오고 block로 구역을 지정하여 html를 완성 시킨다.
   - `mkdir -p {App폴더}/templates/{아무 이름 지정}` -> 이름 지정할때 상위 폴더에 이름과 동일하게 하는것이 가독성이 좋다.

```
<-- 새로운 html 생성-->
{% extends 'base.html' %}

{% block content %}

    <div style="height: 20rem; background-color: #38df81; border-radius: 1rem; margin: 2rem;">
        <h1>
            Testing
        </h1>
    </div>

{% endblock %}
```

   - View.py 수정

```
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.


def helloworld(request):
    return render(request, '{html이 들어가 있는 폴더 이름}/{새로 만든 html 이름}.html')
```



## Reference

[개인 Code 기록 github](https://github.com/chusonghyeon/Django_Project)

[인프런 강의](https://www.inflearn.com/course/%EC%9E%A5%EA%B3%A0-%ED%95%80%ED%84%B0%EB%A0%88%EC%8A%A4%ED%8A%B8/dashboard)

[Django공식페이지](https://www.djangoproject.com/)