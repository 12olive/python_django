当前路径:`pwd`

返回上级目录:`../`

查看占用端口的进程 `lsof -i :端口号`

结束占用端口的命令 \`kill pid号

以上两条命令,可以增加sudo

查找  find/ -name \[文件名\]





# [Homebrew](https://brew.sh/)包管理器 {#h1_1}

## 一、简介 {#h2_2}

[Homebrew](https://brew.sh/)是Mac OS X下的一款软件包管理器, 相当于Linux下的yum、apt-get. 通过[Homebrew](https://brew.sh/)可以方便的下载、安装应用, 不再需要亲自动手去搜索各种安装包.

注意：[Homebrew](https://brew.sh/)与Mac OS X中的[MacPorts](https://www.macports.org/)包管理器不兼容, 如果已经安装[MacPorts](https://www.macports.org/), 需先将其卸载.

## 二、安装 {#h2_3}

### 安装Xcode命令行工具 {#h3_4}

[Homebrew](https://brew.sh/)包管理器依赖Xcode的命令行工具**Command Line Tools \(CLT\) for Xcode**, 可以通过两种方式来获取：

* 只安装Xcode命令行工具, 在终端执行如下命令：

  xcode-select --install

* 直接在AppStore中安装整个Xcode（如果有用Xcode做开发的话）

### 安装[Homebrew](https://brew.sh/) {#h3_5}

直接在终端中执行如下命令执行安装即可

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/[Homebrew](https://brew.sh)/install/master/install)"
```

安装结束后查看[Homebrew](https://brew.sh/)版本信息

```
brew --version
```

## 三、替换Homebrew安装源 {#h2_6}

这里替换为清华大学开源软件镜像站的安装源, 直接在终端执行如如下命令即可:

> git -C "$\(brew --repo\)" remote set-url origin[https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git](https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git)
>
> git -C "$\(brew --repo homebrew/core\)" remote set-url origin[https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git](https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git)
>
> git -C "$\(brew --repo homebrew/cask\)" remote set-url origin[https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git](https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git)
>
> brew update

如果需要替换二进制预编译包源的话, 可以执行如下命令:

> echo 'export HOMEBREW\_BOTTLE\_DOMAIN=[https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles](https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles)' &gt;&gt; ~/.bash\_profile
>
> source ~/.bash\_profile

复原操作可以参考[https://mirrors.tuna.tsinghua.edu.cn/help/homebrew](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew)

## 四、禁用自动更新 {#h2_7}

Homebrew在安装应用时, 默认情况下会自动更新所有应用, 需要等待很长时间的更新操作, 可以选择屏蔽自动更新:

```
echo
'export HOMEBREW_NO_AUTO_UPDATE=true'
>
>
 ~/.bash_profile


source
 ~/.bash_profile

```

## 五、安装brew-cask {#h2_8}

brew-cask是一个Homebrew的增强工具, 用于下载安装Mac OS X的GUI应用的二进制预编译包\(Chrome、sourcetree等客户端\).

Github地址为:[https://github.com/xyb/homebrew-cask-completion](https://github.com/xyb/homebrew-cask-completion)

brew-cask可以采用如下命令安装:

```
brew install homebrew/completions/brew-cask-completion

```

或者

```
brew tap homebrew/completions
brew install brew-cask-completion

```

## 六、常用命令 {#h2_9}

输入brew命令可以看到brew的常用用法, brew cask的用法与brew大体一致

```
Example usage:
brew search     搜索包
brew info       查看包信息
brew install    安装包
brew update     更新brew
brew upgrade    更新软件包
brew outdated   查看可用更新
brew uninstall  卸载应用包
brew list       已安装列表

brew config     查看配置信息
brew doctor     诊断

brew help       查看帮助信息
```



