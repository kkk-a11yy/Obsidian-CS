	[[微服务-pom.xml]]
	[andymall-pom.xml](andymall-pom.xml.md)
	修改完之后maven reload一下，运行clean命令
	 
- 修改andymall聚合模块下的`.gitignore`文件，加入：
	- ** 意思是任意路径下的这个文件
	```r
	**/mvnw  
	**/mvnw.cmd
	**/.mvn
	**/target
	.idea
	**/.gitignore
	
	注意有运行maven `compile`命令后每个项目下生成的`target`文件夹
	```
	- version control 的 local changes 里面文件未改动的：terminal里输入 `git rm -r -f --cached .`  （注意有个点）命令，清除缓存区内容![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230813212536.png)
	- 文件纳入版本控制：add to vcs ![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230815154451.png)
# 把代码提交给github (本人是这个)或者 gitee
- 1.项目提交到本地仓库并推送到github：commit &push![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230815161059.png)
