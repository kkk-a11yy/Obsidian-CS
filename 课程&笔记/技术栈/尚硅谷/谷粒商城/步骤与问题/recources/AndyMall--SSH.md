为了以后用客户端给github推送时不用填写用户和密码
# SSH密钥生成
```r
ksia@bogon ~ % ssh-keygen -t rsa -C "ksiafor@gmail.com"

ksia@bogon ~ % cat /Users/ksia/.ssh/andymall.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDHC2WoJmflcD15vAyWeQk9i4dBMjQ/sf9QVgQa3ZZSiTQb9acQoN1gEXPz6JIQjCLxaLk/jFT0Qogp9s+JttvXvqzTZ5yYvtvgGz5OYjomYtN4qaN3UII18abIpRa8+0UI6q5jkXn1PVXAitiD99EC90YuiBKg5DS3Q86zfEetIhqoxAOUFSdtKLXp7hERb4JQ2WqqM/3FVfocomZGopuxBPB9W1P8RM/k6eLbquqJYyMTyinABDIYZpzZdGxkl0iqSkwR8BfIF+NIgcVcepoeAlGh5So3+5T917r/E7HX0z4JHmNoMlDxlylG0Tl5QStIxXMnqqpzjq89IhMsLrR+v9eEy5m/aOnh5XoWsLpETgEWM5HEuQsJ2KONhwbHhK8CRcWbWbkPkgS+m1qWECKCAHZogJ/iYAd6HJk5qvfVdPBuaQpmb6vPQ3o7+MsGpTyDBkMUQm9YnGfzdy/KE8qGBMVIjxWPHwGRiA4uitaV8RlgDqsY9H/ytwmdTu6gIcU= ksiafor@gmail.com
```

![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230812211336.png)
# 测试是否成功
```r
ksia@bogon ~ % ssh -T git@github.com

Hi kkk-a11yy! You've successfully authenticated, but GitHub does not provide shell access.
```
