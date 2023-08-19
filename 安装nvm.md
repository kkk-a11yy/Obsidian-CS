# 参考资料
- [nvm-sh/nvm: Node Version Manager ](https://github.com/nvm-sh/nvm)
- [MAC nvm安装失败,正确安装步骤 - 掘金](https://juejin.cn/post/7075600154635534344)
- [Mac M1 Pro下载node.js_mac 下载node_Rookie_聪的博客-CSDN博客](https://blog.csdn.net/weixin_46678290/article/details/128508766?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0-128508766-blog-131663483.235%5Ev38%5Epc_relevant_default_base&spm=1001.2101.3001.4242.1&utm_relevant_index=3)
#  命令
```r
//下载
git clone https://gitee.com/mirrors/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`

//安装
~/.nvm/install.sh

```


```r
vim ~/.zshrc

// insert 模式添加：
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

//`esc`键，输入`:wq`保存退出
//进行配置更新
source ~/.zshrc

```

```r
nvm -v
	0.39.4
```

# **nvm 常用命令：**

- nvm -h 获得帮助
- nvm ls-remote 列出所有可安装的node版本
- nvm install 安装指定版本node
- nvm list 查看本地已安装的node版本，同时也会显示当前使用的node版本
- nvm current 显示当前版本
- nvm use 切换使用指定的版本node