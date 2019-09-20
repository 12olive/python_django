return和print

return为返回,可以由其他调用,但不会直接显示

print 直接显示结果

示例

```py
def func1():
    for i in range(1, 5):
        print (i)

def func2():
    for i in range(1, 5):
        return (i)

func1()

print ("..............")
print (func2())

输出结果
1
2
3
4
..............
1
```

程序读到return\(\)语句,其后的语句不会再被执行，所以打印func2\(\),只输出

**"1"**这个结果就退回了。

而print（）语句不同，其后的语句依然会被执行，所以调用func1\(\)时，值

**"1"、"2"、"3"、"4"**都输出了。

