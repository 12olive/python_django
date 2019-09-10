`settings.py`

```py
# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'front'
    #新建的app必须得加载进去
]

#最后部分
# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/2.2/howto/static-files/

STATIC_URL = '/static/'
```

```html
<body>
    <img src="/static/logo.jpg">
</body>
```

注意:`settings.py`中的STATIC\_URL = '/static/' 中的变量是可以变的,只要与html中的&lt;img&gt;中的路径相同即可,但注意app的目录下必须新建一个`static`文件夹,且名称不能更改

使用`load`可不再必须与settings里的`STATIC_URL`保持一致

示例如下

```html
<!DOCTYPE html>
{% load static %}
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <img src="{% static 'logo.jpg' %}">

</body>
</html>
```

如果有多个app则可以在各自的app目录下的static文件夹下新建与app名相同的文件夹,而使用`<img src="{% static 'front/logo.jpg' %}">`而实现对特定位置但同名的图片的调用.

如果有特殊的,与各个app均不太相关的可以在根目录\(与templates文件夹同级目录\)下新建static文件夹,并手动加入路径.\(settings.py中增加STATICFILES\__DIRS = \[os.path.join\(BASE\_DIR, 'static'_\)\]

例:在`static`里新建`index.css`文件,则选择在`index.html`里加载

```html
<!DOCTYPE html>
{% load static %}
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <link rel="stylesheet" href="{% static 'index.css' %}">

</head>
<body>
    <img src="{% static 'cms/logo.jpg' %}">

</body>
</html>
```

如果不想使用`{% load static %},使其变为内置标签,而省略该语句,则可以在settings`里使用补充最后一行内容

```py
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')]
        ,
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
            'builtins': ['django.templatetags.static']
            #添加以上一行
        },
    },
]
```



