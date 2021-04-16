---
layout: post
title: "[airbnb-clone] Django setting"
categories: Django
tags: [python, Django]
---

# Django 환경설정

### Pycharm 이용한 환경설정

### 1. project 생성

- cmd나 git bash를 이용하여 project를 생성할 디렉토리에 접속 후 아래 명령어로  프로젝트 생성

```python
django-admin startproject [project 이름]
```

→ [ project 이름 ] 디렉토리 + [manage.py](http://manage.py) 생성완료 

→ 해당 파일을 Pycharm으로 open

![Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled.png](Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled.png)

### 2. 서버실행 및 연동 확인

- terminal에 manage.py가 있는 디렉토리로 이동 후 아래 명령어 입력

```python
python manage.py runserver
-> localhost:8000 에 아래와 같은 화면이 뜨면 연동 성공
```

![Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%201.png](Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%201.png)

### 3. 앱만들기

- 앱은 프로젝트의 구성 단위 보통 기능별로 세분화함

```python
python manage.py startapp [ app 이름 ]
```

![Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%202.png](Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%202.png)

### 4. templates 생성 (html 파일 생성)

- 위에서 생성한 app 디렉토리 하위폴더로 templates를 생성후 원하는 html을 생성합니다.

![Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%203.png](Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%203.png)

### 5. 함수 생성

- app의 안에 views.py에서 동작을 할 수 있게 해주는 함수 생성

```python
def index(request):
		#request를 받아서 index.html을 불러줌
    return render(request, 'index.html') 
```

### 6. url 설계

- url은 해당 url로 접근 시 정의되어있는 함수를 views.py에서 찾아 실행시킨다.
- 함수를 실행시켜야 하기 때문에 app에 있는 views를 import 해줘야함

```python
from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
		# localhost:8000/admin/ 접근 시 admin page 열림
    path('admin/', admin.site.urls),
		
		# localhost:8000/ 접근 시 views.py의 index 함수 호출
    path('', views.index, name='index') 
]
```

### 7. 결과확인

![Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%204.png](Django%20%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%2055bd28a16cdd430aaf3346d79accc4e3/Untitled%204.png)