---
tags: WSL
links: 
- "[[WSL 的基本命令 | Microsoft Learn](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands)]]"
- "[旧版 WSL 的手动安装步骤 | Microsoft Learn](https://learn.microsoft.com/zh-cn/windows/wsl/install-manual#downloading-distributions)"
resources:
---
```
PS C:\Users\KKK\Desktop> wsl --set-version Ubuntu 2

PS C:\Users\KKK\Desktop> wsl --set-default-version 2

PS C:\Users\KKK\Desktop> wsl --list --verbose
  NAME      STATE           VERSION
* Ubuntu    Stopped         2
```