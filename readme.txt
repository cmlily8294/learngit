git init  //初始化版本库

git add //添加文件到git

git commit -m '内容' //提交

git status //查看状态

git diff HEAD -- readme.txt ///与版本库最新版本比较

/////////////////撤销修改////////////////

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

/////////////////撤销修改////////////////

git remote add origin https://github.com/cmlily8294/learngit.git //与远程库关联
git push -u origin master //推送到远程库 第一次推送时加 -u

查看分支：git branch

创建分支：git branch [name]

切换分支：git checkout [name]

创建+切换分支：git checkout -b [name]

合并某分支到当前分支：git merge [name]

删除分支：git branch -d [name]
git branch -D //强行删除分支

--no-ff方式的git merge：
git merge --no-ff -m "merge with no-ff" dev


当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。


Creating a new branch is quick.
Creating a new branch is quick.
Creating a new branch is quick.

Git is a distributed version control system.
Git is free software distributed under the GPL

changed

changed*2