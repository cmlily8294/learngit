
> Git is a distributed version control system.
> Git is free software distributed under the GPL.

## 基本操作

### 初始化版本库
```bash

git init

```

### 添加文件到git
```bash

git add

```

### 提交
```bash

git commit -m '内容' 

```

### 与远程库关联

```bash

git remote add origin https://github.com/cmlily8294/learngit.git

git push -u origin master //推送到远程库 第一次推送时加 -u

git remote -v  //查看远程详细信息

```

### 克隆远程库

```bash

git clone  https://github.com/cmlily8294/learngit.git

```

### 拉取最新修改

```bash

git pull

git pull –rebase   //拉取代码时删除无意义的commit

```

### 查看状态
```bash

git status 

```
### 与版本库最新版本比较
```bash

git diff HEAD -- readme.txt 

```

### 从git版本库中删除某个文件

```bash

git rm test.txt

```

## 分支操作

### 查看分支

```bash

git branch

```
### 创建分支

```bash

git branch [name]

```
### 切换分支

```bash

git checkout [name]

```

### 创建+切换分支

```bash

git checkout -b [name]

```

### 拉取远程分支并创建对应本地分支

```bash

 git checkout -t origin/[name]

```
### 清理无效的远程追踪分支
```bash
 git remote prune origin
```
### 从某个tag创建新分支

```bash

git checkout -b branch_name tag_name

```

### 合并某分支到当前分支

```bash

git merge [name]

```
 不使用Fast forward模式

```bash

git merge --no-ff -m "merge with no-ff" dev

```

### 删除分支

```bash

git branch -d [name]

```

### 强行删除分支

```bash

git branch -D

```

### 删除远程分支
```bash

git branch -r -d origin/[name]

```

### 本地分支推送到远程
```bash

git push origin :[name]

```

## 历史日志

### 查看日志

```bash

git log --pretty=oneline

```

### 查看分支合并图

```bash

git log --graph

```

## 回退和撤销修改

### 版本回退
```bash

git reset --hard HEAD^  //版本回退 ^ 表示上一个版本，依次类推 ^^ 表示上两个版本  HEAD~100表示前100个版本

```

### 回退到某个版本

```bash

git reset --hard 7e443a2

```
### 撤销修改

- 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file`。
- 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD file`，就回到了场景1，第二步按场景1操作。
- 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

### 临时切换

当手头工作没有完成时，先把工作现场`git stash`一下，然后去修复bug，修复后，再`git stash pop`，回到工作现场。

```bash

git stash  //保留工作现场

git stash pop  //回到工作现场

git stash list  //查看工作现场

```

## 其他操作

### 命令历史记录

记录每次操作的命令，可以从中找到曾经回退的版本号

```bash

git reflog

```

### 切换commit到新分支

切换分支后将commit提交的内容也转换到新分支

```bash

git cherry-pick [commitid]

```

### 密码相关

https方式每次都要输入密码，按照如下设置即可输入一次就不用再手输入密码的困扰而且又享受https带来的极速

设置记住密码（默认15分钟）：

```bash

git config --global credential.helper cache

git config --global credential.helper winstore //windows下

```
如果想自己设置时间，可以这样做：
```bash

git config credential.helper 'cache --timeout=3600'

```
这样就设置一个小时之后失效

长期存储密码：
```bash

git config --global credential.helper store

```

增加远程地址的时候带上密码也是可以的。(推荐)
```bash

http://yourname:password@git.oschina.net/name/project.git

```
