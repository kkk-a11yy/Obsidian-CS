- [MAC nvm安装失败,正确安装步骤 - 掘金](https://juejin.cn/post/7075600154635534344)
- [Mac M1 Pro下载node.js_mac 下载node_Rookie_聪的博客-CSDN博客](https://blog.csdn.net/weixin_46678290/article/details/128508766?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0-128508766-blog-131663483.235%5Ev38%5Epc_relevant_default_base&spm=1001.2101.3001.4242.1&utm_relevant_index=3)
- 命令
```r
ksia@bogon ~ % git clone https://gitee.com/mirrors/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`

//安装
ksia@bogon ~ % ~/.nvm/install.sh

```


```r
ksia@bogon ~ % vim ~/.zshrc

// insert 模式添加：
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

//`esc`键，输入`:wq`保存退出
//进行配置更新
source ~/.zshrc

```

```r
ksia@bogon ~ % nvm -v
0.39.4
```