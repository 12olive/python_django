## 实例化对象

1定义方法

```py
def method(self,arg):
    print('内容')
    return 实现方法
```

2怎么用

对象名.方法名\(参数或空\)

示例如下

```py
class Methon1(object):
    food = 'Banana'

    def method1(self, arg):
        print('内容' + arg)


eat = Methon1()
eat.method1('APPLE')
print(eat.food)
eat.food = 'apple'
print(eat.food)

# eat为对象,Methon()为类,method()为方法,food为类的属性
```

## 



