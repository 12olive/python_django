## 析构函数

析构函数:  \_\_del\_\_\(\)   释放对象时自动调用

手动释放

```py
del 对象名
```

在函数里定义的对象,会在函数结束是时自动释放,用于减少内存空间

默认不显示,但实际是有,一般自动释放,特殊情况可以手动释放

## 重写

重写,将函数重写定义一遍

\_\_str\_\_\(\):在调用print打印对象时自动调用,是给用户使用的的,是一个描述对象用的

\_\_repr\_\_\(\)

在直接调用 `对象名`时,如果定义了`__str__()`实际为`对象名.__str__()`

```py
class Person(object):
    def say(self):
        print('My name is %s, im %d years old'%(self.name, self.age))

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return '%s, %d' %(self.name, self.age)

per1 = Person('Jhon', 40)
print(per1)
#等同于下面的命令
print(per1.__str__())

>>Jhon, 40
Jhon, 40
```



