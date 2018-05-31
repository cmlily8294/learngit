```bash
git init  //初始化版本库

git add //添加文件到git

git commit -m '内容' //提交

git status //查看状态

git diff HEAD -- readme.txt ///与版本库最新版本比较

/////////////////撤销修改////////////////

//场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

//场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

//场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

/////////////////撤销修改////////////////


查看分支：git branch

创建分支：git branch [name]

切换分支：git checkout [name]

创建+切换分支：git checkout -b [name]

合并某分支到当前分支：git merge [name]

删除分支：git branch -d [name]
git branch -D //强行删除分支

--no-ff方式的git merge，不使用Fast forward模式：
git merge --no-ff -m "merge with no-ff" dev


当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。

git stash list  //查看


git remote add origin https://github.com/cmlily8294/learngit.git //与远程库关联
git push -u origin master //推送到远程库 第一次推送时加 -u

git remote -v  //查看远程详细信息

git clone  https://github.com/cmlily8294/learngit.git //克隆远程库

git pull  //拉取最新修改

git log --pretty=oneline  //查看日志
git log --graph     //查看分支合并图。

git reset --hard HEAD^   //版本回退 ^ 表示上一个版本，依次类推 ^^ 表示上两个版本  HEAD~100表示前100个版本

git reset --hard 7e443a2  //回退到某个版本

git reflog  //记录每次操作的命令，可以从中找到曾经回退的版本号

git rm test.txt //从git版本库中删除某个文件


https方式每次都要输入密码，按照如下设置即可输入一次就不用再手输入密码的困扰而且又享受https带来的极速

设置记住密码（默认15分钟）：

git config --global credential.helper cache
git config --global credential.helper winstore //windows下
如果想自己设置时间，可以这样做：

git config credential.helper 'cache --timeout=3600'
这样就设置一个小时之后失效

长期存储密码：

git config --global credential.helper store

增加远程地址的时候带上密码也是可以的。(推荐)
http://yourname:password@git.oschina.net/name/project.git


Creating a new branch is quick.
Creating a new branch is quick.
Creating a new branch is quick.

Git is a distributed version control system.
Git is free software distributed under the GPL

```