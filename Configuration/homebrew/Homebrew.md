---
tags: homebrew , brew-cask 
link:
- "[中科大镜像源](https://mirrors.ustc.edu.cn/help/brew.git.html)" 
- "https://www.jianshu.90com/p/e0471aa6672d"
- "[homebrew-官方](https://brew.sh/#search-bar/)"
- "[home-brew-github](https://github.com/Homebrew/homebrew-cask)"
- "[macos下java环境搭建](https://bibichuan.github.io/posts/55363e5.html)"
---
- 使用代码：
``` r
//安装中科大镜像
/bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"

//brew can nit found command
eval "$(/opt/homebrew/bin/brew shellenv)"

//安装brew-cask
 brew install brew-cask-completion


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

ksia@bogon ~ % /bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"

**==>** **Checking for `sudo` access (which may request your password)...**

Password:

**==>** **The following new directories will be created:**

/opt/homebrew/bin

...

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
	
	
	From https://mirrors.ustc.edu.cn/brew
	
	 * [new branch]          master     -> origin/master
	
	 * [new tag]             0.1        -> 0.1
	
	...
	
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
- home-brew安装路径：/opt/homebrew/Cellar/