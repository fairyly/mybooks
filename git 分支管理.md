# Git 分支管理

## 分支理解
当使用 git commit 进行提交操作时，Git 会先计算每一个子目录的校验和，然后在Git仓库中这些校验和保存为树对象。 

随后，Git 便会创建一个提交对象，它除了包含上面提到的那些信息外，还包含指向这个树对象（项目根目录）的指针。

如此一来，Git就可以在需要的时候重现此次保存的快照。
![](https://user-gold-cdn.xitu.io/2017/10/11/5a81889528dc357b70889e28a64f3428?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

- blob对象, 保存文件快照对象
- 树对象, 记录目录结构和blob索引
- 提交对象, 包含指向树对象指针以及所有提交信息

## 本地分支管理

- git branch 查看当前本地有多少分支
- git branch -v 查看每个本地分支的最后一次提交
- git branch -vv 查看本地分支的所有跟踪分支
- git branch --merged 查看合并到当前分支的分支有哪些
- git branch' --no-merged 查看未合并到当前分支的分支有哪些
- git branch branch-name 创建分支
- git branch -d branch-name  删除branch-name分支
- git branch -D branch-name  强制删除branch-name分支


## 远程分支管理

远程跟踪分支以(remote)/(branch)命名, 它们是远程分支的本地引用, 表示上次你连接远程仓库时候分支所处的状态
- git ls-remote [remote-name]  获取远程应用的完整列表
- git remote show [remote-name] 显示远程分支更多信息
- git push origin --delete branch-name 删除远程分支


## 分支切换

- git checkout branch-name 切换分支
- git check -b branch-name 创建并切换到新分支上
- git checkout -b [branch] [remotename]/[branch] 创建一个跟踪远程分支的本地分支
- git checkout --track [remotename]/[branch] 设置本地分支跟踪远程分支
- git branch -u [remotename]/[branch] 设置本地分支跟踪远程分支


## 变基

- git rebase branch-name 将当前分支变基到branch-name分支上
- git rebase --onto master server client 取出 client 分支，找出处于 client 分支和 server 分支的共同祖先之后的修改，然后把它们在 master 分支上重演一遍
- git config --global pull.rebase true 更改git pull默认为git  pull --rebase


## 其它相关

- git fetch remote-name 抓取远程仓库有而本地仓库没有的数据, 并不合并, 相当于更新跟踪分支
- git log --oneline --decorate --graph --all 查看提交历史, 分支指向以及项目分支分叉情况
- git merge branch-name 将branch-name合并到当前分支上
- git push [remote] [branch] 推送分支到远程仓库


作者：猫xian森
链接：https://juejin.im/post/59dda0bcf265da432e5afba1


