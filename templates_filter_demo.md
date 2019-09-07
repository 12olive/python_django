为什么需要过滤器

因为在DTL中,不支持函数的调用形式`()`,因此不能给函数传递参数,而过滤器其实就是一个函数,可以对需要处理的参数进行处理,并且可以额外接收一个参数,即过滤器最多有两个参数\(`add`或`cut`,的`|`两边各为一个参数,如`{{add1|add:add2}}`\)

`views.py`

```py
from django.shortcuts import render
from datetime import datetime

def gre():
    return 'hello word!'

def index(request):
    text = {'greet': gre} #后面的`gre`为字典中的`value`,实际为一个`gre`函数
    return render(request, 'index.html', context=text)

def add_view(request):
    context={
        'key1': [1,2,3,4],
        'key2': [5,6,7,8]
    }
    return render(request, 'add.html', context=context)

def cut_views(request):
    return render(request,'cut.html')

def date_views(request):
    date={
        'date_now': datetime.now()
        #此时跟本机时间慢8h,因为跟时区的默认设置有关
    }
    return render(request,'date.html',context=date)
```

`url.py`

```py
"""templates_filter_demo URL Configuration

The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/2.2/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
"""
from django.contrib import admin
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index),
    path('add/', views.add_view, name='add'),
    path('cut/', views.cut_views, name='cut'),
    path('date/', views.date_views, name='date'),
]

```

`index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>templates_filter_demo</title>
</head>
<body>
    {{ greet|add:'olive' }}
    {# greet 为context中的key,调用其value,即 gre函数 #}
    <li><a href="{% url 'add' %}">add过滤器</a></li>
    <li><a href="cut/">cut过滤器</a></li>
</body>
</html>
```

`cut.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>cut过滤器</title>
</head>
<body>
    {{ 'hello world'|cut:'o'}}
    {# cut就跟replace作用基本一样,即去掉 cut 后的字符串 #}
</body>
</html>
```

`add.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>add过滤器</title>
</head>
<body>
    <p>{{ '1'|add:'2' }}</p>
    {{ '1'|add:'122sss' }}
    <p>{{ key1|add:key2 }}</p>
</body>
</html>
```

## `add`过滤器语法

```py
def add(value, arg):
    """Add the arg to the value."""
    #如果是两个是数值则直接相加
    try:
        return int(value) + int(arg)
    except (ValueError, TypeError):
    #如果是一个数值一个字符串则拼接,list也是拼接
        try:
            return value + arg
        except Exception:
            return ''
```



