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



