###github常见操作和常见错误！错误提示：fatal: remote origin already exists.

    如果输入$ git remote add origin git@github.com:djqiang（github帐号名）/gitdemo（项目名）.git 

    提示出错信息：fatal: remote origin already exists.

    解决办法如下：

    1、先输入$ 
    git remote rm origin

    2、再输入$ git remote add origin git@github.com:djqiang/gitdemo.git 就不会报错了！

    3、如果输入$ git remote rm origin 还是报错的话，error: Could not remove config section 'remote.origin'. 我们需要修改gitconfig文件的内容

    4、找到你的github的安装路径，我的是C:\Users\ASUS\AppData\Local\GitHub\PortableGit_ca477551eeb4aea0e4ae9fcd3358bd96720bb5c8\etc

    5、找到一个名为gitconfig的文件，打开它把里面的[remote "origin"]那一行删掉就好了！

 

 

    如果输入$ ssh -T git@github.com
    出现错误提示：Permission denied (publickey).因为新生成的key不能加入ssh就会导致连接不上github。

    解决办法如下：

    1、先输入$ ssh-agent，再输入$ ssh-add ~/.ssh/id_key，这样就可以了。

    2、如果还是不行的话，输入ssh-add ~/.ssh/id_key 命令后出现报错Could not open a connection to your authentication agent.解决方法是key用Git Gui的ssh工具生成，这样生成的时候key就直接保存在ssh中了，不需要再ssh-add命令加入了，其它的user，token等配置都用命令行来做。

    3、最好检查一下在你复制id_rsa.pub文件的内容时有没有产生多余的空格或空行，有些编辑器会帮你添加这些的。

 

 

    如果输入$ git push origin master

    提示出错信息：error:failed to push som refs to .......

    解决办法如下：

    1、先输入$ git pull origin master //先把远程服务器github上面的文件拉下来

    2、再输入$ git push origin master

    3、如果出现报错 fatal: Couldn't find remote ref master或者fatal: 'origin' does not appear to be a git repository以及fatal: Could not read from remote repository.

    4、则需要重新输入$ git remote add origin git@github.com:djqiang/gitdemo.git

 

 

    使用git在本地创建一个项目的过程

    $ makdir ~/hello-world    //创建一个项目hello-world
    $ cd ~/hello-world       //打开这个项目
    $ git init             //初始化 
    $ touch README
    $ git add README        //更新README文件
    $ git commit -m 'first commit'     //提交更新，并注释信息“first commit” 
    $ git remote add origin git@github.com:defnngj/hello-world.git     //连接远程github项目  
    $ git push -u origin master     //将本地项目更新到github项目上去

 

   

    gitconfig配置文件

         Git有一个工具被称为git config，它允许你获得和设置配置变量；这些变量可以控制Git的外观和操作的各个方面。这些变量可以被存储在三个不同的位置： 
         1./etc/gitconfig 文件：包含了适用于系统所有用户和所有库的值。如果你传递参数选项’--system’ 给 git config，它将明确的读和写这个文件。 
         2.~/.gitconfig 文件 ：具体到你的用户。你可以通过传递--global 选项使Git 读或写这个特定的文件。
         3.位于git目录的config文件 (也就是 .git/config) ：无论你当前在用的库是什么，特定指向该单一的库。每个级别重写前一个级别的值。因此，在.git/config中的值覆盖了在/etc/gitconfig中的同一个值。
        在Windows系统中，Git在$HOME目录中查找.gitconfig文件（对大多数人来说，位于C:\Documents and Settings\$USER下）。它也会查找/etc/gitconfig，尽管它是相对于Msys 根目录的。这可能是你在Windows中运行安装程序时决定安装Git的任何地方。

 

        配置相关信息：

        2.1　当你安装Git后首先要做的事情是设置你的用户名称和e-mail地址。这是非常重要的，因为每次Git提交都会使用该信息。它被永远的嵌入到了你的提交中：

　　$ git config --global user.name "John Doe"

　　$ git config --global user.email johndoe@example.com

 

       2.2    你的编辑器(Your Editor)

　　现在，你的标识已经设置，你可以配置你的缺省文本编辑器，Git在需要你输入一些消息时会使用该文本编辑器。缺省情况下，Git使用你的系统的缺省编辑器，这通常可能是vi 或者 vim。如果你想使用一个不同的文本编辑器，例如Emacs，你可以做如下操作：

　　$ git config --global core.editor emacs

 

      2.3 检查你的设置(Checking Your Settings)

　　如果你想检查你的设置，你可以使用 git config --list 命令来列出Git可以在该处找到的所有的设置:

　　$ git config --list

      你也可以查看Git认为的一个特定的关键字目前的值，使用如下命令 git config {key}:

　　$ git config user.name

 

      2.4 获取帮助(Getting help)

　　如果当你在使用Git时需要帮助，有三种方法可以获得任何git命令的手册页(manpage)帮助信息:

　　$ git help <verb>

　　$ git <verb> --help

　　$ man git-<verb>

　　例如，你可以运行如下命令获取对config命令的手册页帮助:

　　$ git help config

### git常用指令

git的常用命令
创建仓库
git init
提交的文件的信息添加到索引库中
git add [file]
git add . #'.'或'*'表示全部添加
提交git 默认分支master
git commit [flie] -m [message]
git commit [flie] -a -m [message]
查看提交记录
git log
查看git状态
git status
向远程库提交分支master，也可以提交dev
git push origin master
git push -u origin master
克隆远程仓库到本地库
git clone [url]
增加远程仓库并命名,name 默认是origin
git remote add [name] [url]
git remote add origin [url]
将本地的提交推送到远程仓库
git push [url]
关联远程库，名字origin
git remote add origin [url]
查看远程库信息
git remote -v
将远程仓库下载到本地
git pull [url]

#Git  hub命令符的正确于都方式  
##命令符合集  
###上传项目时需要用到的命令符  
1.git config --global user.email "里面填写邮箱"  
2.git config --global user.name "里面填写用户姓名名称"  
3.初始化当前目录，变成一个git仓库：git init  
4.将本地文件添加到本地仓库中：git add .  
5.将本地文件提交到分支区中：git commit -m "自定义一个文字或单词"  
6.添加远程库，并在远程库中克隆：git remote add origin 填写远程库的链接  
7.将本地的master分支推送到origin主机，同时指定origin为默认主机：git push origin master  
  


###一些常用的命令符  
1：版本查询：git --version  
2：显示当前用户信息：git config --list  
3：显示git常用指令：git  
4：查询仓库状态：git status  
5：生成“后悔药”：git commit -m "xxx"  
6：“后悔药”查询：  
基本查询//git log  
详细查询，包括修改对比//git log -p  
以精简模式显示//git log --oneline  
查看“后悔树”//git log --graph  
7：吃“后悔药”版本回退：  
xxx代表编号或标记，可用git log查询//git checkout xxx  
 回退到最近的版本//git checkout -  
8：标记：git tag  
9：xx代表标记，xxx代表注释：git tag -a xx -m "xxx"  
10：显示标记：git show xx  
11：提交所有更新过的文件：git commit -m "commit message"  
12：修改最后一次提交：git commit --amend  
13：文件改名：git mv <oldname> <newname>  
14：删除远程库： git remote rm origin
15：手动删除远程库：vi .git/config

