---
layout: post
title: Git在ubuntu的安装以及常用命令
category: 技术
tags: Git
keywords: 
description: 
---

## git在ubuntu的安装
1. sudo apt-get install git
2. git config --global user.name "user_name"
3. git config --global user.email "email_id"
5. ssh-keygen -C 'you_email_address@gmail.com' -t rsa                          # 产生密钥
6. 复制 ~/.ssh/id_rsa.pub 的内容到github官网 https://github.com/settings/keys
7. ssh -v git@github.com                                                       # 测试连接


## git常用命令
###git常用流程
```
$ git clone git@github.com:lyb6537/lyb6537.github.io                   #克隆项目
$ git add -A .                                                         #添加当前目录的所有文件到暂存区
$ git commit -m "commit"                                               #将暂存区更新到实际目录中
$ git pull                                                             #更新本地仓库
$ git push                                                             #推送到服务器仓库
```

###创建版本库
```
$ git clone <url>     #克隆远程版本库
$ git init            #初始化本地版本库
```

###修改和提交
```
$ git status                        #查看状态
$ git diff                          #查看变更内容
$ git add .                         #跟踪所有改动过的文件
$ git add <file>                    #跟踪指定的文件
$ git mv <old><new>                 #文件改名
$ git rm<file>                      #删除文件
$ git rm --cached<file>             #停止跟踪文件但不删除
$ git commit -m "commit messages"   #提交所有更新过的文件
$ git commit --amend                #修改最后一次改动
```

###查看提交历史
```
$ git log                            #查看提交历史
$ git log -p <file>                  #查看指定文件的提交历史
$ git blame <file>                   #以列表方式查看指定文件的提交历史
```

###撤销
```
$ git reset --hard HEAD              #撤销工作目录中所有未提交文件的修改内容
$ git checkout HEAD <file>           #撤销指定的未提交文件的修改内容
$ git revert <commit>                #撤销指定的提交
$ git log --before="1 days"          #退回到之前1天的版本 
```

###分支与标签

```
$ git branch                         #显示所有本地分支
$ git checkout <branch/tag>          #切换到指定分支和标签
$ git branch <new-branch>            #创建新分支
$ git branch -d <branch>             #删除本地分支
$ git tag                            #列出所有本地标签
$ git tag <tagname>                  #基于最新提交创建标签
$ git tag -d <tagname>               #删除标签
```

###合并与衍合
```
$ git merge <branch>                 #合并指定分支到当前分支
$ git rebase <branch>                #衍合指定分支到当前分支
```

###远程操作
```
$ git remote -v                         #查看远程版本库信息
$ git remote show <remote>              #查看指定远程版本库信息
$ git remote add <remote> <url>         #添加远程版本库
$ git fetch <remote>                    #从远程库获取代码
$ git pull <remote> <branch>            #下载代码及快速合并
$ git push <remote> <branch>            #上传代码及快速合并
$ git push <remote> :<branch/tag-name>  #删除远程分支或标签
$ git push --tags                       #上传所有标签
```




