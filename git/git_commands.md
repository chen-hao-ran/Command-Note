# Some of basic commands for git
## Common commands
```
#克隆仓库
git clone <address of repo>

#初始化仓库
git init

#关联远程仓库
git remote add <connect name default:origin> <address of repo>

#解绑远程仓库
Unassociate the remote repo : git remote remove <connect name>

#!Associate when origin is not null:
git pull <connect name> <branch name> --allow-unrelated-histories 

#查看远程仓库
git remote -v

#Pull
git pull <connect name> <branch name>

#Push
git push <connect name> <branch name>

#First Push
git push -u <connect name> <branch name>

#提交
git commit -m ""

#Check prior log
git log --pretty=oneline

#Check later log
git reflog --pretty=oneline

#Get specified [id]version
git reset --head id

#查看配置
git config -l
```


## Vpn speed up
* socks5协议，1080端口修改成自己的本地代理端口
```
git config --global http.https://github.com.proxy socks5://127.0.0.1:7890
git config --global https.https://github.com.proxy socks5://127.0.0.1:7890
```

* http协议，1081端口修改成自己的本地代理端口
```
git config --global http.https://github.com.proxy https://127.0.0.1:7890
git config --global https.https://github.com.proxy https://127.0.0.1:7890
```

* Reset proxy
```
git config --global --unset http.proxy
git config --global --unset https.proxy
```

## Git Large Files
```
initialize git lfs: git lfs install
set tracking files: git lfs track "*.zip"I
```



## LF will be replaced by CRLF the next time Git touches it

Issue: 不同OS之间的换行符不同，会出现转换问题

Solution: 

```
# 使 Git 在检出文件时将 LF 转换为 CRLF，并在提交时将 CRLF 转换回 LF
git config --global core.autocrlf true

# 告诉 Git 不要进行任何自动的行结束符转换
git config --global core.autocrlf false
```

