title: Install Zsh and Oh-my-Zsh in Ubuntu
date: 2015-08-19 10:58:57
categories: Notes
tags: [Zsh, Ubuntu, Technical Notes]
description: Install Zsh and Oh-my-Zsh in Ubuntu
---

* [Zsh](http://www.zsh.org/) is the most popular shell in Os X, when I turn to Ubuntu, installation of Zsh is the first thing what I did.

1. Try to find out what shell you are using
	
	> cat /etc/shells

	


先补充点东西

1.ubuntu中默认安装了那些shell

jiang@Linux:~$ cat /etc/shells # /etc/shells: valid login shells/bin/sh/bin/dash/bin/bash/bin/rbash

我的PC上有sh、dash、bash和rbash（这货是谁？）

2.当前正在运行的是那个版本的shell

jiang@Linux:~$ echo $SHELL/bin/bash

3.shell是什么
请google！！！
现在正式安装

安装zsh、git和wget：

jiang@Linux:~$ sudo apt-get install zsh git wget

获取并自动按照oh-my-zsh：

jiang@Linux:~$ wget --no-check-certificate https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh

替换bash为zsh：

jiang@Linux:~$ chsh -s /bin/zsh

设置zsh的参数：
安装完zsh后，在你的家目录下会有一个名为.zshrc的隐藏文件，可以 根据个人习惯配置zsh的参数，我就直接给出配置文件了
如有需要，请点击 这里 下载
下载完毕，你将得到一个名为_.zshrc的文件
先进入家目录，备份原来的.zshrc,然后重命名_.zshrc文件:

jiang@Linux:~$ cp .zshrc .zshrc.bak
jiang@Linux:~$ mv _.zshrc .zshrc

最后重启：

jiang@Linux:~$ sudo reboot

重启后，你将看到
20140305182546.png
OK，你也试试吧，祝你好运！
这里是LigeLaige…Jinqiang的博客，我正在努力做得更好…
