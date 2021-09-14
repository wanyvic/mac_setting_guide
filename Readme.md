# Mac设置指南

## 配置高效的Mac工作环境

本文是以['强迫症的Mac设置指南'](https://github.com/macdao/ocds-guide-to-setting-up-mac)的基础上修改补充而来，把我个人使用Mac的经验分享出来。我认为“一个高效的Mac工作环境”有以下几个特点：

- ***自动化***

  自动化可以大大简化操作，提高效率。举个例子：浏览器搜索内容，需要执行1）鼠标选择文字，2）拷贝内容到剪贴板，3）打开浏览器或切换到浏览器，4）粘贴拷贝的内容，5）按下回车键，总共5步操作。而利用[PopClip](#PopClip)，只需要1）鼠标选择文字，2）鼠标双击文字，3）在弹出的浮动窗点击搜索图标，总共3步操作即可完成。

- ***一致性***

  我经常会遇到使用不同的开发工具或编辑器，快捷键和操作、命令不同的问题。我强烈建议，至少在一个团队中，大家尽量使用相同的开发工具、相同的编辑器、相同的快捷键、相同的命令等环境。

- ***够用就好***
  够用就好，如果系统本身已经满足了我的需求，我不会再使用第三方工具。

- ***高效率***
  效率，一切都是为了效率。

- ***强烈推荐***

  我个人强烈推荐以下神器级的工具：[Homebrew](#homebrew)、[Homebrew Cask](#homebrew-cask)、[iTerm2](#iterm2)、[Alfred](#alfred)、
[PopClip](#popclip)、[Path Finder](#path-finder)、[ShadowsocksX](#shadowsocksx)、[JetBrains全家桶](#jetbrains全家桶)、[Visual Studio Code](#visual-studio-code)、[Dash](#dash)、[Charles](#charles)、[Swagger](#swagger)、[Regex101](#regex101)等。

本文对于第三方应用如何安装和使用只有最简单的介绍，具体还请参考官方网站和相关文档。另外，欢迎大家通过码云的`Issues`或者`Pull Requests`方式来分享你的经验。期待你的反馈。

## 目录

1. [操作系统设置](#1-操作系统设置)

   - [功能键](#功能键)
   - [键盘控制](#键盘控制)
   - [Spotlight/输入法快捷键](#spotlight输入法快捷键)
   - [其他快捷键](#其他快捷键)
   - [设置Trackpad轻点来点按](#设置trackpad轻点来点按)
   - [语音功能](#语音功能)
   - [词典和翻译](#词典和翻译)
   - [Dock位置](#dock位置)
   - [删除Dock上不常用的图标](#删除dock上不常用的图标)
   - [创建大小写敏感的工作区](#创建大小写敏感的工作区)
   - [Keychain Access](#keychain-access)

2. [系统工具](#2-系统工具)

   - [Homebrew](#homebrew)
   - [Homebrew Cask](#homebrew-cask)
   - [iTerm2](#iterm2)
   - [Zsh和Oh My Zsh](#zsh和oh-my-zsh)
   - [AutoJump](#autojump)
   - [Alfred](#alfred)
   - [PopClip](#popclip)
   - [Path Finder](#path-finder)
   - [SecureCRT和SecureFX](#securecrt和securefx)
   - [ShadowsocksX](#shadowsocksx)
   - [ZeroTier](#zerotier)
   - [Moom](#moom)
   - [CheatSheet](#cheatsheet)
   - [Stow和dotfiles](#stow和dotfiles)

3. [开发工具](#3-开发工具)
   - [Java版本管理](#java版本管理)
   - [Node版本管理](#node版本管理)
   - [JetBrains全家桶](#jetbrains全家桶)
   - [Visual Studio Code](#visual-studio-code)
   - [SmartGit](#smartgit)
   - [微信开发者工具](#微信开发者工具)
   - [Navicat Premium](#navicat-premium)
   - [Studio 3T](#studio-3t)
   - [FastoRedis](#fastoredis)
   - [DbSchema](#dbschema)

4. [开发辅助](#4-开发辅助)
   - [Dash](#dash)
   - [Charles](#charles)
   - [Swagger](#swagger)
   - [Paw](#paw)
   - [IBM API Connect](#ibm-api-connect)
   - [Regex101](#regex101)

5. [分享链接](#5-分享链接)

## 1. 操作系统设置

本节介绍操作系统本身的一些设置。

### 功能键

默认情况下，F1-F12都是特殊功能，比如调节屏幕亮度。而当你需要键入F1-F12时需要同时按住Fn，这对于开发人员来说是非常不方便的。

解决方案：将F1-F12改成标准功能键，选择`系统偏好设置` -> `键盘` -> `键盘` -> 选中`将F1、F2等键用作标准功能键`。

### 键盘控制

当系统弹出确认对话框时，如在Sublime Text里关闭文件时可能会出现这样的对话框：

![dialog-box-without-all-controls](resource/dialog-without-keyboard-control.png)

注意这个`Save`按钮跟其他两个按钮不太一样，它的底色是蓝的。这种按钮被称为默认按钮，除了用鼠标点击触发外，还可以通过回车键触发。

那么问题来了，如果你不想保存，想点击`Don't Save`，是不是只能用鼠标点击了呢？能否通过键盘操作？

解决方案：选择`系统偏好设置` -> `键盘` -> `快捷键` -> 选中`所有控制`；或者使用快捷键`Ctrl+F7`。设置之后这个对话框会变成这样：

![dialog-box-with-all-controls](resource/dialog-with-keyboard-control.png)

这个`Don't Save`按钮有了一圈蓝边，这个意味着你可以通过`Space`键触发。不仅如此，你还可以用`Tab`键把蓝边转移到其他按钮，来实现全键盘控制。在这个对话框上，你还可以用`Esc`来执行`Cancel`操作。

除了`所有控制`这个方法，你还可以用`Cmd+⌫`来选择`Don't Save`。`Cmd+⌫`的作用是在包含“删除”或“不存储”按钮的对话框中选择“删除”或“不存储”。

### Spotlight/输入法快捷键

Spotlight的快捷键是`Cmd+Space`，切换输入法的快捷键是`Ctrl+Space`。这个设置有以下的问题：

- 由于我们推荐使用[Afred](#Afred)，其功能与Spotlight类似但功能更加强大，建议关闭Spotlight的快捷键，同时将[Afred](#Afred)的快捷键设置为`Cmd+Space`。设置方法：选择`系统偏好设置` -> `键盘` -> `快捷键` -> `聚集` -> 取消选中`显示"聚焦"搜索`。

- JetBrains的IDE，比如IntelliJ IDEA、WebStorm等都使用`Ctrl+Space`作为自动完成这个最常用功能的快捷键。我不建议更改IDE的快捷键，而建议更改切换输入法的快捷键为`Option+Space`。设置方法：选择`系统偏好设置` -> `键盘` -> `快捷键` -> `输入法` -> 点击`选择上一个输入法` -> 将快捷键改为`Option+Space`。

### 其他快捷键

让双手尽量多的键盘和快捷键，少使用鼠标和触摸板，可以大大提高效率。

- [Mac keyboard shortcts](https://support.apple.com/kb/HT201236)

  苹果官方文档。当你在写代码，怎么通过快捷键让光标转移到行首、行尾、向上翻页或者将光标移左移一个词都在这篇文档里。

- [Mac keyboard shortcuts for accessibility features](https://support.apple.com/kb/HT204434)

  苹果官方文档。回车触发蓝底按钮，空格触发蓝边按钮，都出自这里。

### 设置Trackpad轻点来点按

默认情况下按下触摸板才是点按（click）。我喜欢设置成用轻点作为点按，设置方法：选择`系统偏好设置` -> `触控板` -> `光标与点按` -> 选中`轻点来点按`。

### 语音功能

Mac自带了语音功能，可以用`say`命令让 Mac 开口说话：

```sh
say hello
```

可以和`&&`或者`;`配合使用来提示你某任务已经完成：

```sh
brew update && brew upgrade && brew cleanup ; say mission complete
```

通过命令行来听取发音还是有点麻烦。其实我们几乎可以在任何地方选中单词，然后使用快捷键`Option+Esc`发音。设置方法：选择`系统偏好设置` -> `辅助功能` -> `语音` -> 选中`按下按键时朗读所选文本`。另外，利用我们推荐的[PopClip](#PopClip)的`Say`插件，可以全部通过鼠标操作来实现选择文字并读出发音的功能。

### 词典和翻译

Mac自带了词典应用（Dictionary），你几乎可以在任何应用中通过三指轻拍触摸板来查询对应单词的释义。另外，利用我们推荐的[PopClip](#PopClip)的`字典`或`Google Translate`等翻译插件，可以全部通过鼠标操作来实现选择文字并翻译的功能。

如果你觉得Dictionary中自带的字典不够用，可以手工转换、添加自制的字典。具体教程和字典下载网上很多，大家可以自行百度。

### Dock位置

默认Dock在屏幕下方，我们的屏幕一般是16:10，Dock在屏幕下方的话会占据本来就不大的垂直空间。建议把Dock放到左边或者右边。设置方法：选择`系统偏好设置` -> `程序坞` -> `位于屏幕上的位置` -> 选中`左边`或`右边`。

### 删除Dock上不常用的图标

默认情况下Dock被一堆系统自带的应用占据着，而其中大部分我都很少使用，当我打开几个常用应用后，Dock 上会有很多图标，每个图标都会被挤得很小。所以我会把所有Dock上不常用的固定图标删掉，

### 创建大小写敏感的工作区

Mac的文件系统默认是大小写不敏感的，而Linux的文件系统默认是大小写敏感的，当在Mac开发某些Linux上的程序时，经常会出现一些因为文件名大小写引发的诡异问题。解决方案：在Mac创建一个大小写敏感的工作区来解决避免这些问题：

```sh
hdiutil create -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 100g -volname workspace ~/Documents/workspace.dmg.sparseimage
```

上面的命令是创建了一个100G的工作区，如果想改成其他大小，请修改命令中的大小参数。

可以通过三种方式挂载镜像：

1. 直接双击打开 `~/Documents/workspace.dmg.sparseimage`
2. `open ~/Documents/workspace.dmg.sparseimage`
3. `hdiutil attach ~/Documents/workspace.dmg.sparseimage`

### Keychain Access

钥匙串访问（Keychain Access）是一个Mac应用程序，对我来说它最大的功能就是查看已经保存的各种账号和密码，包括Wi-Fi密码。

## 2. 系统工具

本节介绍一些常用的、系统级的第三方效率工具及其设置。

### Homebrew

[Homebrew](http://brew.sh)是Mac上的软件包管理工具，拥有安装、卸载、更新、查看、搜索等很多实用的功能。简单的一条指令，就可以实现包管理，而不用你关心各种依赖和文件路径的情况，十分方便快捷。官方称之为`The missing package manager for OS X`。

***安装方法：***

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

PS：安装 brew 的时候会自动下载和安装 Apple 的 Command Line Tools。

***使用说明：***

- 查找软件，例如查找名称带sql的软件，可以执行以下的命令：

  ```sh
  brew search sql
  ```

- 安装软件，例如安装MySQL、Gradle、Maven、Node.js可以执行以下的命令：

  ```sh
  brew install mysql gradle maven node
  ```

- 列出已安装软件，可以执行以下的命令：

  ```sh
  brew list
  ```

- 升级已安装软件，可以执行以下的命令：

  ```sh
  brew --cleanup upgrade
  ```

  PS：
  - `--cleanup`表示升级后删除旧版本，如果你需要保留旧版本，请删除此参数。你也可以在升级完全部软件后，统一执行：`brew cleanup`删除全部旧版本。

  - 如果只升级特定软件，可以执行：`brew --cleanup upgrade xxxx`。

- 卸载已安装软件，可以执行以下的命令：

  ```sh
  brew uninstall xxxx
  ```

- 具体命令行参数和使用教程请大家访问官网或自行百度。

### Homebrew Cask

[Homebrew Cask](https://caskroom.github.io)是Mac上使用brew命令行安装Mac应用的工具。几乎所有常用的应用都可以通过brew-cask安装，而且是从应用的官网上下载，所以你要安装新的应用时，建议用brew-cask安装。如果你不知道应用在brew-cask中的ID，可以先用`brew cask search`命令搜索。brew-cask是社区驱动的，如果你发现brew-cask上的应用不是最新版本，或者缺少你某个应用，你可以自己提交pull request。

***安装方法：***

```sh
~~brew tap caskroom/cask~~
```

***使用说明：***

- 查找软件，例如查找名称带chrome的软件，可以执行以下的命令：

  ```sh
  brew cask search chrome
  ```

- 安装软件，例如安装iTerm2，可以执行以下的命令：

  ```sh
  brew cask install iterm2
  ```

- 列出已安装软件，可以执行以下的命令：

  ```sh
  brew cask list
  ```

- 升级已安装软件，可以执行以下的命令：

  ```sh
  brew cask upgrade
  ```

- 重装已安装软件，可以执行以下的命令：

  ```sh
  brew cask reinstall xxxx
  ```

- 卸载已安装软件，可以执行以下的命令：

  ```sh
  brew cask uninstall xxxx
  ```

- 删除已安装软件的安装包，可以执行以下的命令：

  ```sh
  brew cask cleanup
  ```

### iTerm2

[iTerm2](https://www.iterm2.com/)是Mac上最常用的终端应用，是Terminal应用的替代品。提供了诸如`Split Panes`等[一群实用特性](https://www.iterm2.com/features.html)。网上几乎所有的文章都推荐使用iTerm2替代Terminal。

***安装方法：***

```sh
brew cask install iterm2
```

***使用说明：***

- 在iTerm2中，除了可以用`Ctrl+E`等快捷键（详见[其他快捷键](#其他快捷键)）之外，还可以使用`Option+B`、`Option+F`等快捷键（具体可以参考[这里](http://ss64.com/bash/syntax-keyboard.html)、[中文](https://zhuanlan.zhihu.com/p/34509032)）。前提是这样设置一下：

  选择`Iterm`菜单 -> `Preferences` -> `Profiles`，选择你在使用的 Profile（默认是`Default`），在`Keys`标签页中把`Left option (⌥) key acts as`和`Right option (⌥) key acts as`都设置成`+ESC`。

- 在打开新的窗口/标签页的时候，默认情况下新窗口总是HOME目录，还需要我每次敲命令才能进入工作目录。如果想要这个新窗口在打开的时候就自动进入工作目录，需要如下设置：

  选择`Iterm`菜单 -> `Preferences` -> `Profiles`，选择你在使用的 Profile（默认是Default），在`General`标签页中的`Working Directory`部分中选择`Reuse previous seesion's directory`。

- 在iTerm2中双击会自动选中对应的词，三击会选中对应的整行。选中的内容会自动进入剪贴板，不需要再按`Cmd+C`复制。

### Zsh和Oh My Zsh

[Zsh](http://zsh.sourceforge.net/)是Mac和Linux上替代bash的Shell脚本语言解析器，史称『终极 Shell』，其主要特点如下：

- 兼容bash，原来使用bash的兄弟切换过来毫无压力。

- 强大的历史纪录功能，在用`上键`查找历史命令时，zsh支持限制查找。比如输入ls然后再按`上键`，则只会查找用过的ls命令。

- 多个终端会话共享历史记录。

- 智能拼写纠正，输`入gtep mactalk * -R`，系统会提示：`zsh: correct 'gtep' to 'grep' [nyae]?`

- 各种自动补全：路径补全、命令补全、命令参数补全、插件内容补全等。触发补全只需要按一下或两下`Tab`键，补全项可以使用`Ctrl+n/p/f/b`上下左右切换。

- 智能跳转：需要安装autojump，zsh会自动记录你访问过的目录，通过`j 目录名`可以直接进行目录跳转，而且目录名支持模糊匹配和自动补全。

- 通配符搜索：执行`ls -l **/*.sh`，可以递归显示当前目录下的shell文件。

- 其他更多...

[Oh My Zsh](http://ohmyz.sh)是基于zsh命令行，提供了主题配置、插件机制、内置的便捷操作等扩展功能。Oh My Zsh提供给我们一种全新的方式使用命令行，正如它的主页上说的，Oh My Zsh是一种生活方式。

***安装方法：***

- 安装Zsh：Mac系统本身自带zsh，因此不需要单独安装，只需要将Shell切换到zsh即可。切换命令为：

  ```sh
  chsh -s /bin/zsh
  ```

  PS：如何想切换回bash，请执行`chsh -s /bin/bash`。

- 安装Oh My Zsh：

  ```sh
  sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
  ```

***配置说明：***

zsh的配置主要集中在用户当前目录的`.zshrc`文件里，即`~/.zshrc`。用vim或你喜欢的其他编辑器打开`~/.zshrc`，配置路径、环境变量及zsh和Oh My Zsh的功能。zsh和Oh My Zsh主要配置的内容如下：

- 主题：

  oh my zsh提供了数十种主题，相关文件在`~/.oh-my-zsh/themes`目录下，你可以通过修改`~/.zshrc`文件的`ZSH_THEME`参数值随意选择主题，也可以编辑`~/.oh-my-zsh/themes`目录下的主题文件满足自己的变态需求。

- 别名：

  zsh的别名配置在用户当前目录的`.aliases`文件里，即`~/.aliases`。比如：别名：`alias ..="cd .."`，则你只需要在命令行输入`..`，即可以返回上级目录。

  zsh的牛逼之处在于不仅可以设置通用别名，还能针对文件类型设置对应的打开程序，比如：`alias -s html=subl`，则在你安装了Sublime Text的命令行工具的情况下，你只需要在命令行输入`hello.html`，zsh会为你自动打开Sublime Text并读取hello.html。

- 插件：

  oh my zsh提供了完善的插件体系，相关的文件在`~/.oh-my-zsh/plugins`目录下，大家可以根据自己的实际学习和工作环境采用。插件的列表和说明请查看[插件的官网](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview)，也可以看一下相关目录的插件子目录下`README.md`文件。
  
  插件配置也是在`~/.zshrc`里配置，找到`plugins`关键字，你就可以加载自己的插件了。目前我使用的插件配置为：
  
  ```
  plugins=(git autojump osx history)
  ```

### zsh-syntax-highlighting && zsh-autosuggestions
  ```
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
  git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
  source .zshrc
  ```

### exa
  ```
  brew install exa
  cat >> ~/.zshrc << EOF
  alias ll="exa -l"
  alias l="exa"
  alias ls="exa"
  alias la="exa -la"
  alias tree="exa -T"
  EOF
  ```
### AutoJump

[autojump](https://github.com/wting/autojump)是Mac和Linux上一个命令行工具，它可以使用快捷命令，直接跳转到配置好的或历史的目录，而不用管现在身在何处。

***安装方法：***

- 安装autojump

  ```
  brew install autojump
  ```

- 修改`~/.zshrc`文件

  用vim或你喜欢的其他编辑器打开`~/.zshrc`，找到`plugins=`的行添加autojump。如：`plugins=(git autojump)`。然后，在文件的末尾添加如下新的一行：

  ```
  [ -f $(brew --prefix)/etc/profile.d/autojump.sh ] && . $(brew --prefix)/etc/profile.d/autojump.sh
  ```

- 保存退出，重启终端或执行`source ~/.zshrc`让配置生效。

***使用说明：***

- 显示帮助信息：`autojump --help`。
- 跳到全路径名中包含字符串`foo`的目录：`j foo`，如`/Users/someone/prefix-foo-suffix/subdir1/suddir2`。

- 跳到子路径名中包含字符串`foo`的目录：`jc foo`，如`/Users/someone/subdir1/suddir2/prefix-foo-suffix`。

- 使用文件管理器（Finder或其他）打开全路径名中包含字符串`foo`的目录：`jo foo`。

- 使用文件管理器（Finder或其他）打开子路径名中包含字符串`foo`的目录：`jco foo`。

- 添加快捷目录：`j -a s '/Users/XXX/Desktop/code/shark’`，则执行`j s`将直接进入目录`/Users/XXX/Desktop/code/shark`

### Alfred

[Alfred](https://www.alfredapp.com)是Mac用户使用键盘的必备效率神器，配合大量Workflows，习惯之后可以大大减少操作时间。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本，也可以使用其限制部分功能的免费版。

***使用说明：***

- 上手简单，跟Mac自带的Spotlight使用方法类似，具体使用方法可以[参考此文](https://www.jianshu.com/p/e9f3352c785f)，大家也可以自行百度。

- 快速启动只是Alfred的基本功能，Alfred的真正强大之处在于用户可以根据自己的实际需要，自定义各种工作流。网上有大量使用者提供的现成扩展，网址包括：

  - Alfred官网：<https://www.alfredapp.com/workflows/>

  - Packal：<http://www.packal.org/>

  - AlfredWorkflow：<http://www.alfredworkflow.com/>

  - 常用Workflow：<https://www.jianshu.com/p/0e78168da7ab>

### PopClip

[PopClip](http://pilotmoon.com/popclip/)是Mac用户日常工作中另一款必不可少的效率神器，配合丰富的插件，可以实现鼠标一键多种操作。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

***使用说明：***

- PopClip是一个划词工具，依附于各类小插件，我们能获得更多强大的功能来提升我们的操作效率。具体使用方法可以[参考此文](https://www.ifanr.com/app/507343)，大家也可以自行百度。

- PopClip提供了大量的扩展，扩展的网址为：<http://pilotmoon.com/popclip/extensions/>。插件的使用介绍可以[参考此文](https://www.ifanr.com/app/660172)。我安装的插件包括：

  - Google搜索
  - Baidu搜索
  - 剪切
  - 拷贝
  - 复制
  - 复制+回车
  - 删除
  - 全选
  - 打开链接
  - 字典
  - Google翻译
  - Say
  - 等等

### Path Finder

[PathFinder](https://cocoatech.com/)是Mac上一款类似于Finder的系统文件管理器。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

***使用说明：***

- 双窗格的文件浏览器
- 快速地管理您的硬盘驱动器上的多个位置，并在一个窗口中的选项卡
- 您的文件如何重新排序呈现，以满足您的个人喜好
- 快速轻松地查看隐藏文件和Mac OS X包内的导航信息
- 访问经常使用的文件夹，文件和应用程序下架，并保存多个货架设置，以适应不同的活动
- 暂停投递堆栈把文件转换成供将来使用的拖动和拖放操作
- 创建和转换磁盘映像
- 访问OS X命令行

### SecureCRT和SecureFX

[SecureCRT](https://www.vandyke.com/products/securecrt/)和[SecureFX](https://www.vandyke.com/products/securefx/)是一款多平台上支持SSH（SSH1和SSH2）的终端仿真程序。大家可能会说，前面已经推荐了iTerm2了，为啥还推荐这个。我使用中的经验是，SecureCRT比较适合用于远程服务器上的操作，其主要优点如下：

  - 强大的Session保存功能。可以将服务器地址、登录名、登录密码、初始路径等信息都保存起来，使用时一键点击即可。PS：Mac版SecureCRT无法保存密码的问题解决方案如下：点击`Preferences` -> `General`，取消勾选`Use Keychain`。

  - 快速Session克隆功能。右键点击打开连接的Tab，选择`Clone Session`即可快速创建相同连接的窗口。

  - 与SecureFX集成，快速上传/下载服务器上的文件。这可能是SecureCRT区别等其他工具的最大特点，其他iTerm2、XShell等终端程序都需要第三方程序实现文件上传/下载的功能，且无法同步服务器地址、登录名、登录密码等Session信息。SecureFX支持FTP、SFTP、FTP over SSH2和SCP等文件传输协议，同时还具有文件批量传输、目录同步等功能。

***安装方法：***

 - 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

### ShadowsocksX

[ShadowsocksX](https://github.com/shadowsocks/ShadowsocksX-NG/)是一款Mac上科学上网的工具。作为一个程序员，需要经常Google搜索和访问使用Google JS组件的网站，因此能否快速的的科学上网，是提高开发效率的必备手段。

***安装方法：***

```sh
brew cask install shadowsocksx-ng
```

***使用说明：***

- 我个人的使用习惯是，开机即自动启动ShadowsocksX，工作在PAC自动模式下，开启HTTP Proxy代理服务器。

- 浏览网页时，平时不使用ShadowsocksX。需要翻墙时，使用浏览器安装的代理切换插件（如：SwitchyOmega）一键切换到代理模式翻墙。

- 在iTerm2等终端界面中，如需要使用ShadowsocksX翻墙，点击任务栏上的ShadowsocksX图标，点击`Copy HTTP Proxy Shell Export Line`将代理设置的命令行拷贝到剪贴板，然后在iTerm2等终端界面上按`Cmd+V`粘贴命令行。则此终端界面后续的操作，会自动使用ShadowsocksX的代理翻墙访问。

  ```sh
  export http_proxy=http://0.0.0.0:1087;export https_proxy=http://0.0.0.0:1087;
  ```

- 其他软件，如存在Proxy设置，可以通过设置Proxy参数使用ShadowsocksX翻墙。

- 公共的ShadowsocksX服务器由于使用者多，速度都比较慢或存在使用限制，因此我们搭建了私用的ShadowsocksX服务器，参数如下：

  - 日本亚马逊服务器：

  ```
  "server" : "45.32.16.122",
  "server_port" : 10010,
  "password" : "imagetransgwf",
  "method" : "rc4-md5",
  ```

  - 香港阿里云服务器：

  ```
  "server" : "47.89.41.191",
  "server_port" : 8989,
  "password" : "imagetrans",
  "method" : "aes-256-cfb",
  ```

### ZeroTier

[ZeroTier](https://www.zerotier.com/)是一款多平台的内网穿透工具。ZeroTier非常简单易用，能实现虚拟局域网的组建，让你可以在外网也能连回家中、学校、办公室的电脑获取资料和数据。

ZeroTier与其他内网穿透工具，如：[n2n](https://github.com/ntop/n2n)、[ngrok](https://ngrok.com/)、[frp](https://github.com/fatedier/frp)等的优势如下：

  - 配置与使用都非常简单，堪称「无配置，零基础」，小白也能用。
  - 支持非常多的平台，包括：Windows、MacOS、Linux桌面平台，iOS、Android手机平台，以及QNAP、Synology、Western Digital等NAS平台，还支持OpenWRT/LEDE路由器平台。
  - ZeroTier通过全球的多台服务器中转数据，实测速度比n2n要快。另外，也可以通过自建中转节点的方式，加快速度。
  - ZeroTier的可以免费连接100台设备（包括服务器、电脑、手机和路由器），一般情况下是足够的。实在不够，可以多申请几个免费账号。

***安装方法：***

```sh
brew cask install zerotier-one
```

***使用说明：***

- ZeroTier的使用，请参考[此文](https://www.appinn.com/zerotier-one/)，或访问[官网](https://www.zerotier.com/download.shtml)

- 网上有人反应ZeroTier的中转服务器在高峰时段会断网（目前我没遇到过），解决的办法是自建中转服务器，官方的叫法是moon。具体方法请参考[此文](http://www.lucktu.com/archives/766.html)或[官方文档](https://www.zerotier.com/manual.shtml#4_4)。

- 根据ZeroTier的原理，理论上也可以通过ZeroTier的节点实现科学上网的功能，但具体方法尚未尝试。

### Moom

[Moom](https://manytricks.com/moom/)是Mac上专注于窗口位置及尺寸控制的最佳代表。值得称赞的是，安装完毕后的默认配置已经足以满足大部分日常需求，这点对于那些不擅长操作纯英文应用的用户来说是非常便利的。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

***使用说明：***

- 具体使用方法可以[参考此文](https://sspai.com/post/27142)，大家也可以自行百度。

### CheatSheet

[CheatSheet](http://www.mediaatelier.com/CheatSheet/)是一款Mac上能够显示当前程序的快捷键列表的免费软件，默认的快捷键是长按`⌘`。

![CheatSheet](http://www.mediaatelier.com/CheatSheet/imgs/main.png)

***安装方法：***

```sh
brew cask install cheatsheet
```

### Stow和dotfiles

[Stow](http://www.gnu.org/software/stow/)是Mac和Linux上管理符号链接（symlink）的一个小工具。主要用于symlink你的[dotfiles](http://dotfiles.github.io/)，如：emacs、git、zsh等的配置文件。

***安装方法：***

```
brew install stow
```

***使用说明：***

安装了stow之后，我们可以开始symlink自己的dotfiles了。完整使用stow和dotfiles的流程可以参考我的dotfiles<https://gitee.com/gebing/dotfiles>。

当你的dotfiles都妥妥的symlink到`~/dotfiles`后，push到github上就再也不怕换电脑了。

## 3. 开发工具

### Java版本管理

现在Mac都不自带JDK了，所以进行Java开发的话，需要下载JDK。Homebrew Cask提供了自动安装和卸载功能，能够自动从官网上下载并安装JDK。

***安装方法：***

```sh
brew cask install java
```

如果你需要安装JDK8或者其他旧版本，可以使用`homebrew-cask-versions`：

```sh
brew tap caskroom/versions
brew cask install java8
```

***使用说明：***

- 在Mac上，你可以同时安装多个版本的JDK。你可以通过命令`/usr/libexec/java_home -V`来查看安装了哪几个JDK。在Mac上默认情况下系统会使用已经安装的最新版本的Java，但是你可以设置环境变量JAVA_HOME来更改其指向。

- 在Shell环境下，可以通过执行`export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)`这种方式来设置使用特定版本的Java。

- 添加以下脚本到当前Shell配置文件中：`~/.zshrc`或者`~/.bash_profile`。

  ```sh
  function jdk() {
      export JAVA_HOME=`/usr/libexec/java_home -v $@`
      echo "JAVA_HOME switched to '$JAVA_HOME'."
  }
  ```
  
  这样我们就可以通过输入一条命令进行版本切换了：

  ```sh
  jdk 1.8
  jdk 9
  jdk 10
  ```

- 在GUI环境下，由于无法在执行前无法启动Shell来设置`JAVA_HOME`，因此我使用了一个软件来设置`JAVA_HOME`环境变量，[EnvPane](https://github.com/hschmidt/EnvPane)。安装方法和设置方法请参考网站。

- 网上有很多文章推荐使用[jEnv](https://github.com/gcuisinier/jenv)来管理和切换Java版本，且jEnv也可以用brew安装，但我不推荐使用。理由如下：

  - 需要手动把`eval "$(jenv init -)"`加入profile，没有Oh My Zsh插件。

  - 需要手动添加JDK，不会自动采集系统JDK。相反，Mac已经提供`/usr/libexec/java_home`工具来管理安装的JDK。

  - 需要执行`jenv rehash`。这个是跟rbenv学的。

### Node版本管理

Node的版本管理工具有很多，常用的会有以下几个：

* [nvm](https://github.com/creationix/nvm)

  该工具是一个类似RVM的工具，命令安装方式也基本一样，可以参考官方文档。

* [n](https://github.com/tj/n)

  一个简单的工具，安装方式类似nvm，无需额外配置。具体参考官方文档。

* [nodenv](https://github.com/nodenv/nodenv)

  该工具是一个类似rbenv的工具，命令和其完全一样，安装和配置也一样。

  ```
  brew install nodenv
  ```

  你需要手动添加以下配置到`~/.zshrc`或者`~/.zprofile`文件里。

  ```sh
  export PATH="$HOME/.nodenv/bin:$PATH"
  eval "$(nodenv init -)"
  ```

目前根据GitHub Stars，这三个管理工具的排名依次是nvm、n、nodenv。

### JetBrains全家桶

JetBrains全家桶是指[JetBrains公司](https://www.jetbrains.com/)开发的多平台上系列IDE工具，包括Intellij IDEA、PhpStorm、PyCharm、WebStorm、AppCode、GoLand、CLion、DataGrip等。强烈建议大家转到JetBrains全家桶，抛弃Eclipse、Android Studio等其他IDE。使用JetBrains全家桶有以下的优点：

  - 相同的操作方式和快捷键定义。

  - 优异的性能和使用体验，不再会出现Eclipse经常出现的卡死的情况。

  - 即时代码分析和智能提示，会自动帮助你分析和提示你代码中的错误，包括拼写错误、语法错误、使用错误等。

  - 强大的代码重构功能，包括修改函数的函数名、参数名、参数顺序，甚至是返回值类型。

  - 集成调试器。JetBrains全家桶所有的IDE工具都集成了调试器工具，不管你是WEB工程、JS工程、手机工程还是服务器工程，都可以轻松的调试。

  - 太多太多了...

***安装方法：***

- 先安装JetBrains Toolbox。

  ```sh
  brew cask install jetbrains-toolbox
  ```

- 在JetBrains Toolbox中安装JetBrains全家桶的其他IDE工具，主要可安装IDE工具包括：

  | 工具名称 | 主要开发语言 | 主要开发目标 | 收费/免费 | 推荐指数 | 
  | --- | --- | --- | --- | --- |
  | Intellij IDEA Community | Java/Scala/Groovy等 | Java应用/Java服务器/Web应用/Android应用 | 免费 | ***** |
  | Intellij IDEA Ultimate | Java/Scala/Groovy等 | Java应用/Java服务器/Web应用/Android应用 | 收费 | *** |
  | PhpStorm | PHP | PHP服务器/Web应用 | 收费 | **** |
  | WebStorm | HTML/Javascript | Web应用 | 收费 | **** |
  | PyCharm Community | Python | Python应用/Web应用 | 免费 | **** |
  | PyCharm Professional | Python | Python应用/Web应用 | 收费 | **** |
  | RubyMine | Ruby | Ruby应用/Web应用 | 收费 | *** |
  | GoLand | Go | Go应用/Web应用 | 收费 | **** |
  | CLion | C/C++ | C/C++应用 | 收费 | *** |
  | AppCode | Object C/Swift | IOS应用 | 收费 | *** |
  | DataGrip | SQL | 数据库应用 | 收费 | *** |
  
- JetBrains全家桶中收费IDE工具的激活方法：

  启动对应的IDE工具，如：PhpStorm，在激活界面中选择`License Server`，并在License server address的输入框中输入：`http://47.94.156.248:10001`，点击`Activate`按钮。

  PS：收费的IDE工具目前主要的破解方式有以下3种：
  
  - 激活服务器。由于最新版本的JetBrains全家桶屏蔽了本机上的激活服务器和网上一些公开的激活服务器，目前只能使用我们自己搭建的私用激活服务器。
  
  - 破解激活。

  - 网上搜寻可用的激活码。

***使用说明：***

- JetBrains全家桶使用的入门门槛较高，但熟悉后会发现其非常好用的。具体使用说明，可以参考网上的[“IntelliJ IDEA 使用教程”](http://wiki.jikexueyuan.com/project/intellij-idea-tutorial/)。

- JetBrains全家桶有几套内建的快捷键方案（Keymap）。其中适用于Mac的有`Mac OS X`和`Mac OS X 10.5+`两种。区别是:

  - `Mac OS X`方案和其他平台上的快捷键类似，
  - `Mac OS X 10.5+`更加符合Mac常用的快捷键。

  一个团队使用不同的快捷键会严重影响效率，建议统一快捷键方案。我建议使用`Mac OS X`方案，因为与Windows平台上的快捷键类似。
  
- 	JetBrains全家桶的强大功能，还表现在其强大和丰富的插件库。通过安装不同的插件，基本上可以实现全开发语言的编程。我安装的插件列表如下：

  | 插件名称 | 插件介绍 | 官网地址 | 
  | --- | --- | --- |
  | .ignore |	各类版本控制忽略文件生成工具 | <https://github.com/hsz/idea-gitignore> |
  | ADB Idea | Android应用开发辅助工具 | <https://github.com/pbreault/adb-idea> |
  | Alibaba Java Coding Guidelines | 阿里巴巴出的代码规范检查插件 | <https://github.com/alibaba/p3c> |
  | BashSupport | Bash语法支持 | <https://github.com/jansorg/BashSupport> |
  | CheckStyle-IDEA | 代码规范检查 | <https://github.com/jshiell/checkstyle-idea/> |
  | Dash | Dash搜索工具| <https://github.com/gdelmas/IntelliJDashPlugin> |
  | Database Navigator | 数据库工具 | <http://www.jetbrains.net/confluence/display/CONTEST/Database+Navigator> |
  | Docker integration | Docker管理工具 | <https://plugins.jetbrains.com/plugin/7724-docker-integration> |
  | Erlang | Erlang语言支持 | <http://ignatov.github.com/intellij-erlang> |
  | FindBugs-IDEA | 潜在Bug检查 | <http://andrepdo.github.io/findbugs-idea> |
  | Gitee	| 开源中国码云插件 | <https://gitee.com/oschina/intellij-gitosc> |
  | Grep Console	| 自定义设置控制台输出颜色 | <https://github.com/krasa/GrepConsole> |
  | GsonFormat | 把JSON字符串直接实例化成类 | <https://github.com/zzz40500/GsonFormat> |
  | JRebel Plugin | 代码热部署 | <https://zeroturnaround.com/software/jrebel/> |
  | Key Promoter X | 快捷键提示 | <https://github.com/halirutan/IntelliJ-Key-Promoter-X> |
  | Lombok Plugin |	Lombok注解框架插件 | <https://github.com/mplushnikov/lombok-intellij-plugin> |
  | Markdown Navigator	| Markdown编辑器 | <http://github.com/vsch/idea-multimarkdown> |
  | Maven Helper | Maven辅助插件 | <https://github.com/krasa/MavenHelper> |
  | OpenInTerminal | 任意位置打开终端 | <https://github.com/luktom/OpenInTerminal> |
  | Protobuf Support | Protobuf语言支持 | <https://github.com/protostuff/protobuf-jetbrains-plugin> |
  | Scala | Scala语言支持 | <http://www.jetbrains.net/confluence/display/SCA/Scala+Plugin+for+IntelliJ+IDEA> |
  | String Manipulation | 字符串驼峰式/下划线命名转换工具  | <https://github.com/krasa/StringManipulation> |
  | Swagger Codegen | Swagger代码生成器| <https://github.com/jimschubert/intellij-swagger-codegen> | 
  | Swagger Plugin | Swagger语法支持| <https://github.com/zalando/intellij-swagger> |
  | Translation | 翻译插件 | <https://github.com/YiiGuxing/TranslationPlugin> |

### Visual Studio Code

如果说JetBrains全家桶是IDE工具的神器，那么[Visual Studio Code](https://code.visualstudio.com/)就是文本编辑器的神器。如果只做些简单的代码和文本编辑，就需要Visual Studio Code这样轻量级的编辑器了。相比其他同类产品，Visual Studio Code比[Sublime Text](https://www.sublimetext.com/)开源，比[Atom](https://atom.io/)更快。虽然是轻量级工具，由于其强大和丰富的插件，其功能一点不比普通的IDE工具差。

***安装方法：***

```sh
brew cask install visual-studio-code
```

***使用说明：***

- Visual Studio Code的使用方法可以参考[中文手册](https://jeasonstudio.gitbooks.io/vscode-cn-doc/)或[使用技巧](https://zhuanlan.zhihu.com/p/22880087)。


### SmartGit

[SmartGit](https://www.syntevo.com/smartgit/)是一款跨平台优秀的Git版本管理的图形化客户端。相对于Git命令行，SmartGit提供了很多自动化和人性化功能，强烈推荐。

***安装方法：***

```sh
brew cask install smartgit
```

***使用说明：***

- SmartGit是收费软件，但在首次启动时License类型选择`for non-commercial use only`即可免费使用。

PS：

- 如果你还使用SVN进行版本管理，建议使用同一家公司出品的[SmartSVN](https://www.smartsvn.com/)。

  - SmartSVN的安装方式为：
  
    ```sh
    brew cask install smartsvn
    ```

  - 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载注册码生成器。

- 网上有人推荐使用[SourceTree](https://www.sourcetreeapp.com/)。SourceTree也是一款不错的Git版本管理的图形化客户端，以我个人短暂的使用经验来看，其自动化处理冲突的功能上比SmartGit稍弱。SourceTree的主要优点在于：（1）汉化；（2）免费使用。

  - SourceTree的安装方法为：

    ```sh
    brew cask install sourcetree
    ```

  - 用brew-cask安装会自动增加命令行工具`stree`到`$PATH`里。在命令行中输入`stree`可以快速用SourceTree打开当前Git仓库。详细用法请参见`stree --help`。

### 微信开发者工具

[微信开发者工具](https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html)是微信出品的微信/小程序开发调试工具。微信开发者工具可以帮助开发者简单和高效地开发和调试微信/小程序，集成了公众号网页调试和小程序调试两种开发模式。

***安装方法：***

```sh
brew cask install wechatwebdevtools
```

### Navicat Premium

[Navicat Premium](https://www.navicat.com/en/products/navicat-premium)是一款多平台上数据库管理和开发工具。使用Navicat Premium可以同时连接MySQL、MariaDB、SQL Server、Oracle、PostgreSQL 和 SQLite数据库。它与Amazon RDS、Amazon Aurora、Amazon Redshift、Microsoft Azure、Oracle Cloud、阿里云和腾讯云等云数据库兼容。你可以快速轻松地创建、管理和维护数据库。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

### Studio 3T

[Studio 3T](https://studio3t.com/)是一款优秀的跨平台MongoDB数据库管理工具。Studio 3T相比同公司出品的免费版MongoDB数据库管理工具[Robo 3T](https://robomongo.org/)，其功能更加强大，包括：

- 可视化查询Builder

- 方便的数据编辑

- 表格/树状/Json数据的展现方式

- SQL查询/导入/导出

- Mongo命令智能提示

- 数据导入/导出

- 数据比较/同步

***安装方法：***

```sh
brew cask install studio-3t
```

***使用说明：***

- Studio 3T是收费软件，但在可以将License类型改成`Non-Commercial License`即可免费使用绝大部分功能。

### FastoRedis

[FastoRedis](hhttps://www.fastoredis.com/)是一款优秀的跨平台Redis数据库管理工具。相比其他Redis工具（如：[Redis Desktop Manager](https://redisdesktop.com/)、[Medis](https://github.com/luin/medis)等），其最大的特定是支持Redis Cluster和Redis Sentinel。

***安装方法：***

- FastoRedis号称是开源的，但必须订阅其服务才能下载安装包。目前只有之前我下载的v1.8.6版本Mac平台的安装包，大家可以从本文结尾处的[分享链接](#5-分享链接)下载该版本。

- 出品FastoRedis的公司还出品了[FastoNoSQL](https://www.fastonosql.com/)，是一款支持包含Redis在内多个NoSQL数据库的工具。FastoNoSQL号称是开源的，但必须订阅其服务才能下载安装包。而其Github上的[源码](https://github.com/fastogt/fastonosql)，由于缺少私有的子模块而无法编译。目前FastoNoSQL其实是伪开源，但是值得随时关注其动向。

### DbSchema

[DbSchema](https://www.dbschema.com/)是一款跨平台的数据库设计工具。使用DbSchema可以设计数据库，探索和编辑数据，编写和执行查询，从文件创建报表，加载数据，生成随机数据，打印模式图表或生成文档或Json Schema文件。DbSchema除了可以通过JDBC使用传统SQL数据库，还特别原生支持MongoDB。

***安装方法：***

```sh
brew cask install dbschema
```

***使用说明：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载注册码生成器。

## 4. 开发辅助

所谓“工欲善其事必先利其器”，作为一个优秀的程序员，必须掌握相关的辅助工具去快速开发和查找问题。这里就主要介绍相关的开发辅助工具。

### Dash

[Dash](https://kapeli.com/)是Mac上的API文档浏览和代码片段管理的神器。Dash自带了丰富的API文档，涉及各种主流的编程语言和框架，包括但不限于:ActionScript，Android，C++，CAppuccino，Cocos2D，Cocos3D，Corona，CSS，Django，Groovy，HTML，Java，JavaFX，JavaScript，jQuery，Kobold2D，Lua，MySQL，Node.js，Man Pages，Perl，PHP，Python，Ruby，Ruby on Rails，Scala，Sparrow，SQLite，Unity 3D，WordPress，XSLT，XUL等等。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

***使用说明：***

- Dash的使用非常简单，安装完Dash后，进入`Preferrence` -> `Downloads`，查找并选择你需要的API文件，点击下载即可。

- 查找API文档时，既可以在搜索栏在全部下载的文档中搜索关键词，也可以先点击特定的API文档后再输入关键词，在指定的API文档内搜索。

- 进入API详情页面后，也可以按下`Cmd+F`在页面内进行搜索。

### Charles

[Charles](https://www.charlesproxy.com/)是一款跨平台的HTTP代理/反向代理/HTTP跟踪工具。当浏览器或客户端连接Charles的代理或端口转发访问服务器时，Charles可以监控浏览器或客户端发送和接收的所有数据。它允许开发者查看所有连接互联网的HTTP通信，包括：request、response和HTTP headers（包含cookies与caching信息）。其主要功能包括：
  - 支持HTTP代理和Socks代理。可以作为标准代理服务器。
  - 支持SSL代理。可以截取分析SSL的请求。
  - 支持端口转发。可以在非HTTP请求或无法设置代码的场景下使用。
  - 支持流量控制。可以模拟慢速网络以及等待时间较长的请求。
  - 支持AJAX调试。可以自动将json或xml数据格式化，方便查看。
  - 支持AMF调试。可以将Flash Remoting或Flex Remoting信息格式化，方便查看。
  - 支持重发网络请求，方便后端调试。
  - 支持修改网络请求参数，支持网络请求的截获并动态修改。

我们在开发过程中，经常会出现前端和后台的工程师在纠缠发送或返回数据错误的问题，这个时候使用Charles可以立刻让问题显现出来。Charles比使用TcpDump、WireShark等抓包工具有以下的优势：
  - 使用简单，不需要在客户端或服务器安装任何程序，随时使用。
  - 清晰明了，只显示请求和应答的数据并可以以多种方式展示。
  - 功能强大，请求和应答的数据可以动态修改。

PS：[Fiddler](https://www.telerik.com/fiddler)跟Charles类似，但功能和方便性不如远远Charles，因此不推荐使用。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

***使用说明：***

- Charles的使用：<https://www.jianshu.com/p/0fee626ffbb0>
- 移动应用抓包调试利器Charles：<https://www.jianshu.com/p/68684780c1b0>
- https://www.telerik.com/fiddler

### Swagger

[Swagger](https://swagger.io/)是目前最受欢迎的REST APIs文档生成工具。Swagger是一个规范和完整的框架，用于生成、描述、调用和可视化REST风格的Web服务。Swagger是由以下的部分组成：

  - [Swagger规范](https://swagger.io/specification/)
  
    Swagger规范（即OpenAPI规范）使我们可以用指定的JSON或者YAML文件来描述API定义，包括请求、应答、认证等。我个人建议使用YAML来写，原因是它更简单。

  - [Swagger Editor](https://swagger.io/swagger-editor/)

    Swagger Editor是一个基于浏览器的在线Swagger文档编辑工具。它提供语法高亮、自动完成、即时预览等功能。
    
    PS：除此之外，我们还可以通过以下方法生成Swagger文档：
    
      - 在其他编辑器或IDE上（如：Visual Studio Code、Intellij IDEA）通过编写Swagger编辑器插件编写Swagger文档。具体可以在[此网址](https://swagger.io/open-source-integrations/)查找相关插件和工具。

      - 通过各种语言版本的、根据注释生成Swagger文档的非官方工具，包括：swagger-springmvc、swagger-php等。具体可以在[此网址](https://swagger.io/open-source-integrations/)查找相关插件和工具。

      - 在第三方API网站或工具上编辑生成API定义后，导出Swagger文档。目前支持导出Swagger文档的API网站包括：

        - [SoSoApi](http://www.sosoapi.com/)

        - [IBM API Connect](https://console.bluemix.net/docs/services/apiconnect/index.html)

        其他一些网站（如：[ShowDoc](https://www.showdoc.cc)、[RAP2](http://rap2.taobao.org/)等，都不支持导出Swagger文档。

  - [Swagger Codegen](https://swagger.io/swagger-codegen/)
  
    Swagger Codegen是一个根据Swagger文档内容自动生成相关API接口代码的工具。Swagger Codegen可以生成几乎所有开发语言和开发平台下对应API接口的代码，包括:

    - 客户端: ActionScript, Ada, Apex, Bash, C#, C++, Clojure, Dart, Elixir, Elm, Eiffel, Erlang, Go, Groovy, Haskell, Java (Jersey1.x, Jersey2.x, OkHttp, Retrofit1.x, Retrofit2.x, Feign, RestTemplate, RESTEasy, Vertx, Google API Client Library for Java, Rest-assured), Kotlin, Lua, Node.js (ES5, ES6, AngularJS with Google Closure Compiler annotations) Objective-C, Perl, PHP, PowerShell, Python, R, Ruby, Rust (rust, rust-server), Scala (akka, http4s, swagger-async-httpclient), Swift (2.x, 3.x, 4.x), Typescript (Angular1.x, Angular2.x, Fetch, jQuery, Node)

    - 服务器端: Ada, C#, C++, Erlang, Go, Haskell, Java (MSF4J, Spring, Undertow, JAX-RS: CDI, CXF, Inflector, RestEasy, Play Framework, PKMST), Kotlin, PHP (Lumen, Slim, Silex, Symfony, Zend Expressive), Python (Flask), NodeJS, Ruby (Sinatra, Rails5), Rust (rust-server), Scala (Finch, Lagom, Scalatra)

    - API文档: HTML, Confluence Wiki

    - 配置文件: Apache2

    - 其他: JMeter

    PS：除此之外，很多编辑器或IDE也都提供Swagger Codegen的非官方插件，实现在编辑器或IDE中生成API接口代码。   

  - [Swagger UI](https://swagger.io/swagger-ui/)
  
    Swagger UI是一个根据Swagger文档内容展示和测试API接口的工具。Swagger UI可以给前端展示相关的API文档，并像使用Postman以及Curl命令一样，通过Web界面进行接口测试。Swagger UI是一个静态依赖的网站，可以很方便的集成到现有的、使用不同语言开发（如Java、Php等）的网站中。

  - [Swagger Inspector](https://swagger.io/swagger-inspector/)

    Swagger Inspector是一个根据Swagger文档内容在线测试API接口的工具。除了可以测试Swagger规范的接口外，Swagger Inspector还可以测试标准HTTP、XML、WDSL的API。另外，Swagger Inspector还可以根据现有接口反向生成Swagger文档。

具体Swagger的生态图，请见下图：

![swagger-ecosystem](resource/swagger-ecosystem.png)

### Paw

[Paw](https://paw.cloud/)是一款Mac上HTTP客户端模拟测试工具，可以让Web开发者设置各种请求Header和参数，模拟发送HTTP请求，测试响应数据，支持OAuth、HTTP Basic Auth、Cookies等，这对于开发Web服务和REST接口的应用很有帮助，非常实用的一款Web开发辅助工具。

***安装方法：***

- 此工具是收费软件，大家可以从本文结尾处的[分享链接](#5-分享链接)下载破解版本。

***使用说明：***

- PAW提供一个全功能的HTTP Client，能够模拟全部基于HTTP的API请求，并支持几乎所有数据格式（比如：Text、File、JSON、XML等）。PAW的HTTP Client的强大的功能包括：能够根据自定义规则动态生成请求数据、数据生成的Extension、及根据服务器环境参数切换请求数据。

- PAW提供了强大的API管理功能，能够导入Swagger（即Open API）、BluePrint、WSDL等API定义文档，查看API接口定义，导出现有API定义到API文档。

- PAW另一个强大的功能是其代码生成的功能，通过PAW的官方和第三方Extension，PAW可以根据API接口定义生成各种开发语言相应的API请求代码，包括：cURL、HTTP、Swift、Objective-C、Python、JavaScript、 Node、Ruby、PHP cURL、Java、Go等。

- PAW还提供了团队开发的功能，包括：工程同步、项目分支等。

### IBM API Connect

[IBM API Connect](https://console.bluemix.net/docs/services/apiconnect/index.html)是IBM提供的多平台上一个免费API接口管理工具。IBM API Connect可以定义/编辑API接口、定义/编辑实体模型和对应的数据源、自动生成实体模型对应的API接口、模拟和测试API接口。

***安装方法：***

IBM API Connect是一个离线工具（但需要BM BlueMix的账号和登录验证），运行在你的本机，通过命令行和浏览器来操作。安装方法请参考IBM的[相关文档](https://console.bluemix.net/docs/services/apiconnect/creating_apis.html)。安装步骤如下：

  1. 申请并创建[IBM BlueMix](https://console.bluemix.net/)的免费账号。

  1. 安装node.js。

      ```sh
      brew install node
      ```

  1. 安装API Connect。

      ```sh
      npm install -g apiconnect
      ```

安装完成后，你可以执行`apic`显示API Connect的命令行帮助信息，可以执行`apic edit`启动API Designer界面，也可以执行`apic loopback`创建API工程。

***使用说明：***

- API Connect可以通过命令行和浏览器两种方式操作，具体使用请参考[IBM网站](https://console.bluemix.net/docs/services/apiconnect/apic_overview.html)和[入门教程](https://console.bluemix.net/docs/services/apiconnect/tutorials/tut_create_api_node.html)。

- API Connect使用了node.js的API框架[LoopBack](https://loopback.io/)作为其API网关和API服务端。我们可以修改LoopBack以改变其API网关和API服务端的行为。具体请参考LoopBack官方网站。

### Regex101

[Regex101](https://regex101.com/)是一个在线正则表达式的开发和测试工具。网上在线或离线的正则表达式工具很多，但Regex101无疑是其中功能最全和最强大的。由于Regex101必须翻墙才能访问，因此我找到了一个[离线和汉化版Regex101](https://github.com/Zjmainstay/RegexTesterForMac)。

***安装方法：***

大家可以从本文结尾处的[分享链接](#5-分享链接)下载我修改后的版本，也可以从[GitHub](https://raw.githubusercontent.com/Zjmainstay/RegexTesterForMac/master/dist/Regex101.zip)上下载原版。

***使用说明：***

- 用户可以在Regex101中编写、测试、验证正则表达式，支持PHP、Javascript、Python和Golang等语言风格的正则表达式。

- Regex101会自动显示正则表达式的解释、测试的匹配/替换的过程和结果。同时Regex101提供正则表达式的快速参考和解释，便于大家编写。

- Regex101还提供了正则表达式对应代码的自动生成的功能，可以生成PHP、Javascript、Python、C#、Java、Ruby、Rust、Golang、Perl等多种语言的代码。

- Regex101还提供了代码库的功能，可以搜索网上共享的正则表达式。

## 5. 分享链接

前面推荐的软件有些是收费软件，需要破解。为了方便大家下载，这里给出我个人网盘上的共享链接，大家可以从中寻找并下载相应的破解软件。

4.3.1195 <https://pan.baidu.com/s/17MFg_yjhlzazIpcmgFxVqg> 提取码: 342c 
4.6.1263 <https://pan.baidu.com/s/1-7OdQ9rEgA_RQUgAMu5U2w> 提取码: 2sgp 


PS：
- 此共享链接中的破解软件会不定期更新，保证提供最新版本的破解软件。请大家下载后，仔细阅读相关的破解说明来操作。共享链接中目录，是针对不同软件的破解说明和汉化资源。

- 如果共享链接内的软件不是最新版的，表示当前版本的破解可以应用到最新版本。大家可以从软件官网上下载最新版本软件，再使用旧版中的破解文件破解即可。大家也可以直接到相应软件的目录中，执行下载相应的破解补丁。

## 参考资料

- [高效MacBook工作环境配置](http://blog.csdn.net/zen99t/article/details/54754896)
- [程序员如何优雅地使用Mac？](http://www.zhihu.com/question/20873070)
- [装点你的Dock：外观篇](http://sspai.com/33493)
- [Hacker's Guide to Setting up Your Mac](http://lapwinglabs.com/blog/hacker-guide-to-setting-up-your-mac)
- [Setting up a new (OS X) development machine](https://mattstauffer.co/blog/setting-up-a-new-os-x-development-machine-part-1-core-files-and-custom-shell)

