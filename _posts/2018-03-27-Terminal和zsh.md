---
layout:     post
title:      Terminal和zsh
subtitle:   总要折腾一下……
date:       2018-03-27
author:     ARay
header-img: img/Programming.jpg
catalog: true
tags:
- MacOS
- Terminal
---

昨天学会了怎么用gem和homebrew来装app，然而发现系统自带的终端看起来不够好看，在找资料的时候看见都推荐用iTerm，于是下载了一个装上。

MacOS的Terminal默认的shell是bash。

### 先看看系统自带了那些shell

在终端输入：

```
cat /etc/shells
```

然后会显示

```
/bin/bash
/bin/csh
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

作为外行来说，虽然不懂这些shell之间的差别，但是bash的界面看起来不够炫，得换。

换成zsh。

虽然Mac自带了zsh，貌似设置很复杂啊，但是教程都说装上oh my zsh就方便了。

赶紧装。

### 安装 oh my zsh

打开iterm，输入

```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh`
`cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

就OK了。

接着重新启动iTerm，输入

```
zsh
```

shell就已经切换到zsh了。而且oh my zsh已经帮忙配置好了。

这时候换个界面就是很容易的事情了啊。

### 修改主题

```
open ~/.zshrc 
```

修改 `ZSH_THEME=“robbyrussell”` 主题在  **/.oh-my-zsh/themes**目录下。

修改为 `ZSH_THEME="kolo"` 可以[参照这里][1]进行选择.

好了，基本搞定，接下来就

### 把zsh设置为默认的shell。

```
chsh -s /bin/zsh
```

对于我这种半吊子来说，已经差不多了。以后再来慢慢折腾各种Theme。



[1]:	https://github.com/robbyrussell/oh-my-zsh/wiki/themes