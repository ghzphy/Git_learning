# Git学习笔记
参考: [廖雪峰Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)

- 创建版本库
	
在某个目录下输入 git init 命令可变成git管理的仓库

	git init
	> Initilized empty Git repository in /XXXXX

- 把本地文件添加到版本库

假设本地已有XXX等文件，现在登录github账户，create a new repo，创建一个新的仓库XXX.
根据Github的提示，在本地的XXX仓库下运行命令：

	git remote add origin git@github.com:ghzphy/XXX.git
	git push -u origin master

将本地库内容推送远程，用git push命令.  -u是首次推送使用的，之后只要本地提交后，就可以通过命令:
	git push origin master

- 从远程库克隆

假设此时github上已有完整的仓库XXX，我们可以从远程库克隆，在适当的目录下输入命令

	git clone git@github.com:ghzphy/XXX.git

也可以用https://github.com/ghzphy/XXX.git这样的地址，不过这种速度慢，而且每次推送都必须输入口令。但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。

- 常用命令

	- git status 命令查看仓库当前的状态
	- git diff 命令查看文件的difference: git diff files
	- git add 命令将文件添加到仓库，git add file， git add .
	- git commit 命令把文件提交到仓库，git commit -m "description" 表示本次提交的说明
	- git log 命令显示提交日志，输出简化：'git log --pretty=oneline'
	- git reflog 记录每一次命令。
	- git pull orgin master 获取远程库与本地仓库同步合并
- 文件版本
	
在Git中，用HEAD表示当前版本，上一个版本是HEAD^，上上一个是HEAD^^，依次多一个^。我们将当前版本回退到上一个版本，命令为:

	git reset --hard HEAD^
	git reset --hard 版本号	

- 文件(夹)修改/删除
	- git rm file 删除file文件。
	- git checkout -- file 命令是撤销工作区的修改。
	- git rm -r --cached files

- 大小写

查看git中的大小写敏感

	git config --get core.ignorecase

更改设置
	git config core.ignorecase false