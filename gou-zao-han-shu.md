## 构造函数

```py
__init__()
```

在使用类创建对象的时候自动调用

注意:如果不显示的写出构造函数,默认会自动添加一个空的构造函数

示例如下

```py
class Methon1(object):
    def __init__(self):
        print("this is a init")

eat = Methon1()

>>> this is a init
```

```py
class Methon1(object):

    def __init__(self, name, age):
        print(name , age)

eat = Methon1('Mike', 20)

>>> Mike 20
```

```py
class Methon1(object):
    # food = 'Banana'
    # name = 'lilei'
    # age = 10

    def __init__(self, name, age):
        self.name = name
        self.age = age

eat1 = Methon1('Jhon', 40)
print(eat1.name, eat1.age)
eat2 = Methon1('Mike', 20)
print(eat2.name, eat2.age)

>>>Jhon 40
Mike 20
```

self代表类的实例,而非类

哪个对象调用方法,那么该方法中的self就代表那个对象

