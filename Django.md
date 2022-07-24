# Django

## 1. Django 란?
파이썬으로 만들어진 무료 오픈소스 웹 애플리케이션 프레임워크(web application framework)입니다.

<br>

## 2 - 1. 프레임 워크란?
프레임워크란, 소프트웨어의 구체적인 부분에 해당하는 설계와 구현을 재사용이 가능하게끔 일련의 협업화된 형태로 클래스들을 제공하는 것입니다.

<br>

## 2 - 2. 프레임 워크 vs 라이브러리
프레임워크를 자동차에 비교하자면 자동차의 뼈대정도? 하지만 라이브러리는 자동차의 기능을 하는 부품이라고 비유 할 수 있다. 프레임워크는 나의 코드를 프레임워크에 맞춰야한다면, 라이브러리는 자유롭게 내가 사용한다는 점에서 주체의 차이도 보여진다.

<br>

## 3. Django 개발 환경

<p align="center">
    <img src = "../Pictures\Django_1.png">
</p>

Django를 쓰기 위해서는 Django와 파이썬 버전을 가상환경으로 독립적으로 만들어서 관리한다. 그 이유는 무엇일까?

패키지도 개발에 따라 변화하기 때문에, 일정한 버전을 정해두고 개발을 시작합니다. 즉 각 프로젝트에 맞는 버전에 맞춰서 개발을 해 나아가야지 나중에 개발 환경에 업데이트가 생겨도 차질없이 개발을 진행할 수 있습니다.

각 개발 환경 설치와 가상환경에 따라서는 타 블로그를 참조 할 것

<br>

## 4. Django 사용법

## 4 - 1. Django 프로젝트 생성
```
django-admin startproject {프로젝트 이름}
```
현재 저는 vsc를 통해서 연결하여 작업하기 때문에 
```
code .
```
를 치게 되면 vsc를 통해서 해당 디렉터리를 관리하고 작업 할 수 있습니다.

<br>


## 4 - 2. Django 서버 실행
```
django-admin runserver {ip:port}
python manage.py runserver {ip:port}
# {ip:port} 생략시 현 컴퓨터가 서버가 된다.
```
서버의 주소가 나오고 서버가 실행 된다.

## 4 - 3. 프로젝트의 구조
```
proj/ #프로젝트명
    manage.py
    proj/ # 프로젝트명
        __init__.py
        settings.py
        urls.py
        wsgi.py
```
> Project Root : 
최상위 디렉토리인 프로젝트 명(codeit_proj) 디렉토리는 Project Root라고 하고 우리 프로젝트의 전체 파일이 들어 있는 디렉토리 입니다.

> manage.py :
manage.py는 하나의 Django 프로젝트를 생성하면 자동으로 만들어지는 프로젝트 관리를 위한 명령 유틸리티입니다. Django 앱을 만들거나, 데이터베이스 관련 기능을 수행하거나, 개발 서버를 실행하는 등의 여러기능을 실행 할 수 있습니다.

> ProjectApp (Django Root) : 
Project Root 안에 있는 프로젝트 명(codeit_proj) 디렉토리는 Django 프로젝트를 위한 여러 파일이 담겨 있는 디렉토리 입니다.

> __ init __.py : 
__init__.py 파일이 포함된 디렉토리를 Python의 패키지로 인식하게끔 하기 위해서 사용합니다. python 3.3 이후 버전부터는 이 파일이 없어도 패키지로 인식되지만 하위 버전 호환을 위해 작성해 주는 것이 좋습니다.

>  settings.py : 
settings.py 는 Django 프로젝트의 여러 가지 설정을 담고 있는 파일입니다.

> urls.py : 
urls.py 는 Django 프로젝트로 들어온 url을 보고 알맞은 로직(View)으로 연결해주는 역할을 하는 파일입니다. Django 프로젝트의 목차라고 할 수 있습니다.

> wsgi.py : 
wsgi.py 의 WSGI는 WebServer Gateway Interface의 약자로 파이썬에서 웹 통신을 하기 위한 일종의 약속입니다. 

<br>


## 4 - 4 Django 의 app과 생성

