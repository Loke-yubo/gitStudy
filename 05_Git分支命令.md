# Git分支

本质是一个提交对象 被HEAD引用

## 分支命令

1. 分支
    git branch  -> 查看所有分支
    git branch (分支名)  -> 创建分支
    git checkout 分支名 -> 切换分支
    git checkout -b 分支名 -> 创建并切换分支
    git branch -d 分支名 -> 删除分支
        -D (name) -> 强制删除分支
        -v  -> 查看分支滴最后一次提交
    git branch (name) (has)  指定提交对象版本创建分支
    git merge branchname  -> 合并分支 快进合并指在同一条线上的分支不会冲突。典型合并指不在同一条线上的合并，可能冲突。
    git branch -merged -> 查看已经合并过的分支
    git branch --no-merged -> 查看没有合并过的分支列表
    git config alias 新指令(logline) 老的完整指令(git log --oneline) -> 重命名一个指令

## 注意点

    在切换分支时一定要保证当前分支是干净的
