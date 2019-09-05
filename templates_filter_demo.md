`views.py`

```py
from django.shortcuts import render

def gre():
    return 'hello world!'

def index(request):
    text = {'greet': gre} #后面的`gre`为字典中的`value`,实际为一个`gre`函数
    return render(request, 'index.html', context=text)
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
    {{ greet }}
    {# greet 为context中的key,调用其value,即 gre函数 #}
</body>
</html>
```



