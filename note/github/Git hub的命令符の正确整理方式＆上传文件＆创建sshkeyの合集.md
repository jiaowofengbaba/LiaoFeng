# Git  hub命令符的正确于都方式     
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