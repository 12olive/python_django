`views.py`

```py
from django.shortcuts import render

def gre():
    return 'hello world!'

def index(request):
    text = {'greet': gre} #后面的`gre`为字典中的`value`,实际为一个`gre`函数
    return render(request, 'index.html', context=text)
```



