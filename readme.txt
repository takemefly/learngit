Git is a distributed version control system.
Git is free software distributed under the GPL.

--创建SSH Key
$ ssh-keygen -t rsa -C "13032199255@189.cn"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa):

--在github上添加秘钥

-- 测试连接
ssh -T git@github.com
当你第一次使用Git的clone或者push命令连接GitHub时，会得到一个警告：
The authenticity of host 'github.com (192.30.255.112)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)?  
这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入yes回车即可。
Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：




--将本地仓库推到git远程仓库
git remote add origin git@github.com:takemefly/learngit.git

git push -u origin master --git push命令，实际上是把当前分支master推送到远程。

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，
还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

从现在起，只要本地作了提交，就可以通过命令：

$ git push origin master


从远程库克隆
git clone git@github.com:takemefly/gitskills.git

创建dev分支，然后切换到dev分支：
	git checkout -b dev
git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：
	git branch dev
	git checkout dev
用git branch命令查看当前分支：

dev分支的工作完成，我们就可以切换回master分支：
git checkout master

我们把dev分支的工作成果合并到master分支上：
git merge dev

-- 删除分支
git branch -d dev


创建并切换到新的dev分支，可以使用：
git switch -c dev

git switch master

Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>或者git switch <name>

创建+切换分支：git checkout -b <name>或者git switch -c <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>


