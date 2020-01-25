---
categories: 
- Computer Science
- Git
---
## Git学习

### 创建版本库

mkdir dirname // make directory 创建目录 dirname 为目录名

pwd //print working directory 查看当前工作目录的完整路径

ls -a // 显示所有文件及目录，包括隐藏档

git init



### 修改与提交

git add filename1.txt filename2.txt // 把要提交的所有*修改* 放到暂存区

git commit -m "what I did in this commission" // 一次性把暂存区的所有修改提交到分支 -m表示message

git log // 查看修改日志

git log --graph // 查看分支合并图

git log --pretty=oneline // 每次修改在一行简明显示



git reflog // 查看命令历史

git reset --hard versionnumber // 彻底回退到某版本

git status // 查看版本库状态



cat filename // 查看文件内容

git diff HEAD -- readme.txt // 查看版本库最新版本和工作区的readme文件的区别

git restore --staged filename // 撤销提交到暂存区



rm filename // remove 删除文件

rmdir dirname // 删除空文件目录

git rm filename // 从版本库中删除文件

git checkout -- filename // 误删文件的恢复



### 远程仓库

git remote add origin git@github.com:longqianh/learngit.git

git push -u origin master

git clone git@github.com:longqianh/learngit.git



### 分支管理

git checkout 

git branch // 查看分支

git branch -d branchname // 删除分支

git branch branchname // 创建分支

git checkout branchname 或 git checkout branchname // 切换分支

git checkout -b branchname 或 git switch -c branchname // 创建并切换分支

git merge branchname // 合并branch分支到master上

git merge --no-ff -m "branchname" // 合并branch分支到master上,并产生一条记录

建议：使用分支完成某个任务，合并后再删掉分支



git remote // 查看远程库信息

git branch --set-upstream branchname origin/branchname // 建立本地分支与远程分支的关联

git pull // 拉取远程分支新提交并合并

git push branchname // 向远程仓库推送分支



git tag tagname  // 给分支打标签

git tag -a tagname -m "message" // 给标签加说明

git tag // 查看所有标签

git push tagname // 推送一个本地标签到远程

git push --tag // 推送所有本地标签

git tag -d tagname // 删除标签

git push origin :refs/tags/tagname // 删除一个远程标签



git config --global alias.st status // 配置别名 加--global对当前用户起作用，不加则对当前仓库起作用