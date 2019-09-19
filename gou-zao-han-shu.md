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
class Person(object):
    # food = 'Banana'
    # name = 'lilei'
    # age = 10

    def __init__(self, name, age):
        self.name = name
        self.age = age

per1 = Person('Jhon', 40)
print(per1.name, per1.age)
per2 = Person('Mike', 20)
print(per2.name, per2.age)

>>>Jhon 40
Mike 20
```

self代表类的实例,而非类

哪个对象调用方法,那么该方法中的self就代表那个对象

self.\_\_class\_\_ 代表类名

示例如下

```py
class Person(object):

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def say(self):
        print('My name is %s, im %d years old'%(self.name, self.age))

per1 = Person('Jhon', 40)
per1.say()
print(per1.name, per1.age)
per2 = Person('Mike', 20)
print(per2.name, per2.age)
>> My name is Jhon, im 40 years old
Jhon 40
Mike 20
```

注意:self不是关键字,可以换成其他的标识符\(字符\)都可以.

如

```py
def say(a):
    print(a.name)
```



