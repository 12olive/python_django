# HTML中注释方法

Django模板template\(html\)中如何使用注释comment

单行注释:

使用 {\#  \#} 单行注释，例如:

```py
{# Everything you see here is a comment. It won't show up in the HTML output. #}
```

多行注释：

```py
{% comment %} this is a comment {% endcomment %}
```





