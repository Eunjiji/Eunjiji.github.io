---
layout: post
title: "[airbnb-clone] Django setting"
categories: Django
tags: [python, Django]
---

<div class="message">
 Django를 이용한 Airbnb clone 코딩을 진행 해보려고 한다!
</div>


## Django를 쓰는 이유

Python의 많은 프레임 워크 중에서 Flask와 Pyramid 가 아닌 **Django**를 사용 하는 이유는??

- Flask와 pyramid는 아주 가벼운 프레임 워크로 미니멀하게 꼭 필요한 정도의 기능만 제공한다. 
- 간단한 것들은 Django 보다 빨리 만들수는 있지만 규모가 커질수록 많은 기능들을 차곡차곡 구현해야 하기 때문에 오히려 더 오래걸린다.
- Django는 그에 비해 거대한 프레임 워크로 많은 기능(관리자 페이지, 사용자 인증 등)을 포함하고 있어 개발 할 때 손이 좀 덜 간다.
- Django는 많은 기능이 필요로 하는 프로젝트를 진행할때 적합하다.
- 적은 기능들을 빠르게 구현하는건 Flask, Pyramid 쪽이 나을 수도 있음.

이러한 이유들로 Django를 이용해 Airbnb clone coding을 진행 해보려고 한다.

## Setting

* 프로젝트 폴더 생성
{% highlight python %}
mkdir airbin-clone
{% endhighlight %}

* pipenv(pip + virtualenv) 설치 (가상환경 세팅)
    1. pipenv는 자동으로 virtualenv 환경을 생성해준다.
    2. requirements.txt 대신 Pipfile와 Pipfile.lock 사용
    3. 패키지를 설치/삭제하면 자동으로 Pipfile에서 추가/삭제 된다.
{% highlight python %}
pip install pipenv
{% endhighlight %}



* 프로젝트 가상환경 생성
{% highlight python %}
# three는 파이썬 버전을 의미함
pipenv --three
{% endhighlight %}

* 프로젝트 가상환경 접속
    - 프로젝트 패키지 설치시 가상환경으로 들어가서 설치를 진행해야한다.  
    (그래야 프로젝트를 다른 사람이 받아도 설정이 수월함)
{% highlight python %}
# 꼭 가상환경 속으로 들어와서 세팅을 진행해야함!!
pipenv shell
{% endhighlight %}



### Git 연동
{% highlight python %}
# git readme, gitignore 파일 생성
touch README.md
touch .gitignore

# git 프로젝트 생성
git init
git remote 프로젝트 주소
git add .
git commit -m "Initial commit"
git push -u origin/master

{% endhighlight %}