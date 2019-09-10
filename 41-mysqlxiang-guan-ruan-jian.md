### 1 安装 MySQL

### 2安装Navicat,可安装破解版

### 3使用命令安装mysqlclient

`pip3 install mysqlclient`

### 4在django文件的settings文件更改引擎设置

```py

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
#原版datebases
```

```py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        #更改数据库引擎,也可以用其他的如:sqlite3/mysql/orcle等
        'NAME': 'django_db1',
        #数据库的名字:django_db1
        'USER': 'ROOT',
        #数据库用户名
        'PASSWORD': 'linjiang',
        #数据库的主机密码
        'HOST': 'LOCALHOST',
        #'HOST': '127.0.0.1'
        'PORT': '3306'
    }
修改后的databases及部分代码注释
```