Django에서 프로젝트는 웹서비스의 전체 라고 보면 되고, 거기서 app은 기능을 나타내는 단위라고 생각 하면 된다.

```
# 앱 생성 방법 
python manage.py startapp {생성할 App 이름}


생성된 Django App 구조

{app_name}/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
```

>  admin.py : 
각각의 앱을 Django의 관리자 기능과 연결하거나 관리자 기능에 대해 설정을 하는 파일입니다.

> apps.py : 
각각의 App마다 추가적인 기능 및 설정을 넣어 주기 위한 파일입니다.

> migrations 디렉토리 : 
Django 앱의 데이터 구조에 대한 변경 사항인 migration 파일이 저장되는 디렉토리 입니다.

>  models.py : 
앱에서 사용하는 데이터 구조를 정의하고 데이터베이스와의 소통을 담당하는 파일입니다. 

> tests.py : 
앱에 대한 테스트 코드를 작성하는 파일입니다. 테스트는 말 그대로 Django 프로젝트의 모든 기능이 의도한 대로 잘 동작하는지 체크하는 것을 말합니다. 그리고 이런 테스트는 작은 함수 하나를 체크하는 테스트부터 여러 함수의 상호작용이 있는 전반적인 큰 로직을 테스트하는 것까지 다양한 크기의 테스트가 있습니다. 그렇기 때문에 프로젝트를 모두 완성한 다음 테스트를 준비하는 것이 아니라 앱 별로 작은 단위의 자동화된 테스트를 미리 만들어서 프로젝트 전체에 대한 테스트가 효율적으로 이루어질 수

> views.py
앱에서 어떤 기능을 할지에 대한 메인 로직을 담당하는 파일입니다. 

## 4 - 5 Djagno URL 
일반적으로 실행된 프로젝트의 URL은 settings.py 에 있는 ROOT_ULCONF 를 따라 가게 됩니다.

<p align="center">
    <img src = "../Pictures\Django_2.png">
</p>

여기서 costaurant.urls 파일로 따라가라 라고 했으니 그 파일을 열어보게 되면

<p align="center">
    <img src = "../Pictures\Django_3.png">
</p>

다음과 같이 나온다. 현 URL에서 뒤에 \admin 이나 \foods를 적게 된다면 url은 또 해당 파일을 찾아 가게 될 것입니다. 만약에 url/foods/로 접근 하였다고 해봅시다. 그러면 foods.urls 을 찾아가라고 했으니 따라가게 되면,

<p align="center">
    <img src = "../Pictures\Django_4.png">
</p>

다음과 같이 나옵니다. 이번에는 vieew.index 파일을 찾아가라고 하였으니, 

<p align="center">
    <img src = "../Pictures\Django_5.png">
</p>

도달하게 되면 화면에 보여지는 페이지가 어떻에 구성되었는지를 확인 할 수 있습니다.


<br>

## 4 - 6 URL 작성
```
urlpatterns=[
    path('foods/', views.index),
    path('foods/banana/', views.fruit),
] 
```
여기서 중요한 점은 슬래시가 붙은 주소는 '디렉토리'를 가리키고 슬래시가 없는 주소는 '파일'을 가리키도록 만들어 졌다 라는 점 입니다. 이에 유의해서 슬래시를 작성하여야 합니다.

<br>


## 4 - 7 Django의 템플릿과 렌더링
Django에서의 Template(템플릿)은 화면 구성을 담당 하는 것을 의미합니다. 예를들어서 HTML 파일 같은것이 있습니다.
이런 템플릿을 유저에게 보여주는 행위를 템플릿을 Render한다 라고 합니다. 

<p align="center">
    <img src = "../Pictures\Django_5.png">
</p>

현재 httpresponse 대신에 html 파일을 렌더링 해보겠습니다. 


<p align="center">
    <img src = "../Pictures\Django_6.png">
</p>

일단 templates/foods 라는 디렉터리를 foods 디렉터리 아래에 만들고 아래에 index.html 을 만들어 랜더링 하고 싶은 내용을 기입합니다. 그리고 render 함수를 이용하여 render(request, {경로})
를 기입해주게 되면 해당 템플릿을 찾아 랜더링을 해줍니다.

