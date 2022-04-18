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

## Django 정적파일 관리하기
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

## Django Template 와 static 폴더 구조 

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

## Django의 템플릿 언어
정적이 아닌 동적으로 웹페이지를 움직이는데 사용하는 언어라고 할 수 있다.


