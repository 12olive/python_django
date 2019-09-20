访问限制

如果要让内部属性不被外部直接fh访问,则在属性钱加"\_\_",这个就变成了私有属性

内部可以使用

```py
class Person(object):
    def __init__(self, name, age, money):
        self.name = name
        self.age = age
        self.__money = money

    def say(self):
        print('My name is %s, im %d years old, I have %d $'%(self.name, self.age, self.money))

    def run(self):
        print(self.__money)


per1 = Person('Jhon', 40, 1000)
per1.run()
# per1.say() 
# print(per1.money)
# print(per1.__money) 以上三个语句报错,因为__money为私有变量,不能直接访问,但可以在内部使用__money.

```