<br>


## 4 - 8 render()
```
render( request, template_name, context=None, content_type=None, status=None, using=None )
```
render 함수는 인자로 주어진 템플릿을 사전형(dict) 인자인 context와 결합해서 렌더링을 거친 다음 HttpResponse 객체로 반환하는 함수입니다. 쉽게 말하면 인자로 넘겨주는 템플릿과 context 데이터를 합쳐서 HttpResponse 객체로 돌려주는 함수입니다. 

<br>


## 4 - 9 Django MVT 아키텍처
MVT란 Model, View, Template를 줄인 개념이다. 

> Model : 데이터 구조 생성, 데이터베이스와 소통

> View: 웹 사이트의 로직을 담당, Model 과 Template 사이를 연결

> Template: 웹 사이트의 화면 구성을 담당, 매번 바뀌는 동적인 화면을 구성

<p align="center">
    <img src = "../Pictures\Django_7.png">
</p>

<br>

## 4 - 10 아키텍처 패턴

아키텍처 패턴(Architecture Pattern)은 소프트웨어 내부에 존재하는 구조적인 패턴을 말하는데요. 쉽게 말해서 오랜 시간 개발된 다양한 소프트웨어들이 결국 내부적으로 비슷한 구조를 갖게 되는 경우가 많다는 점이 발견되었고 발견된 구조들을 일반화해서 범주를 나눠 놓은 것입니다.

대표적인 10가지 아키텍처 패턴은 아래와 같습니다.

1. 계층화 패턴(Layered pattern)
2. 클라이언트-서버 패턴 (Client-server pattern)
3. 마스터-슬레이브 패턴 (Master-slave pattern)
4. 파이프-필터 패턴 (Pipe-filter pattern)
5. 브로커 패턴 (Broker pattern)
6. 피어 투 피어 패턴 (Peer-to-peer pattern)
7. 이벤트-버스 패턴 (Event-bus pattern)
8. MVC 패턴 (Model-view-controller pattern)
9. 블랙보드 패턴 (Blackboard- pattern)
10. 인터프리터 패턴 (Interpreter pattern)

이중에서도 클라이언트 - 서버, MVC 패턴에 대해서 잠깐 보겠습니다. 

> 클라이언트 - 서버 패턴
먼저 클라이언트-서버 패턴입니다. 앞에서 배웠던 클라이언트와 서버 기억하시나요? 클라이언트는 서비스를 요청하는 쪽이고 서버는 요청을 받아서 서비스를 제공하는 쪽이었죠? 소프트웨어도 이처럼 내부적으로 두 개의 구조로 나눠서 서버는 클라이언트의 요청을 기다리고 있다가 클라이언트로부터 요청이 들어오면 요청에 맞는 서비스를 제공하도록 하는 거죠. 우리 주위에서 많이 볼 수 있는 패턴으로 인터넷 웹 사이트, 온라인 게임 등이 모두 클라이언트 - 서버 패턴에 해당합니다.

> MVC 패턴
MVC 패턴은 하나의 소프트웨어를 역할에 따라 Model, View, Controller 세 가지의 파트로 나눠서 개발하는 패턴입니다. 하나씩 간단히 살펴보면 Model은 데이터를 저장, 보관하고 View는 사용자에게 보여지는 부분을 담당하며 Controller는 사용자의 입력을 받아서 내부 로직을 처리합니다. 이렇게 역할에 따라 분리해서 개발하게 되면 분업이 가능해지고 이로 인해 프로그램을 더 빠르고 완성도 있게 개발할 수 있습니다. 더해서 기능별로 나누어져 있으므로 추후 유지 보수가 용이하겠죠.

