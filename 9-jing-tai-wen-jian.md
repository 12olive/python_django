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



