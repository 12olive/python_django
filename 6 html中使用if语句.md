# if 语句

1.所有的标签应在`{% if %}`之间

2.if标签应有闭合标签,即`{% endif %}`.

3.if标签做判断和`Python`中相同.

4.还可以使用\`elif,\`else\`语句.

示例如下

`html.index`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <ul>
    <!--<ul>标签可以更好的控制行距</ul>-->
    <!--可以在books 后增加 `reversed`,代表逆序-->
    {% for book in books %}
        <li>
        <!--<li>标签代表竖向排列</li>-->
            {{ book }}
        </li>
    {% endfor %}
    </ul>
    
    {% if age < 18 %}
        <P>您是未成年人,不能进入网吧</P>
    {% elif age == 18 %}
        <p>刚好过18,可以进入</p>
    {% else %}
         <p>已经过了浪的年纪,回家去吧!</p>
    {% endif %}
    <table border="1">
        <thead>
            <tr>
               <td>书名</td>
               <td>作者</td>
               <td>定价</td>
            </tr>
        </thead>
        <tbody>
            {% for book in books %}
                <tr style="background: green;">

                    <td>
                        {{ book.name }}
                    </td>
                    <td>
                        {{ book.author }}
                    </td>
                     <td>
                        100
                    </td>
                </tr>
            {% endfor %}

        </tbody>
    </table>
</body>
</html>
```

&lt;table&gt;表格标签 &lt;table border="10"&gt;线宽为10&lt;/table&gt;

&lt;td&gt; 表格中的一个单元格&lt;/td&gt;

&lt;thead&gt; 表头标签&lt;/thead&gt;

&lt;tbody&gt;表内容&lt;/tbody&gt;

&lt;tr&gt;tr是“table row（表格行）”的缩写，用于表示一行的开始和结束。&lt;/tr&gt;

`forloop.counter` 代表为循环的次数

` DLT`模板中没有\`continue\`和\`break\`语句



