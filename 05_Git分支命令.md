# Git分支命令

1. 分支
    git branch  -> 查看所有分支
    git branch (分支名)  -> 创建分支
    git branch -d 分支名 -> 删除分支
        -D (name) -> 强制删除分支
        -v  -> 查看分支滴最后一次提交
    git branch (name) (has)  指定提交对象版本创建分支

2. 切换分支
    git checkout 分支名
3. 查看当前分支所指对象
4. 指令重命名
    git config alias 新指令(logline) 老的完整指令(git log --oneline)
