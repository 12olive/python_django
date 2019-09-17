**安装Pipenv：**

```
pip install pipenv
```

**创建虚拟环境**

```
pipenv install
# Pipenv会自动为你创建虚拟环境，自动生成一个随机的虚拟环境目录名。
```

**激活虚拟环境**

```
pipenv shell
```

此外，Pipenv还提供了一个pipenv run命令，在该命令后附加的参数会直接作为命令在虚拟环境中执行，这允许你不必显式的激活虚拟环境即可在虚拟环境中执行命令。比如，pipenv run python会启动虚拟环境中的Python解释器。

