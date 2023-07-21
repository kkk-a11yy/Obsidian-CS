-   #3  Add init & command ![](lecture-note/Pasted%20image%2020230503222847.png)
     
     -  测试yml文件里新加的这两个命令，Create PuLL request:  Add Gitpod Configuration    close #3 ，勾选 as draft![](lecture-note/Pasted%20image%2020230504140612.png)
     - 然后#3 下面就有了个#5 ，因为自己之前创建的#4 给close了，这里没显示![](lecture-note/Pasted%20image%2020230504140921.png)
         - 打开#5，开一个新的gitpod  ![](lecture-note/Pasted%20image%2020230504141223.png)
           -  在 .gitpod.yml 文件添加 port 配置   ；  添加 commit : Configure port 5173 behavior.  ![](lecture-note/Pasted%20image%2020230504141813.png)
             - 对port 配置同步： syn changes  ![](lecture-note/Pasted%20image%2020230504142021.png)
               -  查看 并新开一个gitpod ![](lecture-note/Pasted%20image%2020230504142137.png)
               - 这里可能遇到端口占用问题导致open-browser 受阻打不开，参考[错误](安装配置/clash%20for%20win/错误.md#^0b9c96)
               - check 这个配置正确启动之后，关闭旧的gitpod，在这个新的gitpod上继续
               - 命令行 `ctrl+c`
        - 修改 `svelte.config.js`    `gp url`    /  `gp 5173 url`  ![](lecture-note/Pasted%20image%2020230504172515.png)
    - 修改 `.gitpod.yml`   
        -  ``` command: export HMR HOST=`gp url 5173` && npm run dev```
        - ![](lecture-note/Pasted%20image%2020230504175407.png)
     - 修改svelte.config.js  截取`https://` 之后的地址
        -   ```hmr:{
                    clientPort: process.env.HMR_HOST ? 443 : 5173,
                    host: process.env.HMR_HOST ? process.env.HMR_HOST.substring("https://".length) : "locallhost"
                }```
          - ![](lecture-note/Pasted%20image%2020230504175135.png)
          - 提交这些修改： ![](lecture-note/Pasted%20image%2020230504175540.png)
          - syn ![](lecture-note/Pasted%20image%2020230504212947.png)
         