---
layout：    post
title:      Gem和Homebrew
subtitle:   安装软件也可以很装逼
date:       2018-03-19
author:     ARay
header-img: img/Programming.jpg
catalog:true
tags:
-MacOS
-terminal
---
gem 安装与使用
---

> ruby 是一种语言，是某些软件包代码的执行环境。而`gem`是管理这些基于ruby程序的程序。

### 安装gem

- Mac 自带 gem
- 安装gem程序包时，在安装命令前添加 sudo 则是以管理员身份安装，可以跳过权限问题。

### gem 安装源的管理

> 列出安装源
> 
> ```ruby
> gem sources -l
> ```



> 添加安装源
> 
> ```ruby
> gem sources -a XXX
> ```
> 
> ```ruby
> gem source -a https://gems.ruby-china.org
> gem source -a http://gems.github.com/
> gem source -a http://rubygems.org/
> ```



> 删除安装源
> 
> ```ruby
> gem sources -r XXX
> ```



> 更新安装源
> 
> ```ruby
> gem sources -u
> ```



### gem的升级和更新

更新gem本身

```ruby
gem update --system
```

更新gem安装的所有程序包

```ruby
gem update
```

更新某个程序包

```ruby
gem up date xxx
```

### ruby和gem常用命令

```
ruby -v #查看ruby 版本
ruby -e ''require"watir"; puts Watir::IE::VERSION''　#查看watir版本

gem -v #gem版本
gem update #更新所有包
gem update --system #更新RubyGems软件自身
gem install rake #安装rake,从本地或远程服务器
gem install rake --remote #安装rake,从远程服务器
gem install watir -v(或者--version) 1.6.2#指定安装版本的
gem uninstall rake #卸载rake包
gem list d #列出本地以d打头的包
gem query -n ''[0-9]'' --local #查找本地含有数字的包
gem search log --both #从本地和远程服务器上查找含有log字符串的包
gem search log --remoter #只从远程服务器上查找含有log字符串的包
gem search -r log #只从远程服务器上查找含有log字符串的包
gem help #提醒式的帮助
gem help install #列出install命令 帮助
gem help examples #列出gem命令使用一些例子
gem build rake.gemspec #把rake.gemspec编译成rake.gem
gem check -v pkg/rake-0.4.0.gem #检测rake是否有效
gem cleanup #清除所有包旧版本，保留最新版本
gem contents rake #显示rake包中所包含的文件
gem dependency rails -v 0.10.1 #列出与rails相互依赖的包
gem environment #查看gem的环境
```

---- 

Homebrew
---

- 安装前先检查一下 Xcode 的命令行工具是否已经安装，如果 macOS 系统更新过可能也需要重新安装一次，「终端」中输入

  ```
  xcode-select --install
  ```

> 如果已经安装命令行工具，那么就会出现`xcode-select: error: command line tools are already installed, use "Software Update" to install updates`的提示信息。

**Homebrew是一个MacOS上的软件包安装工具，通过命令行的方式安装和卸载软件，大部分的流行软件都提供了 Homebrew 的安装方式，也是开源世界里安装和更新软件的主流方式。**

### Homebrew的安装

只需要在联网的情况下，运行以下命令

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

brew的常用命令

```
brew doctor # 检查 Homebrew 的环境是否正常
brew install you-get # 安装源码，比如这行是安装 you-get 的命令
brew info you-get # 显示软件的各种信息，包括版本、源码地址、模块依存关系等等
brew uninstall you-get  # 卸载软件，一键静默卸载
brew search git # 模糊搜索 brew 支持的软件。不加软件名会列出所有它支持的软件。
brew list # 列出本机通过 brew 安装的所有软件
brew update # 更新 brew 软件自身
brew upgrade you-get # 更新安装过的软件，如果不加软件名更新所有可更新的软件
brew cleanup # 清除下载的各种缓存，历史版本一类的
```

### Homebrew-Cask

> brew cask 是对于 brew 的扩展，可以采用 brew 的方式安装图形界面的软件。安 装Homebrew-Cask 输入以下命令：
> 
> ```
> brew tap caskroom/cask
> ```

brew - cask常用命令

```
brew cask install iina # 下载安装软件，以 iina 为例
brew cask reinstall iina # 重新安装软件，以 iina 为例
brew cask uninstall iina # 卸载软件，以 iina 为例
brew cask search iina # 模糊搜索软件，如果不加软件名，就列出所有它支持的软件
brew cask info iina # 显示这个软件的详细信息，或是其安装目录信息等
brew cask list # 列出本机按照过的软件列表
brew cask cleanup #  清除下载的缓存以及各种链接信息
brew update && brew upgrade brew-cask # 更新 cask 自身
```

> “brew 是从下载源码解压然后 ./configure && make install ，同时会包含相关依存库。并自动配置好各种环境变量，而且易于卸载。 这个对程序员来说简直是福音，简单的指令，就能快速安装和升级本地的各种开发环境。而 brew cask 是已经编译好了的应用包 （.dmg/.pkg），仅仅是下载解压，放在统一的目录中（/opt/homebrew-cask/Caskroom），省掉了自己去下载、解压、拖拽（安装）等步骤，同样，卸载相当容易与干净。这个对一般用户来说会比较方便，包含很多在 AppStore 里没有的常用软件。”
> 
> ── [brew和brew cask有什么区别？][1]

[1]:	https://www.zhihu.com/question/22624898