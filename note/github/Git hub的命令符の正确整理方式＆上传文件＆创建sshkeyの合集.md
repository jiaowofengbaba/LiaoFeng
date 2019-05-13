# Git  hub命令符的正确于都方式   
* * *
> sshkey密钥创建方式
* * *
* cat ~/.ssh/id_rsa.pub “查看本地文件夹是否有.ssh文件”  
+ 如果没有需要用 ssh-keygen -t rsa -C "你的邮箱"  “来生成你的心的密钥”  
* 然后打开.ssh文件夹将文件夹中 id_rsa.pub 文件打开复制里面的密钥  
+ 打开Git hub官网进入你的账号，点击头像右面的三角号，找到settings单击打开  
* 进入以后找到SSH and GPG keys单击进入，然后单击New SSH key进入生成页面  
+ Tile文本框是给密钥设置一个标题，Key文本框是把刚刚复制的密钥粘贴到里面，然后点击Add SSH key创建密钥即可  
* * *
>上传项目时需要用到的命令符 
* * * 
* git config --global user.email "里面填写邮箱"  
+ git config --global user.name "里面填写用户姓名名称"  
* 初始化当前目录，变成一个git仓库：git init  
+ 将本地文件添加到本地仓库中：git add .  
* 将本地文件提交到分支区中：git commit -m "自定义一个文字或单词"  
+ 添加远程库，并在远程库中克隆：git remote add origin 填写远程库的链接  
* 将本地的master分支推送到origin主机，同时指定origin为默认主机：git push origin master  
* * *
# 命令符合集   
> 一些常用的命令符  
* * *
1. 版本查询：git --version  
2. 显示当前用户信息：git config --list  
3. 显示git常用指令：git  
4. 查询仓库状态：git status  
5. 生成“后悔药”：git commit -m "xxx"  
6. “后悔药”查询:  
基本查询//git log  
详细查询，包括修改对比//git log -p  
以精简模式显示//git log --oneline  
查看“后悔树”//git log --graph  
7. 吃“后悔药”版本回退：  
xxx代表编号或标记，可用git log查询//git checkout xxx  
 回退到最近的版本//git checkout -  
8. 标记：git tag  
9. xx代表标记，xxx代表注释：git tag -a xx -m "xxx"  
10. 显示标记：git show xx  
11. 提交所有更新过的文件：git commit -m "commit message"  
12. 修改最后一次提交：git commit --amend  
13. 文件改名：git mv <旧的文件名> <新的文件名>  
14. 删除远程库： git remote rm origin
15. 手动删除远程库：vi .git/config
16. 查看这个文件上次修改具体改了那些内容：git diff readme.txt  
17. 显示最近到最远的提交日志，用于回溯版本：git log  
18. 恢复：commit  
19. 现实对版本库的各种操作记录，用于重返未来：git reflog  
20. 先添加多个文件 之后一起提交  
    git add file1.txt  
    git add file2.txt  
21. 把暂存区的修改回退到工作区（unstage）：git reset HEAD file  
22. 删除版本库的test.txt文件：git rm test.txt  
23. 创建dev分支并切换：git checkout -b dev  
* * *
## 未完待续！！！