MVC 아키텍처와 MVT 아키텍처
MVC에 대한 이야기를 듣다 보니 무언가 생각나지 않으신가요? 바로 우리가 배웠던 Django의 MVT 구조와 비슷한 형태를 보이고 있습니다. 
MVT는 데이터 구조를 만들고 데이터베이스와의 소통을 담당하는 Model, 로직을 담당하는 View, 그리고 화면 구성을 담당하는 Template 이렇게 세 가지로 나누어져 있는 구조였는데 이러한 MVT 구조는 MVC 구조를 기반으로 만들어졌습니다. 차이점이 있다면 Model이 하는 역할은 그대로지만 MVC 아키텍처의 View가 하는 역할을 Template이 하고 Controller가 하는 역할을 View가 맡아서 처리합니다.
```
MVC 구조           MVT 구조 (Django)
Model       ->    Model
View        ->    Template
Controller  ->    View
```
그렇다면 왜 Django는 MVT 라는 구조를 만들었을까요? 기존 MVC 아키텍처에서는 Controller가 중심에서 모든 요청을 맡아 처리하지만 MVT 아키텍처에서는 실제로 요청을 받아들이는 부분, 즉 기존의 MVC의 Controller가 했던 역할의 일부를 분리해서 Django 프레임워크가 직접 처리합니다.

덕분에 개발자는 서비스에 중요한 Model, View, Template에 집중하고 나머지 모든 부분은 Django 프레임워크에 맡겨서 훨씬 편리하고 빠르게 개발할 수 있습니다. 이와 같은 개발의 간편함이 Django 프레임워크가 MVT 아키텍처를 통해 추구하고자 하는 것입니다.

<br>

## 4 - 11 Django 정적파일 관리하기
정적파일이란 웹 페이지를 렌더링 하는 과정에서 필요한 추가적인 파일을 의미한다.

<p align="center">
    <img src = "../Pictures\Django_8.png">
</p>

이번에는 static/{app이름} 디렉터리 안에 imanges, fonts, css 등의 파일을 집어 넣습니다. 그런 다음 템플릿 안에 있는 index.html 맨 위 부분에 {% load static %} 을 집어넣습니다.

<p align="center">
    <img src = "../Pictures\Django_9.png">
</p>

그리고 받아 오고 싶은 여러 정적인 이미지 파일이나, 폰트 등을 가지고 오고 싶을 떈, 

<p align="center">
    <img src = "../Pictures\Django_10.png">
</p>

다음과 같이 변경합니다. 

<br>

## 4 - 12 Django Template 와 static 폴더 구조 

<p align="center">
    <img src = "../Pictures\Django_11.png">
</p>

template 와 static 폴더의 구조를 보면 그 안에 app의 이름이 함께 들어있는 특이한 구조를 가진다. 왜 이런 샌드위치 구조를 가질까?

<p align="center">
    <img src = "../Pictures\Django_12.png">
</p>

다음과 같이 앱A와 앱B를 만들고 각각의 템플릿 바로 밑에 index를 만들어서 접근하게 되면 앱B에서 만든 index도 a의 index를 가리키게 되는데 그 이유는 아래와 같다.

<p align="center">
    <img src = "../Pictures\Django_13.png">
</p>

프로젝트 아래의 settings.py 를 보면 TEMPLATES 라는 함수가 있는데, 이는 자동으로 templates 라는 폴더를 찾아서 랜더링을 도와주는 함수이다. 이때 template 경로에 있는 index.html 파일이 2개이기 때문에, 위에 같은 일이 벌어지게 된다. 따라서 이를 방지하기 위해서 templates 와 static 아래에는 항상 app 이름의 디렉터리 하나를 더 만들고 샌드위치 구조를 만들어야 접근하는데 용이하다.

<br>

## 4 - 13 Django의 템플릿 언어
정적이 아닌 동적으로 웹페이지를 움직이는데 사용하는 언어라고 할 수 있다.

템플릿 언어에는 템플릿 변수, 템플릿 태그, 템플릿 필터, 템플릿 주석이 존재한다.

> 템플릿 변수 : {{변수명}}
* 우리가 지정한 데이터로 변환
* view 에서 넘겨 받은 값으로 변환
```
value = {
    title : "django"
    version : 1. 0
}
접근할때는 codeit.title
```
> 템플릿 필터 : {{변수명 | 필터}}
* 템플릿 변수를 특정 형식으로 변환 

