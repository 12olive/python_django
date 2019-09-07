# temlpates\_url\_demo

## urls.py

```py
from django.urls import path
from . import views
urlpatterns = [
    path('', views.index, name="index"),
    path('books/', views.book, name='book'),
    path('books/detail/<book_id>', views.book_detail, name='book_detail'),
    path('movie/', views.movie, name='movie'),
    path('city/', views.city, name='city'),
    path('login/', views.login, name='login'),
]
```

## index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>templets_url_demo</title>
    <style>
        .nav{
            overflow: hidden;
        }
        .nav li{
            float: left;       {#li的元素左对齐,outside属性为上下显示,为默认选项#}
            list-style: none;  {#去掉li元素左侧的点#}
            margin: 0 20px;    {#0为上下边距,20为左右边距#}
        }
    </style>
</head>
<body>
    <ul class="nav">
        <li><a href="/">首页</a></li>
        <li><a href="{% url 'book' %}">读书</a> </li>
        <li><a href="movie/">电影</a> </li>
        <li><a href="city/">同城</a> </li>
        <li><a href="{% url 'book_detail' book_id='123' %}">最热文章</a></li>
        {# book_id='123' 中book_id和=和后面的字符串之间不能有空格;缺省book_id这个参数名称也可以,直接用字符串如'123'表示 #}
        <li><a href="{% url 'login' %}?next=lin">登录</a></li>
    </ul>
</body>
</html>
```

## views.py

```py
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return render(request, 'index.html')

def login(request):
    next = request.GET.get('next')
    text = '登录界面,登陆完成后跳转的url是:%s'% next
    return HttpResponse(text)

def book(request):
    return HttpResponse('book')

def book_detail(request, book_id):
    book_num = '您的书籍编号为: %s'% book_id
    return HttpResponse(book_num)

def movie(request):
    return HttpResponse('movie.html')

def city(request):
    return HttpResponse('city.html')
```



