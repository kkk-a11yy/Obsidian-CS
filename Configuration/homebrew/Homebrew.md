- 参考资料：
	- "https://mirrors.ustc.edu.cn/help/brew.git.html"
	- "https://www.jianshu.com/p/e0471aa6672d"
- 使用代码：
``` r
/usr/bin/ruby -e "$(curl -fsSL https://cdn.jsdelivr.net/gh/ineo6/homebrew-install/install)"
```

- 常用语句
``` r
which brew  	展示brew的位置

brew search 	列出brew支持的软件
brew search <package_name>      搜索


brew install <package_name>     安装软件
brew uninstall <package_name>     卸载软件


brew update                     从服务器上拉取，并更新本地 brew 的包目录
brew upgrade <package_name>     更新软件
brew outdated                   查看你的软件中哪些有新版本可用
brew cleanup                    清理老版本。使用 `-n` 参数，不会真正执行，只是打印出真正运行时会做什么。

brew list							查看你安装过的包列表
brew list --versions            查看你安装过的包列表（包括版本号）

brew link <package_name>        将软件的当前最新版本软链到`/usr/local`目录下
brew unlink <package_name>      将软件在`/usr/local`目录下的软链接删除

brew info                       显示软件的信息 
brew deps                       显示包依赖

```


``` r
L
ksia@bogon ~ % /usr/bin/ruby -e "$(curl -fsSL https://cdn.jsdelivr.net/gh/ineo6/homebrew-install/install)"

  

Warning: Ruby版本Homebrew安装脚本已被废弃，新版脚本使用Bash重写。

请使用以下命令:

  /bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"

  



ksia@bogon ~ % /bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"

**==>** **Checking for `sudo` access (which may request your password)...**

Password:

**==>** **The following new directories will be created:**

/opt/homebrew/bin

/opt/homebrew/etc

/opt/homebrew/include

/opt/homebrew/lib

/opt/homebrew/sbin

/opt/homebrew/share

/opt/homebrew/var

/opt/homebrew/opt

/opt/homebrew/share/zsh

/opt/homebrew/share/zsh/site-functions

/opt/homebrew/var/homebrew

/opt/homebrew/var/homebrew/linked

/opt/homebrew/Cellar

/opt/homebrew/Caskroom

/opt/homebrew/Frameworks

**==>** **安装提示**

中文安装教程（建议收藏）：https://brew.idayer.com/

Mac下镜像飞速安装Homebrew教程（备用） ：https://zhuanlan.zhihu.com/p/90508170

如果你想换源，可以使用镜像助手：https://brew.idayer.com/guide/change-source/

  

安装遇到问题，可以通过讨论群寻求帮助。

也欢迎加群讨论，扫码关注公众号（湖中剑），回复'brew'加入讨论群。

  

█████████████████████████████████████

█████████████████████████████████████

████ ▄▄▄▄▄ █▀█ █▄▀▄ ▄ ▄▄██ ▄▄▄▄▄ ████

████ █   █ █▀▀▀█ ▀█▀▀▀▀▄▀█ █   █ ████

████ █▄▄▄█ █▀ █▀▀█▄▀ █▀▄ █ █▄▄▄█ ████

████▄▄▄▄▄▄▄█▄▀ ▀▄█▄▀ █▄▀ █▄▄▄▄▄▄▄████

████     ▀▄▄▄▄▀▄▀▄▄█▀▀█ █ ▀ ▀▄█▄▀████

████ ▀█▄▀▀▄  █▄█▀█ ▄██ █ ▀ ▄▄██▀█████

████ █   █▄ ▄ ▄█▄ ▀  ██ ▀ ▀▀▀▄ █▀████

████ ██▄██▄▀ █  ▄█▀ ▄▄▀▀ ▀ █▄█▄▀█████

████ ▄ ▀▄▄▄▀█▄ ▄▀     ▀ ▀█▀ ▀▀ █▀████

████ █ ▀▀▀▄█▄█▄█▀█▀▄ █▀▀▄▄█▄▄▄▄▀█████

████▄██▄▄█▄█▀▀▀█▄█▄ ▀▄▀█ ▄▄▄ ▀   ████

████ ▄▄▄▄▄ █▄▀  ▄█▄  ▄▀  █▄█  ▄▀█████

████ █   █ █ ▀▄▄ ▀▄ ▀███ ▄▄▄▄ ▄▀ ████

████ █▄▄▄█ █ ▄▄▀ ██▄▀▄▀▄ ▀▄   ▄ █████

████▄▄▄▄▄▄▄█▄▄█▄▄████▄█████▄▄█▄██████

█████████████████████████████████████

█████████████████████████████████████

  

  

请按回车键（RETURN）继续安装，按其他任意按键取消安装

**==>** **/usr/bin/sudo /usr/bin/install -d -o root -g wheel -m 0755 /opt/homebrew**

**==>** **/usr/bin/sudo /bin/mkdir -p /opt/homebrew/bin /opt/homebrew/etc /opt/homebrew/include /opt/homebrew/lib /opt/homebrew/sbin /opt/homebrew/share /opt/homebrew/var /opt/homebrew/opt /opt/homebrew/share/zsh /opt/homebrew/share/zsh/site-functions /opt/homebrew/var/homebrew /opt/homebrew/var/homebrew/linked /opt/homebrew/Cellar /opt/homebrew/Caskroom /opt/homebrew/Frameworks**

**==>** **/usr/bin/sudo /bin/chmod ug=rwx /opt/homebrew/bin /opt/homebrew/etc /opt/homebrew/include /opt/homebrew/lib /opt/homebrew/sbin /opt/homebrew/share /opt/homebrew/var /opt/homebrew/opt /opt/homebrew/share/zsh /opt/homebrew/share/zsh/site-functions /opt/homebrew/var/homebrew /opt/homebrew/var/homebrew/linked /opt/homebrew/Cellar /opt/homebrew/Caskroom /opt/homebrew/Frameworks**

**==>** **/usr/bin/sudo /bin/chmod go-w /opt/homebrew/share/zsh /opt/homebrew/share/zsh/site-functions**

**==>** **/usr/bin/sudo /usr/sbin/chown ksia /opt/homebrew/bin /opt/homebrew/etc /opt/homebrew/include /opt/homebrew/lib /opt/homebrew/sbin /opt/homebrew/share /opt/homebrew/var /opt/homebrew/opt /opt/homebrew/share/zsh /opt/homebrew/share/zsh/site-functions /opt/homebrew/var/homebrew /opt/homebrew/var/homebrew/linked /opt/homebrew/Cellar /opt/homebrew/Caskroom /opt/homebrew/Frameworks**

**==>** **/usr/bin/sudo /usr/bin/chgrp admin /opt/homebrew/bin /opt/homebrew/etc /opt/homebrew/include /opt/homebrew/lib /opt/homebrew/sbin /opt/homebrew/share /opt/homebrew/var /opt/homebrew/opt /opt/homebrew/share/zsh /opt/homebrew/share/zsh/site-functions /opt/homebrew/var/homebrew /opt/homebrew/var/homebrew/linked /opt/homebrew/Cellar /opt/homebrew/Caskroom /opt/homebrew/Frameworks**

**==>** **/usr/bin/sudo /usr/sbin/chown -R ksia:admin /opt/homebrew**

**==>** **/usr/bin/sudo /bin/mkdir -p /Users/ksia/Library/Caches/Homebrew**

**==>** **/usr/bin/sudo /bin/chmod g+rwx /Users/ksia/Library/Caches/Homebrew**

**==>** **/usr/bin/sudo /usr/sbin/chown -R ksia /Users/ksia/Library/Caches/Homebrew**

**==>** **Downloading and installing Homebrew...**

remote: Enumerating objects: 7257, done.

remote: Counting objects: 100% (7257/7257), done.

remote: Compressing objects: 100% (168/168), done.

remote: Total 244511 (delta 7130), reused 7133 (delta 7089), pack-reused 237254

Receiving objects: 100% (244511/244511), 67.22 MiB | 8.36 MiB/s, done.

Resolving deltas: 100% (180648/180648), done.

From https://mirrors.ustc.edu.cn/brew

 * [new branch]          master     -> origin/master

 * [new tag]             0.1        -> 0.1

 * [new tag]             0.2        -> 0.2

 * [new tag]             0.3        -> 0.3

 * [new tag]             0.4        -> 0.4

 * [new tag]             0.5        -> 0.5

 * [new tag]             0.6        -> 0.6

 * [new tag]             0.7        -> 0.7

 * [new tag]             0.7.1      -> 0.7.1

 * [new tag]             0.8        -> 0.8

 * [new tag]             0.8.1      -> 0.8.1

 * [new tag]             0.9        -> 0.9

 * [new tag]             0.9.1      -> 0.9.1

 * [new tag]             0.9.2      -> 0.9.2

 * [new tag]             0.9.3      -> 0.9.3

 * [new tag]             0.9.4      -> 0.9.4

 * [new tag]             0.9.5      -> 0.9.5

 * [new tag]             0.9.8      -> 0.9.8

 * [new tag]             0.9.9      -> 0.9.9

 * [new tag]             1.0.0      -> 1.0.0

 * [new tag]             1.0.1      -> 1.0.1

 * [new tag]             1.0.2      -> 1.0.2

 * [new tag]             1.0.3      -> 1.0.3

 * [new tag]             1.0.4      -> 1.0.4

 * [new tag]             1.0.5      -> 1.0.5

 * [new tag]             1.0.6      -> 1.0.6

 * [new tag]             1.0.7      -> 1.0.7

 * [new tag]             1.0.8      -> 1.0.8

 * [new tag]             1.0.9      -> 1.0.9

 * [new tag]             1.1.0      -> 1.1.0

 * [new tag]             1.1.1      -> 1.1.1

 * [new tag]             1.1.10     -> 1.1.10

 * [new tag]             1.1.11     -> 1.1.11

 * [new tag]             1.1.12     -> 1.1.12

 * [new tag]             1.1.13     -> 1.1.13

 * [new tag]             1.1.2      -> 1.1.2

 * [new tag]             1.1.3      -> 1.1.3

 * [new tag]             1.1.4      -> 1.1.4

 * [new tag]             1.1.5      -> 1.1.5

 * [new tag]             1.1.6      -> 1.1.6

 * [new tag]             1.1.7      -> 1.1.7

 * [new tag]             1.1.8      -> 1.1.8

 * [new tag]             1.1.9      -> 1.1.9

 * [new tag]             1.2.0      -> 1.2.0

 * [new tag]             1.2.1      -> 1.2.1

 * [new tag]             1.2.2      -> 1.2.2

 * [new tag]             1.2.3      -> 1.2.3

 * [new tag]             1.2.4      -> 1.2.4

 * [new tag]             1.2.5      -> 1.2.5

 * [new tag]             1.2.6      -> 1.2.6

 * [new tag]             1.3.0      -> 1.3.0

 * [new tag]             1.3.1      -> 1.3.1

 * [new tag]             1.3.2      -> 1.3.2

 * [new tag]             1.3.3      -> 1.3.3

 * [new tag]             1.3.4      -> 1.3.4

 * [new tag]             1.3.5      -> 1.3.5

 * [new tag]             1.3.6      -> 1.3.6

 * [new tag]             1.3.7      -> 1.3.7

 * [new tag]             1.3.8      -> 1.3.8

 * [new tag]             1.3.9      -> 1.3.9

 * [new tag]             1.4.0      -> 1.4.0

 * [new tag]             1.4.1      -> 1.4.1

 * [new tag]             1.4.2      -> 1.4.2

 * [new tag]             1.4.3      -> 1.4.3

 * [new tag]             1.5.0      -> 1.5.0

 * [new tag]             1.5.1      -> 1.5.1

 * [new tag]             1.5.10     -> 1.5.10

 * [new tag]             1.5.11     -> 1.5.11

 * [new tag]             1.5.12     -> 1.5.12

 * [new tag]             1.5.13     -> 1.5.13

 * [new tag]             1.5.14     -> 1.5.14

 * [new tag]             1.5.2      -> 1.5.2

 * [new tag]             1.5.3      -> 1.5.3

 * [new tag]             1.5.4      -> 1.5.4

 * [new tag]             1.5.5      -> 1.5.5

 * [new tag]             1.5.6      -> 1.5.6

 * [new tag]             1.5.7      -> 1.5.7

 * [new tag]             1.5.8      -> 1.5.8

 * [new tag]             1.5.9      -> 1.5.9

 * [new tag]             1.6.0      -> 1.6.0

 * [new tag]             1.6.1      -> 1.6.1

 * [new tag]             1.6.10     -> 1.6.10

 * [new tag]             1.6.11     -> 1.6.11

 * [new tag]             1.6.12     -> 1.6.12

 * [new tag]             1.6.13     -> 1.6.13

 * [new tag]             1.6.14     -> 1.6.14

 * [new tag]             1.6.15     -> 1.6.15

 * [new tag]             1.6.16     -> 1.6.16

 * [new tag]             1.6.17     -> 1.6.17

 * [new tag]             1.6.2      -> 1.6.2

 * [new tag]             1.6.3      -> 1.6.3

 * [new tag]             1.6.4      -> 1.6.4

 * [new tag]             1.6.5      -> 1.6.5

 * [new tag]             1.6.6      -> 1.6.6

 * [new tag]             1.6.7      -> 1.6.7

 * [new tag]             1.6.8      -> 1.6.8

 * [new tag]             1.6.9      -> 1.6.9

 * [new tag]             1.7.0      -> 1.7.0

 * [new tag]             1.7.1      -> 1.7.1

 * [new tag]             1.7.2      -> 1.7.2

 * [new tag]             1.7.3      -> 1.7.3

 * [new tag]             1.7.4      -> 1.7.4

 * [new tag]             1.7.5      -> 1.7.5

 * [new tag]             1.7.6      -> 1.7.6

 * [new tag]             1.7.7      -> 1.7.7

 * [new tag]             1.8.0      -> 1.8.0

 * [new tag]             1.8.1      -> 1.8.1

 * [new tag]             1.8.2      -> 1.8.2

 * [new tag]             1.8.3      -> 1.8.3

 * [new tag]             1.8.4      -> 1.8.4

 * [new tag]             1.8.5      -> 1.8.5

 * [new tag]             1.8.6      -> 1.8.6

 * [new tag]             1.9.0      -> 1.9.0

 * [new tag]             1.9.1      -> 1.9.1

 * [new tag]             1.9.2      -> 1.9.2

 * [new tag]             1.9.3      -> 1.9.3

 * [new tag]             2.0.0      -> 2.0.0

 * [new tag]             2.0.1      -> 2.0.1

 * [new tag]             2.0.2      -> 2.0.2

 * [new tag]             2.0.3      -> 2.0.3

 * [new tag]             2.0.4      -> 2.0.4

 * [new tag]             2.0.5      -> 2.0.5

 * [new tag]             2.0.6      -> 2.0.6

 * [new tag]             2.1.0      -> 2.1.0

 * [new tag]             2.1.1      -> 2.1.1

 * [new tag]             2.1.10     -> 2.1.10

 * [new tag]             2.1.11     -> 2.1.11

 * [new tag]             2.1.12     -> 2.1.12

 * [new tag]             2.1.13     -> 2.1.13

 * [new tag]             2.1.14     -> 2.1.14

 * [new tag]             2.1.15     -> 2.1.15

 * [new tag]             2.1.16     -> 2.1.16

 * [new tag]             2.1.2      -> 2.1.2

 * [new tag]             2.1.3      -> 2.1.3

 * [new tag]             2.1.4      -> 2.1.4

 * [new tag]             2.1.5      -> 2.1.5

 * [new tag]             2.1.6      -> 2.1.6

 * [new tag]             2.1.7      -> 2.1.7

 * [new tag]             2.1.8      -> 2.1.8

 * [new tag]             2.1.9      -> 2.1.9

 * [new tag]             2.2.0      -> 2.2.0

 * [new tag]             2.2.1      -> 2.2.1

 * [new tag]             2.2.10     -> 2.2.10

 * [new tag]             2.2.11     -> 2.2.11

 * [new tag]             2.2.12     -> 2.2.12

 * [new tag]             2.2.13     -> 2.2.13

 * [new tag]             2.2.14     -> 2.2.14

 * [new tag]             2.2.15     -> 2.2.15

 * [new tag]             2.2.16     -> 2.2.16

 * [new tag]             2.2.17     -> 2.2.17

 * [new tag]             2.2.2      -> 2.2.2

 * [new tag]             2.2.3      -> 2.2.3

 * [new tag]             2.2.4      -> 2.2.4

 * [new tag]             2.2.5      -> 2.2.5

 * [new tag]             2.2.6      -> 2.2.6

 * [new tag]             2.2.7      -> 2.2.7

 * [new tag]             2.2.8      -> 2.2.8

 * [new tag]             2.2.9      -> 2.2.9

 * [new tag]             2.3.0      -> 2.3.0

 * [new tag]             2.4.0      -> 2.4.0

 * [new tag]             2.4.1      -> 2.4.1

 * [new tag]             2.4.10     -> 2.4.10

 * [new tag]             2.4.11     -> 2.4.11

 * [new tag]             2.4.12     -> 2.4.12

 * [new tag]             2.4.13     -> 2.4.13

 * [new tag]             2.4.14     -> 2.4.14

 * [new tag]             2.4.15     -> 2.4.15

 * [new tag]             2.4.16     -> 2.4.16

 * [new tag]             2.4.2      -> 2.4.2

 * [new tag]             2.4.3      -> 2.4.3

 * [new tag]             2.4.4      -> 2.4.4

 * [new tag]             2.4.5      -> 2.4.5

 * [new tag]             2.4.6      -> 2.4.6

 * [new tag]             2.4.7      -> 2.4.7

 * [new tag]             2.4.8      -> 2.4.8

 * [new tag]             2.4.9      -> 2.4.9

 * [new tag]             2.5.0      -> 2.5.0

 * [new tag]             2.5.1      -> 2.5.1

 * [new tag]             2.5.10     -> 2.5.10

 * [new tag]             2.5.11     -> 2.5.11

 * [new tag]             2.5.12     -> 2.5.12

 * [new tag]             2.5.2      -> 2.5.2

 * [new tag]             2.5.3      -> 2.5.3

 * [new tag]             2.5.4      -> 2.5.4

 * [new tag]             2.5.5      -> 2.5.5

 * [new tag]             2.5.6      -> 2.5.6

 * [new tag]             2.5.7      -> 2.5.7

 * [new tag]             2.5.8      -> 2.5.8

 * [new tag]             2.5.9      -> 2.5.9

 * [new tag]             2.6.0      -> 2.6.0

 * [new tag]             2.6.1      -> 2.6.1

 * [new tag]             2.6.2      -> 2.6.2

 * [new tag]             2.7.0      -> 2.7.0

 * [new tag]             2.7.1      -> 2.7.1

 * [new tag]             2.7.2      -> 2.7.2

 * [new tag]             2.7.3      -> 2.7.3

 * [new tag]             2.7.4      -> 2.7.4

 * [new tag]             2.7.5      -> 2.7.5

 * [new tag]             2.7.6      -> 2.7.6

 * [new tag]             2.7.7      -> 2.7.7

 * [new tag]             3.0.0      -> 3.0.0

 * [new tag]             3.0.1      -> 3.0.1

 * [new tag]             3.0.10     -> 3.0.10

 * [new tag]             3.0.11     -> 3.0.11

 * [new tag]             3.0.2      -> 3.0.2

 * [new tag]             3.0.3      -> 3.0.3

 * [new tag]             3.0.4      -> 3.0.4

 * [new tag]             3.0.5      -> 3.0.5

 * [new tag]             3.0.6      -> 3.0.6

 * [new tag]             3.0.7      -> 3.0.7

 * [new tag]             3.0.8      -> 3.0.8

 * [new tag]             3.0.9      -> 3.0.9

 * [new tag]             3.1.0      -> 3.1.0

 * [new tag]             3.1.1      -> 3.1.1

 * [new tag]             3.1.10     -> 3.1.10

 * [new tag]             3.1.11     -> 3.1.11

 * [new tag]             3.1.12     -> 3.1.12

 * [new tag]             3.1.2      -> 3.1.2

 * [new tag]             3.1.3      -> 3.1.3

 * [new tag]             3.1.4      -> 3.1.4

 * [new tag]             3.1.5      -> 3.1.5

 * [new tag]             3.1.6      -> 3.1.6

 * [new tag]             3.1.7      -> 3.1.7

 * [new tag]             3.1.8      -> 3.1.8

 * [new tag]             3.1.9      -> 3.1.9

 * [new tag]             3.2.0      -> 3.2.0

 * [new tag]             3.2.1      -> 3.2.1

 * [new tag]             3.2.10     -> 3.2.10

 * [new tag]             3.2.11     -> 3.2.11

 * [new tag]             3.2.12     -> 3.2.12

 * [new tag]             3.2.13     -> 3.2.13

 * [new tag]             3.2.14     -> 3.2.14

 * [new tag]             3.2.15     -> 3.2.15

 * [new tag]             3.2.16     -> 3.2.16

 * [new tag]             3.2.17     -> 3.2.17

 * [new tag]             3.2.2      -> 3.2.2

 * [new tag]             3.2.3      -> 3.2.3

 * [new tag]             3.2.4      -> 3.2.4

 * [new tag]             3.2.5      -> 3.2.5

 * [new tag]             3.2.6      -> 3.2.6

 * [new tag]             3.2.7      -> 3.2.7

 * [new tag]             3.2.8      -> 3.2.8

 * [new tag]             3.2.9      -> 3.2.9

 * [new tag]             3.3.0      -> 3.3.0

 * [new tag]             3.3.1      -> 3.3.1

 * [new tag]             3.3.10     -> 3.3.10

 * [new tag]             3.3.11     -> 3.3.11

 * [new tag]             3.3.12     -> 3.3.12

 * [new tag]             3.3.13     -> 3.3.13

 * [new tag]             3.3.14     -> 3.3.14

 * [new tag]             3.3.15     -> 3.3.15

 * [new tag]             3.3.16     -> 3.3.16

 * [new tag]             3.3.2      -> 3.3.2

 * [new tag]             3.3.3      -> 3.3.3

 * [new tag]             3.3.4      -> 3.3.4

 * [new tag]             3.3.5      -> 3.3.5

 * [new tag]             3.3.6      -> 3.3.6

 * [new tag]             3.3.7      -> 3.3.7

 * [new tag]             3.3.8      -> 3.3.8

 * [new tag]             3.3.9      -> 3.3.9

 * [new tag]             3.4.0      -> 3.4.0

 * [new tag]             3.4.1      -> 3.4.1

 * [new tag]             3.4.10     -> 3.4.10

 * [new tag]             3.4.11     -> 3.4.11

 * [new tag]             3.4.2      -> 3.4.2

 * [new tag]             3.4.3      -> 3.4.3

 * [new tag]             3.4.4      -> 3.4.4

 * [new tag]             3.4.5      -> 3.4.5

 * [new tag]             3.4.6      -> 3.4.6

 * [new tag]             3.4.7      -> 3.4.7

 * [new tag]             3.4.8      -> 3.4.8

 * [new tag]             3.4.9      -> 3.4.9

 * [new tag]             3.5.0      -> 3.5.0

 * [new tag]             3.5.1      -> 3.5.1

 * [new tag]             3.5.10     -> 3.5.10

 * [new tag]             3.5.2      -> 3.5.2

 * [new tag]             3.5.3      -> 3.5.3

 * [new tag]             3.5.4      -> 3.5.4

 * [new tag]             3.5.5      -> 3.5.5

 * [new tag]             3.5.6      -> 3.5.6

 * [new tag]             3.5.7      -> 3.5.7

 * [new tag]             3.5.8      -> 3.5.8

 * [new tag]             3.5.9      -> 3.5.9

 * [new tag]             3.6.0      -> 3.6.0

 * [new tag]             3.6.1      -> 3.6.1

 * [new tag]             3.6.10     -> 3.6.10

 * [new tag]             3.6.11     -> 3.6.11

 * [new tag]             3.6.12     -> 3.6.12

 * [new tag]             3.6.13     -> 3.6.13

 * [new tag]             3.6.14     -> 3.6.14

 * [new tag]             3.6.15     -> 3.6.15

 * [new tag]             3.6.16     -> 3.6.16

 * [new tag]             3.6.17     -> 3.6.17

 * [new tag]             3.6.18     -> 3.6.18

 * [new tag]             3.6.19     -> 3.6.19

 * [new tag]             3.6.2      -> 3.6.2

 * [new tag]             3.6.20     -> 3.6.20

 * [new tag]             3.6.21     -> 3.6.21

 * [new tag]             3.6.3      -> 3.6.3

 * [new tag]             3.6.4      -> 3.6.4

 * [new tag]             3.6.5      -> 3.6.5

 * [new tag]             3.6.6      -> 3.6.6

 * [new tag]             3.6.7      -> 3.6.7

 * [new tag]             3.6.8      -> 3.6.8

 * [new tag]             3.6.9      -> 3.6.9

 * [new tag]             4.0.0      -> 4.0.0

 * [new tag]             4.0.1      -> 4.0.1

 * [new tag]             4.0.10     -> 4.0.10

 * [new tag]             4.0.11     -> 4.0.11

 * [new tag]             4.0.12     -> 4.0.12

 * [new tag]             4.0.13     -> 4.0.13

 * [new tag]             4.0.14     -> 4.0.14

 * [new tag]             4.0.15     -> 4.0.15

 * [new tag]             4.0.16     -> 4.0.16

 * [new tag]             4.0.17     -> 4.0.17

 * [new tag]             4.0.18     -> 4.0.18

 * [new tag]             4.0.19     -> 4.0.19

 * [new tag]             4.0.2      -> 4.0.2

 * [new tag]             4.0.20     -> 4.0.20

 * [new tag]             4.0.21     -> 4.0.21

 * [new tag]             4.0.22     -> 4.0.22

 * [new tag]             4.0.23     -> 4.0.23

 * [new tag]             4.0.24     -> 4.0.24

 * [new tag]             4.0.25     -> 4.0.25

 * [new tag]             4.0.26     -> 4.0.26

 * [new tag]             4.0.27     -> 4.0.27

 * [new tag]             4.0.28     -> 4.0.28

 * [new tag]             4.0.3      -> 4.0.3

 * [new tag]             4.0.4      -> 4.0.4

 * [new tag]             4.0.5      -> 4.0.5

 * [new tag]             4.0.6      -> 4.0.6

 * [new tag]             4.0.7      -> 4.0.7

 * [new tag]             4.0.8      -> 4.0.8

 * [new tag]             4.0.9      -> 4.0.9

 * [new tag]             4.1.0      -> 4.1.0

remote: Enumerating objects: 3567, done.

remote: Counting objects: 100% (3567/3567), done.

remote: Total 7544 (delta 3567), reused 3567 (delta 3567), pack-reused 3977

Receiving objects: 100% (7544/7544), 1.62 MiB | 4.97 MiB/s, done.

Resolving deltas: 100% (5805/5805), completed with 740 local objects.

From https://mirrors.ustc.edu.cn/brew

 * [new tag]             1.1.0.1              -> 1.1.0.1

 * [new tag]             1.1.2.1              -> 1.1.2.1

 * [new tag]             1.2.7                -> 1.2.7

 * [new tag]             1.2.8                -> 1.2.8

 * [new tag]             4.0.29               -> 4.0.29

 * [new tag]             backup/activesupport-23-38-09 -> backup/activesupport-23-38-09

 * [new tag]             backup/brew-cask-style-14-54-55 -> backup/brew-cask-style-14-54-55

 * [new tag]             backup/create-cache-00-29-47 -> backup/create-cache-00-29-47

 * [new tag]             backup/days-03-02-52 -> backup/days-03-02-52

 * [new tag]             backup/days-03-02-59 -> backup/days-03-02-59

 * [new tag]             backup/days-19-30-23 -> backup/days-19-30-23

 * [new tag]             backup/gpg-verification-01-53-16 -> backup/gpg-verification-01-53-16

 * [new tag]             backup/remove-popen-read-19-56-50 -> backup/remove-popen-read-19-56-50

 * [new tag]             backup/remove-popen-read-20-00-21 -> backup/remove-popen-read-20-00-21

HEAD is now at aa74840dc Merge pull request #15729 from dduugg/inreplace-sig

**==>** **Tapping homebrew/services**

remote: Enumerating objects: 2404, done.

remote: Counting objects: 100% (17/17), done.

remote: Compressing objects: 100% (14/14), done.

remote: Total 2404 (delta 5), reused 13 (delta 2), pack-reused 2387

Receiving objects: 100% (2404/2404), 668.35 KiB | 508.00 KiB/s, done.

Resolving deltas: 100% (1082/1082), done.

From https://gitee.com/imirror/homebrew-services

 * [new branch]      master     -> origin/master

HEAD is now at ef8e026 Merge pull request #563 from Homebrew/services_scope_service

HOMEBREW_BREW_GIT_REMOTE set: using https://mirrors.ustc.edu.cn/brew.git as the Homebrew/brew Git remote.

**==>** **🎉 恭喜，安装成功！**

  

**==>** **Homebrew是由志愿者义务维护的，如果可以请考虑捐赠：**

  https://github.com/Homebrew/brew#donations

  

**==>** **Next steps:**

自动配置环境变量

**执行成功**

  

**Warning**: 重要信息!!!

如果遇到 **command not found brew**，请执行下面脚本完成安装或者直接重新打开终端:

**eval "$(/opt/homebrew/bin/brew shellenv)"**

  

**- 运行** **brew help** 开始体验吧

- 教程文档:

    https://brew.idayer.com

  

**==>** **维护加速脚本以及解答问题是很费时费力的工作，如果有幸帮助到你，可以考虑请我喝杯咖啡，或者给项目点个赞。**

  ☕ 喝咖啡：https://brew.idayer.com/reward/

  🌟 点赞：https://github.com/ineo6/homebrew-install

  🌟 点赞：https://gitee.com/ineo6/homebrew-install



```