> 템플릿 태그 : {% 태그 %} {% end태그 %}
* 템플릿 작성에 용이하게 하기 위해 사용
```
{% for %}
{% end for %}
{% if %}
{% else %}
{% endif %}
```
> 템플릿 주석 : 
* 주석 용도로 사용
```
{# 내용 #}
```

<br>

## 4 - 14 중복되는 템플릿 코드 없애기
{%block%}, {%extends%} 를 사용하여 템플릿 상속을 통해서 사용한다.

<p align="center">
    <img src = "../Pictures\Django_14.png">
</p>

일단 index.html의 뼈대를 가져올 html 파일인 base.html을 템플릿에 만든다.
그리고 index.html에 있는 모든 내용을 복사해 base.html 에 담는다.

<p align="center">
    <img src = "../Pictures\Django_15.png">
</p>

이제 base는 기본 뼈대가 되고 변경되는 내용을 index.html에 담을 준비를 한다.
그 행위는 아래와 같다. 

<p align="center">
    <img src = "../Pictures\Django_16.png">
</p>

이러면 부모 템플릿이 준비되었다고 할 수 있다. 

<p align="center">
    <img src = "../Pictures\Django_17.png">
</p>

이제 index.html로 넘어와서 부모 템플릿의 내용을 삭제하고 헤더 첫줄에
{% extends '부모 템플릿 경로' %}을 적어준다 맨 첫줄에 적어야 한다.
그리고 나서 아까 있던 블럭들의 내용을 채우면 된다. 그 예는 아래와 같다.

<p align="center">
    <img src = "../Pictures\Django_18.png">
</p>

만약에 자식 템플릿에 내용이 없다면, 부모 템플릿의 내용을 따라 간다.

<br>

## 4 - 15 계속 변하는 동적 웹 페이지 만들기

만들기 전에 앞서 MVT 구조를 보자.

<p align="center">
    <img src = "../Pictures\Django_19.png">
</p>

여기서 우리는 View 에서 템플릿으로 가고 그것을 화면으로 보내는 부분을 건드려볼 예정이다. 

일단 날짜를 현재에 맞게 만들어주도록 만들어 보겠다. 일단 템플릿은 views 에서 쏴주니까, views 에서 함수를 만든다.

<p align="center">
    <img src = "../Pictures\Django_20.png">
</p>

datatime 라이브러리를 통해 today라는 변수에 날짜를 담았으니 이것을 템플릿으로 보내주면 된다. 이때 값을 넘겨주는 방법은 render 함수에 세 번째 파라미터로 넘겨주면 되며 이때 값은 dict 형태로 넘겨주어야 한다. 따라서 그것을 하여 만들게 되면, 

<p align="center">
    <img src = "../Pictures\Django_21.png">
</p>

자 이렇게 하면 해당 템플릿에 정보가 가게 되고 그 정보를 사용하는 변수인 템플릿 변수를 사용하여 처리 하면 된다. 처리방법은 아래와 같다.

<p align="center">
    <img src = "../Pictures\Django_22.png">
</p>


<br>


## 4 - 15 Django의 우아한 URL

Django는 URL의 형태를 우아하게 만들수 있는데, 이를 우아한 URL이라고도 한다. URL을 우리가 원하는 형태로 구성할 수 있으며, 직관적이고 알아보기 쉬운 구조를 가졌다. 만약에 chicken 이라는 새로운 html을 만들고 그를 연결하고자 한다면,

<p align="center">
    <img src = "../Pictures\Django_23.png">
</p>

에 view까지 만들어 처리하면 되지만, 모든 메뉴에 대한 상세 페이지를 만들어야 한다면 많은 반복이 필요하다. 따라서 이를 동적으로 정리할 필요가 있는데 이를 동적 URL이라고 한다. 이를 사용하는 방법은 다음과 같다.

<p align="center">
    <img src = "../Pictures\Django_24.png">
</p>

여기서 <str:food>의 인수가 views에 넘어가게 되는데 이를 받아서 처리 할수 있다. 

<p align="center">
    <img src = "../Pictures\Django_25.png">
</p>
<p align="center">
    <img src = "../Pictures\Django_26.png">
