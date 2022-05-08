# Git操作

1. 创建工作目录
    git init
2. 添加暂存区
    git add (路径)

    底层命令
        git hash-object -w (文件名) 添加了多少个文件，生成多少个git对象
        git updata-index  生成树
3. 提交版本
    git commit
        -m "注释"
        -a 跳过暂存区

    底层命令：
        git write-tree
        git commit-tree
4. 查看当前文件夹文件状态
    git status
    git diff    查看哪些修改没有添加暂存区
    git diff  --staged 查看哪些修改没有提交

5. 查看日志
    git log
        --oneline   -> 将日志记录一行一行的显示
        --grep="关键字"   -> 查找日志记录中(commit提交时的注释)与关键字有关的记录
        --graph  -> 记录图形化显示 ！！！
        --all -> 将所有记录都详细的显示出来
        --author "username" -> 查找这个作者提交的记录
        --reverse    -> commit 提交记录顺序翻转
        -num   -> git log -10 显示最近10次提交 ！！！
        -p   -> 显示每次提交所引入的差异（按 补丁 的格式输出）！！！
        --before=  1  day/1  week/1  "2019-06-06"    -> 查找规定的时间(如:1天/1周)之前的记录
        --after= "2019-06-06"  -> 查找规定的时间(如:1天/1周)之后的记录
        --stat   -> 显示每次更新的文件修改统计信息，会列出具体文件列表 ！！！
        --abbrev-commit   -> 仅显示 SHA-1 的前几个字符，而非所有的 40 个字符 ！！！
        --pretty=format:"xxx"  ->  可以定制要显示的记录格式 ！！！
6. 删除文件
    git rm 文件名
7. 重命名
    git mv 原文件名 改为滴文件名
