layout: post
title: MacVim setup 
description: First guide for MacVim 
tags: [MacVim, Mac]
---

>考虑到某同学要在 Mac Os X 上学习 vim 的需求，于是汇总一篇 MacVim 的初步指南。
>考虑到 github 和 gitcafe 的流行，在文中也涉及到某些 git 的应用

Vim 的学习曲线比较陡峭，所以建议日常的时候使用 Vim 做一些不紧急的文书工作，比如我写这篇 blog，就是在 vim 下使用[plasticboy/vim-markdownh](https://github.com/plasticboy/vim-markdown)插件来完成，虽然不如 mou 之类Markdown实时渲染写作 app专业，但是胜在编辑长文章的时候跳转查找批量编辑方便，顺便也对vim 的快捷键有一个复习。同时，对于在 window/Linux 上使用过 vim 的同学也可以逐步感受出 MacVim 和 Vim 的一些区别。	

声明：
1. 部分参考资料来自网络，已在在文末列出 Reference List  
2. 本文遵循 MIT 原则，转载请保留出处：woodjuice.github.io

<!--more-->

## MacVim install (MacVim安装指南)   

1. Click and Download Macvim. //下载 macvim，国内不能下载的同学请戳[这里](http://download.csdn.net/download/myscom/8008723） (适合10.9+系统)
2. Unzip the items and drag *MacVim.app* into Applicationsfolder. //解压缩文件，然后把MacVim拖到*应用程序*里
3. drag *mvim* into */usr/bin*, then you can use *mvim* to start Macvim. //为了能在终端打开 MacVim，可以将mvim 这个脚本拖进*/usr/bin*.  
4. If you need some help, type*:h mvim*. //要是丫出了啥妖蛾子需要帮助，就猛拍键盘输入*:h mvim*

<br></br>

## 配置文件存放点

**gvimrc**和**vimrc**  

**gvimrc**是来存放外观设置的地方，**vimrc**是来存放对 vim 本身设置的地方，一般来说我们需要修改的是用户自己的 vimrc 和 gvimrc，而不是在全局文件上做修改，以防出什么幺蛾子。
gvimrc 存放在*~/.gvimrc*  
vimrc 存放在*~/.vimrc*  

>“.”表示这是一个隐藏文件，如果你发现没有这两个文件存在，请直接手动创建一个  

<br></br>

### 一些小问题
**蛋疼的编码问题**  

MacVim always set encoding to *UTF-8* //MacVim 直接把编码设置成 UTF8

<pr></pr>


**标签功能**
simply type *:tabe $VIM/gvimrc*  

**更像 Mac 系统自带编辑器的方式移动光标**

>Text editors on Mac OS X lets the user hold down shift+movement key to extend
the selection.  Also, pressing a printable key whilst selecting replaces the
current selection with that character.   

Mac OS X 提供*shift+上下左右*来做文本选择，要替换的时候就敲入自己所需要的内容。要实现这个功能，只要*~/.vimrc*加入自己的设置

代码如下

```
if has("gui_macvim")  
	  let macvim_hig_shift_movement = 1  
	endif  
```
<br></br>

## 一些简单的命令和快捷键  

1.*so * 这是 source 命令，在对 vimrc 文件编辑以后，经常使用*so ~/.vimrc*进行编译和排错
2. 打开命令，快捷键为 command+o, 或者输入*open .*,比如要打开*vimrc*文件的时候就输入</pr>
>open ~/.vimrc

## 插件介绍 
<pr></pr>
  
**Vundle**
>Vundle 是一个将 vim 插件集中管理的插件，在使用 Vundle 之前必须要将各个插件包的各个部分分别解压到对应的文件夹，Vundle则会在*~/vim/bundle*文件夹里统一下载管理。

#### Vundle Setup  
<pr></pr>
>git clone http://github.com/gmarik/vundle.git ~/.vim/bundle/vundle*  

在*vimrc*文件里写入  
```  
set nocompatible    " be iMproved
filetype off        " required!
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
" let Vundle manage Vundle
" required!
Bundle *gmarik/vundle*
" vim-scripts repos
Bundle *vim-plugin-foo*
Bundle *vim-plugin-bar*
filetype plugin indent on    " required!
```  

安装就完成了  

#### Vundle Usage 

安装插件: *:BundleInstall*,即可以直接在*BundleInstall*后面跟上 github 上的项目名 
更新插件: *BundleUpdate*  
"卸载不在列表中的插件: *:BundleClean*  

也可以直接在*Vimrc*里写入要安装的插件名，比如：  
*Bundle ctrlp.vim*  //这个是在 vim-script 上的项目
*Bundle Valloric/YouCompleteMe**  //这个就是一个 github 上的repo

----------------

<pr></pr>


### Some plugins from Vundle
<pr></pr>
**plasticboy/vim-markdown**	

Markdown语法插件github地址请猛击：[plasticboy/vim-markdownh](https://github.com/plasticboy/vim-markdown/)

用 Vundle 安装时，先在*~/.vimrc*加入   

```  

Plugin *godlygeek/tabular*
Plugin *plasticboy/vim-markdown*
  
```
<pr></pr>
之后运行

```
:so ~/.vimrc
:PluginInstall
```  

第一条语句是用来source vimrc 文件的，第二条进行安装

**ZenCoding.vim**  

[ZenCoding](http://pepelsbey.net/2008/08/zen-html/)
这个插件估计都成为Html/Css 同学的标配插件。  

不多说，上演示[视频](http://v.youku.com/v_show/id_XMTM4NDQwNzgw.html)，尼玛太尼玛的快了  

ZenCoding墙内介绍请戳[这里](http://blog.chinaunix.net/uid-22414998-id-3183557.html)




### Reference

[vim插件管理Vundle](http://249wangmang.blog.163.com/blog/static/526307652012103010202962/)

[Git时代的VIM不完全使用教程](http://beiyuu.com/git-vim-tutorial/)

[国内对 ZenCoding比较详尽的一个](http://blog.chinaunix.net/uid-22414998-id-3183557.html)