</p>

이러면 이제 menu/"아무이름" 을 치게 되면 화면에 url에서 받은 변수의 이름이 화면에 나타나게 된다. 

<br>

## 4 - 16 django에서의 에러페이지 처리
일반적으로 상태코드를 통해 어떤 에러가 떳는지 확인할수 있으며, 그에 따라 적당한 대처가 가능하다 장고에서도 이런 에러를 처리하기 위해서 자체적으로 툴을 제공하고 있다. 

```
from django.shortcuts import render
from django.http import HttpResponse
from datetime import datetime

# Create your views here.
def index(request):
    today = datetime.today().date()
    context = {"date" : today}
    return render(request, 'foods/index.html', context=context)

def food_detail(request, food):
    context = dict()
    if food == "chicken":
        pass
    else:
        raise Http404("이런 음식은 없다구요!")
    
    return render(request, 'foods/detail.html', context=context)
```
처럼 치킨일 경우 해당 페이지를 처리하지만, 만약 치킨이 아닌 다른 것이 올 경우 
raise Http404("")를 사용하면된다. 여기서 raise는 파이썬에서 지정한 에러를 강제로 발생시키는 함수이다. 

<br>

## 4 - 17 django의 Model 이해

<p align="center">
    <img src = "../Pictures\Django_27.png">
</p>

각각의 데이터가 어떤 형식으로 들어갈지 미리 정하는 것을 데이터 모델링이라고 한다. 즉 요구 사항에 맞게 짜는 것을 의미한다.

<p align="center">
    <img src = "../Pictures\Django_28.png">
</p>

이런 데이터들을 저장하는 곳이 데이터베이스며 데이터 베이스 종류로는 위와 같은 것들이 있다.

여기서 데이터들을 추가, 조회, 수정, 삭제를 거쳐야 하는데 이 특성을 (Create Read Update Delete) 라고도 하며 SQL문으로 조절한다. 

하지만 SQL문을 새로배우기에는 빠듯하기 때문에 장고에서는 ORM(Object-Relational Mapper)을 통해서 소통 할 수 있도록 해준다.

즉 이런 그림이 나온다고 할 수 있다.


<p align="center">
    <img src = "../Pictures\Django_29.png">
</p>

<br>

## 4 - 18 django의 Model 작성

만약 음식을 데이터에 저장하고 사용하고 싶으면 다음과 같이한다. 
```
from django.db import models

# Create your models here.
class Menu(model.Model):
     name = models.CharField(max_length=50)
     description = models.CharField(max_length=100)
     price = models.IntegerField()
     img_path = models.CharField(max_length=255)

     def __str__(self):
         return self.name
```
여기서 Menu클래스는 model.Model을 상속받아서 한다는 의미이고, models.TYPEField(길이) 를 통해서 각각을 구성한다. 그런 다음 장고에게 모델이 바뀌었다라는것을 알려주어야 한다.

<p align="center">
    <img src = "../Pictures\Django_30.png">
</p>

해당 명령어는 python - makemigrations 을 통해서 모델을 등록하고 migrate를 통해서 모델을 생성하는 절차를 밞는다.

<br>

## 4 - 18 마이그레이션(migrations)이란?

아까 전에 했던 내용을 살펴 보면 모델을 등록하고 생성하는 작업이었다. 

<p align="center">
    <img src = "../Pictures\Django_31.png">
</p>

마이그레이션(Migration)은 모델(Model)의 변경 사항 즉 Django 프로젝트의 데이터 구조 변경 사항을 관리하기 위한 Django만의 관리 방법입니다. 변경될 때마다 히스토리를 하나씩 만들어 두고 마치 블럭을 갈아 끼우듯 생성한 히스토리를 실제 데이터베이스에 반영하는 거죠. 그리고 이 모든 과정은 Django의 ORM(Object-Relational Mapping)을 통해 진행됩니다.

우리는 앞에서 4가지 명령어를 사용했는데 여기서 간단히 다시 짚어보겠습니다.

* makemigrations
* migrate
* showmigrations
* sqlmigrate

