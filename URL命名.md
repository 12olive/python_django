# URL命名

```
#front:是用来管理前台相关的代码的
#cms:是用来管理后台相关的代码的
```

## 为什么需要URL命名

可以随便变更url定向,如果在代码中写死可能会经常变更,因此给URL取个名字.

## 如何给一个url指定名称?

在`path`函数中,传递一个`name`参数就可以指定.示例代码如下:

## 应用命名空间

多个页面\(app\)变量相同就会产生变量重复.需要做一个应用命名空间的变量叫 `app_name`  
,只要在`app`的`url.py`中定义一个叫做`app_name`的变量,来指定这个应用的命名空间 即可.

# 模板

在之前的章节,视图函数直接返回文本,而在实际环境很少如此使用,实际页面大佛使用HTML代码..我们 主要使用DTL模板系统.

## DTL与普通HTML文件的区别

DTL模板是一种带有特殊语法的html文件,这个html文件可以被Django变异,可以传递参数进去,实现数据动态化.在变异完成后,生成一个普通的HTML文件,然后发送给客户端,

## 渲染模板:

渲染模板有多种样式.这里主要用两种.  
第一种  
`Render_to_string`:找到模板,然后将模板编译后渲染成python的 字符串格式.最后再通过HttpResponse类包装成一个HTTPResponse在template文件夹下新建一个html.对象返回回去.示例代码如下:

```py
frome django .template,loder import render_to_string
From django.http import HTTPResponse:

def book_detail(request, book_id):
http = render_to_string(‘detail.html)
Return HttpResponse(html)
```

第二种  
`render`  
示例如下:

```python
from django.shortcuts import render

def book_list(request):
return render(request, “list.html”)
```



