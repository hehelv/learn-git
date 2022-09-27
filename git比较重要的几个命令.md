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
输入 git status ，git会有提示
一般是
    git restore  文件 从暂存区退回


## 恢复工作区误删文件
git checkout -- 文件名 
从版本库删除文件 git rm 文件名



# 分支管理




# 打标签


