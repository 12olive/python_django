**安装Pipenv：**

pipenv 的安装和普通的第三方库没什么区别，可以直接使用 pip 命令安装。

```
pip install pipenv
```

在 Mac 上可以使用 brew 命令来安装

```
brew install pipenv
```

**创建虚拟环境**

```
# 进入项目所在目录
cd your_project

pipenv install
# Pipenv会自动为你创建虚拟环境，自动生成一个随机的虚拟环境目录名。
```

**激活虚拟环境**

```
#运行程序前我们还是要激活虚拟环境，我们可以使用 pipenv shell 来激活，不需要指定名字，只要你在当前项目下执行该命令就行。
pipenv shell
```

此外，Pipenv还提供了一个pipenv run命令，在该命令后附加的参数会直接作为命令在虚拟环境中执行，这允许你不必显式的激活虚拟环境即可在虚拟环境中执行命令。比如，pipenv run python会启动虚拟环境中的Python解释器。

**删除虚拟环境**

```
pipenv --rm 
#删除虚拟环境后，会把虚拟环境目录和里面的所有依赖包删除掉，但是 Pipfile 和 Pipfile.lock 文件还会保留。
```