```
python manage.py makemigrations
```
모델의 변경 사항을 인식해서 새로운 마이그레이션을 만듭니다. 이때 마이그레이션은 각 앱 디렉토리 내 migrations 디렉토리 안쪽에 생성됩니다.

```
python manage.py migrate
```
생성된 최신 버전의 마이그레이션을 데이터베이스에 반영합니다. 만약 이전 마이그레이션으로 되돌리고 싶다면 python manage.py migrate {앱 이름} {되돌릴 마이그레이션 번호}를 사용할 수 있습니다.
```
python manage.py showmigrations
```
현재 django 프로젝트의 모든 마이그레이션과 반영 상태를 나타냅니다. 만약 특정 앱에 대한 것만 보고 싶다면 python manage.py showmigrations {앱 이름}을 사용할 수 있습니다.
```
python manage.py sqlmigrate {앱 이름} {마이그레이션}
```
인수로 넘겨준 마이그레이션이 ORM을 통해 변경된 SQL문을 출력합니다. sqlmigrate를 통해 모델이 의도한 대로 SQL문으로 변경되어 데이터베이스에 반영되었는지 확인할 수 있습니다.

<br>

## 4 - 18 모델 데이터 CRUD
python manage.py shell 
을 통해서 쉘을 킵니다. 

<br>

1. 데이터 추가하기 (Create)

데이터를 추가하기 위해서는 import를 이용해서 먼저 사용할 Model을 불러 와야 합니다.
```
from {app_name}.models import {model}

data_model = {model}.objects.create( {field_name}=value, ... )
# example
# food = Food.objects.create(price=10000)
```
2. 데이터 조회하기 (Read)
   
데이터 모델의 모든 데이터를 가져오기 위해서는 all()을 사용합니다.
```
# 모든 데이터 조회하기
data = {model}.obejcts.all()

# 하나의 데이터 조회하기
data = {model}.objects.get(field=value)

# 조건에 맞는 여러 데이터 조회하기
data = {model}.objects.filter(field=value)

# 정렬해서 데이터 조회하기
data = {model}.objects.order_by('field_1', '-field_2')
field_1을 기준으로 오름차순으로 정렬하고 
그 결과를 다시 field_2를 기준으로 내림차순으로 정렬합니다.

# 데이터의 개수 세기
rows = {model}.objects.count()

# 조건을 걸어서 조회하기 

__exact, __iexact
__exact는 대소문자를 구분해서 조건과 정확히 일치 하는지를 체크하며
__iexact는 대소문자를 구분 하지 않고 일치하는 지를 체크합니다.
data = {model}.objects.filter(name__iexact='chicken')

__contains, __icontains
지정한 문자열을 포함 하는지를 체크합니다. 
마찬가지로 __icontains는 대소문자를 구분하지 않고 체크합니다.
data = {model}.objects.filter(name__contains='chicken')

__range
지정한 범위 내에 포함 되는지 체크합니다.
날짜, 숫자 문자 등 모든 데이터의 범위를 사용할 수 있으며 파이썬의 range와 비슷합니다.
data = {model}.objects.filter(price__range=(1000,5000))
```

3. 데이터 수정하기(Update)
데이터를 수정하기 위해서는 수정할 데이터 객체를 가져온 다음 원하는 필드를 수정하고 save()를 호출하여 데이터베이스에 반영하면 됩니다.
```
data = {model}.objects.get(id=1)
data.name = 'Woojae'
data.save()
```
4. 데이터 삭제하기(Delete)
데이터를 삭제하기 위해서는 삭제할 데이터 객체를 가져온 다음 delete()를 호출하면 됩니다.
```
data = {model}.objects.get(id=3)
data.delete()
```

<br>

## 4 - 19 QuerySet이란?

<p align="center">
    <img src = "../Pictures\Django_32.png">
</p>
데이터와 소통할때 생기는 자료형으로 리스트와 비슷하다.


<br>

## 4 - 20 관리자 도구 사용하기

<p align="center">
    <img src = "../Pictures\Django_34.png">
</p>

일단 관리자 아이디와 비밀번호를 만든다.

