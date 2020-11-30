#分布式技术作业

>**19级大数据管理与应用 薛彬彬**
>**学号2019302190071**

##作业要求
**利用*Django*编写前端网页及后端数据库等实现具有秒传功能的云盘系统**


[TOC]

##作业完成过程

###一.在vode中创建Django的项目文件

####1.创建项目主体文件mysite_login

在所需要创建的位置通过命令符输入代码`django-admin startproject mysite_login`

在项目包中的`settings.py`更改时区为亚洲/上海，语言为中文
```python
LANGUAGE_CODE = 'zh-hans'

TIME_ZONE = 'Asia/Shanghai'

USE_I18N = True

USE_L10N = True

USE_TZ = False
```

在vscode终端中输入`py manage.py runserver`运行服务器进行调试

测试服务器运行正常

输入`py manage.py startapp login`创建登录应用命名为`login`

在项目包中的`settings.py`文件里添加`login`应用
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'login',
]
```

在`login`应用文件夹中创建`urls.py`及`templates`文件夹
配置项目根路由
```python
from django.contrib import admin
from django.urls import path
from django.conf.urls import url, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('login/', include('login.urls')),
]
```

在应用包下创建并配置`urls.py`文件
```python
from django.conf.urls import url
from . import views
urlpatterns=[
    url(r'^$',views.login_view)

]
```




```python
def login_view(request):

    return render(request,'login.html')
```

##主要问题和解决方法

##作业结果展示