```py
from types import MethodType

#创建一个空类
class Person (object):
    pass

per =Person()
#动态添加属性,这体现了动态语言的特点:灵活
per.name = 'Tom'
print(per.name)

#动态添加方法
'''
#其中一种方法,但不推荐
def say(self):
print('My name is ' + self.name)
per.speak = say
per.speak(per)

'''
def say(self):
    print('My name is ' + self.name)
per.speak = MethodType(say, per)
per.speak()

#如果想要限值实例添加特定的属性,如那么,age等,需要再定义类的时候,定义一个特殊的属性(__slots__)可以限值动态添加的属性

#例如
class Person (object):
    __slots__ = ('name', 'age')
```

```py
class Person(object):
    def __init__(self, age):
    #self.age = age  书序属性直接对外暴露,可以使用如下方法进行限制访问
    self.__age = age
    
    '''
    #使用私有变量,可以使用方法来提取对象和改变变量
    def getAge(self):
        return self.__age
    def setAge(self):
        if age < 0:
            age = 0
        self.__age = age
    '''
    #也可以使用 方法名为受限制的变量去掉双下划线
    @property
    def age(self):
        return self.__age
    #getAge
    #去掉下划线.setter
    @age.setter 
    def age(self, age):
        if age < 0:
            age = 0
        self.__age = age
    #setAge
    
per.age = 100 #相当于调用setAge
print(per.age) #相当于调用getAge

#@property:可以对受限制访问的属性使用点语法,而不是使用方法,当然实际上还是使用的方法,但表面上可以当做属性来使用
```

运算符重载

```py
class Person(object):
    def __init__(self, num):
        self.num = num

    #运算符重载
    def __add__(self, other):
        return Person(self.num + other.num)
    def __str__(self):
        return 'num=' + str(self.num)

per1 = Person(1)
per2 = Person(2)
print(per1 + per2)
#相当于print(per1.__add__(per2)
print(per1)    
```

发邮件

```py
#发邮件的库
import smtplib

#邮件文本
from email.mime.text import  MIMEText

#STMP服务器
STMPsever = 'stmp.163.com'

#发邮件的地址
sender = '12olive@163.com'
#发送者邮箱的密码,是授权密码,不是登录密码
password = '123456789'

#设置发送的内容
message = 'hello world'
#转换成邮件文本
msg = MIMEText(message)

#主题
msg['Subject'] = 'your friend'

#发送者
msg['From'] = sender



```