<p align="center">
    <img src = "../Pictures\Django_33.png">
</p>

admin.py 에서 우리가 만든 모델을 등록한다.
사이트에 접속후 admin 으로 접속하면 모델을 관리할수있다!

<br>

## 4 - 21 모델 적용하기

템플릿에서 이제 모델을 이용하여 데이터를 사용하는 방법을 배워보자
<p align="center">
    <img src = "../Pictures\Django_35.png">
</p>

일단 모델을 import 해준다.
<p align="center">
    <img src = "../Pictures\Django_36.png">
</p>

```
menus = Menu.object.all()
context["menus"] = menus
```
메뉴s라는 변수를 만든다음에 menus를 넣는다.

<p align="center">
    <img src = "../Pictures\Django_37.png">
</p>

템플릿을 적절하게 조절하여 만들어준다.


<br>

## 4 - 22 djgngo 배포하기

배포하는데 서버의 컴퓨터가 존재한다. 배포하는 방식은 2가지가 있다.

<p align="center">
    <img src = "../Pictures\Django_38.png">
</p>

두 서비스의 차이는 개발자가 어디까지 영향을 미칠수 있는가 이다.

* Iaas : 서버 장비 + 운영체제만 제공
  
대표적인 예로는 아마존 aws_ec2 가있습니다.
  
* paas : 서버 장비 + 운영체제 + 실행환경 제공

대표적인 예로는 aws_elastic beanstalk, googld app engine, heroku 정도가 있습니다. 

배포하기전 여러 과정을 지켜야 하는데, 방법은 다음과 같다.

1. 디버그 모드 끄기
   
디버그는 에러를 잡아주는 역활을 하는데 만약 템플릿이름이 바뀌는 경우 에러 페이지에서 어느 파일에 어떤 것이 있는지 경로를 알려줌으로 해킹에 취약 할 수가 있다. 따라서 이를 방지하기 위해서 디버그 모드를 꺼야 한다.

<p align="center">
    <img src = "../Pictures\Django_39.png">
</p>

2. 호스트 설정하기

<p align="center">
    <img src = "../Pictures\Django_40.png">
</p>

ALLOWED_HOSTS = [] 안에 호스트로 지정한 서버의 내용을 기입한다.

3. 정적 파일 한곳으로 모으기

<p align="center">
    <img src = "../Pictures\Django_41.png">
</p>

서버가 우리 정적파일을 찾아주기 위해서 static_url 밑에 static_root를 적어주어야 합니다. 


<p align="center">
    <img src = "../Pictures\Django_42.png">
</p>

그런 다음 해당 명령어를 입력해 static 파일을 한곳으로 모아줍니다.

<br>

## 4 - 22 djgngo 배포하기 _ pythonanywhere

1. 프로젝트 디렉토리를 전체 압축합니다.

<p align="center">
    <img src = "../Pictures\Django_43.png">
</p>

2. pythonanywhere 에 가입
   
<p align="center">
    <img src = "../Pictures\Django_44.png">
</p>

3. files 을 누르고 압축했던 파일 업로드 합니다. 






<p align="center">
    <img src = "../Pictures\Django_45.png">
</p>


4. open bash 창을 열어 줍니다. 

<p align="center">
    <img src = "../Pictures\Django_46.png">
</p>

해당 창을 열고 unzip 을 통해서 압축을 풀어줍니다.

5. 가상 환경 조성하기
우리는 파이썬 3.7 버전을 사용했으니 그에 따른 환경을 조성해주어야 합니다.

<p align="center">
    <img src = "../Pictures\Django_47.png">
</p>

```
virtualenv --python=python3.7 django-evns
를 입력하여 파이썬 3.7의 가상환경을 조성합니다.
그리고 나서 django-envs 파일안으로 들어가서
source bin/activate 를 통해 환경을 적용시켜줍니다.
마지막으로는 그 환경에 django==2.2 버전을 설치해줍니다.
```

6. 오른쪽 상단 웹을 누르고 들어가기
   
<p align="center">
    <img src = "../Pictures\Django_48.png">
</p>

Code 부분에 코드위치를 적어줍니다.
