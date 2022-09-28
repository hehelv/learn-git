# 简单操作
git add .
git commit -m ""


git status : 告诉你文件有没有被修改
git diff readme.txt : 告诉你修改了那些内容(工作区内，add到暂存区就看不出了)

想要知道版本库中 readme.txt 与 工作区中readme.txt 的区别，使用：
git diff HEAD -- readme.txt

HEAD指向的版本就是当前的版本
切换版本：
git reset --hard commit_id(前几位就可以)

git log 查看包括当前版本以前的版本，帮助回到过去的版本

git reflog 查看命令历史， 回到“未来”的版本


## 想要撤回修改怎么做？
git reset HEAD 文件  把暂存区的修改撤销，退回工作区

输入 git status ，git会有提示
一般是
    git restore  文件 从暂存区退回


## 恢复工作区误删文件
git checkout -- 文件名 
从版本库删除文件 git rm 文件名



# 分支管理
## 基础命令
git branch : 查看分支

git checkout 分支名 : 切换分支

git checkout -d 分支名 ： 删除分支

## 合并
git merge 分支 ： 将分支合并到当前分支 （默认是 ff（fast forword）模式）

git log --graph : 可以看到分支合并图

git merge --no-ff : 取消ff模式合并， 合并之后会创建一个新分支

## 保存当前工作环境
保存当前工作环境（有时候要切换其他分支，但是不想提交，使用这个）：
git stash : 保存当前工作环境

git stash pop : 切回分支后， 还原当时的工作环境

git stash list : 查看你之前stash的所有环境

git stash apply stash@{0} ： 选择使用list中其中一个环境

git cherry-pick <commit> ：选择一个提交修改应用到当前分支

## 删除版本库中分支
git branch -D 分支名

## 多人协作
当你推送时，报错，说明有人已经在你之前提交

git pull ： 先拉下来

本地解决冲突，再push

git push


## 本地分支与远程分支建立关联
git branch --set-upstream branch-name origin/branch-name

git remote -v : 查看远程库信息


## rebase

git rebase : 可以将merge后的git log --graph, 变成一条直线

更加好看

# 打标签

标签是打在某次提交上的， 相当于一次快照

git tag tagname <commit> : 给某次提交加标签

git tag tagname -m "xxx" : 可以给标签添加信息

git tag ：查看所有标签

git tag -d  tagname : 本地删除tag

推送标签到远程：
git push origin tagname
git push origin --tags : 推送本地所有标签


git push origin :refs/tags/<tagname> ： 远程删除标签


# 关于一些小技巧

可以直接看廖雪峰：https://www.liaoxuefeng.com/wiki/896043488029600/900004590234208
- .gitignore文件

- 别名
