# Git底层命令

## 基础的linux命令

    clear: 清除屏幕
    echo 'test content':往控制台输出信息
    ll: 查看当前目录下的子文件 详细信息平铺
    ls:查看当前目录下的子文件 名称
    find 目录名: 将对应目录下的子孙文件子孙目录平铺
    find 目录名 -type f: 将对应目录下的文件平铺
    rm 文件名: 删除文件
    mv 源文件 重命名文件: 重命名
    cat 文件的url: 查看文件内容
    vim 文件的url: 
        i : 插入模式，可编辑
        esc/: : 进行命令执行
        q! : 强制退出
        wq : 保存退出
        set nu : 设置行号

## 初始化仓库

    git init 
        .git隐藏文件夹
            hooks 客户端或服务端的钩子脚本
            info 全局排除文件
            logs 日志
            objects 所有数据内容
            refs 指向数据的指针
            config 项目的配置选项
            description 描述信息
            HEAD 当前分支
            index 暂存区信息

## git对象

    是一个key: value 存储为blob类型
    🌟 向数据库写入内容 并返回对应键值 
        命令
            echo 'test content' | git hash-object -w --stdin
                -w 表示存储该对象，不写则只返回键值
                --stdin 便是从标准输入读取内容，不指定则需制定存储文件的路径,配合echo使用

            git hash-object -w 文件路径
        返回：
            返回一个40个字符的校验和，是一个SHA-1哈希值

## 树对象

    🌟 将多个文件组织到一起，形成一个目录，包含多个数据对象或者树对象。项目的快照
    创建： 
        使用 update-index为文件创建暂存区。通过 write-tree 生成树对象
        git update-index --add --cacheinfo (filetype) (key) (name)
            --add 首次加入暂存区i
            --cacheinfo 从数据库获取文件,如果在当前目录下不需要
            filetype 文件类型： 100644 普通文件； 100755 可执行文件； 120000 符号链接
            key git对象的key
            name git对象的value
        git write-tree  产生树对象，即项目文件快照，即生成项目版本
        git read-tree --prefix=bak (tree)  读取一个树对象添加到暂存区。

## 提交对象

    🌟 将每次树对象作为一次提交，同时可以指定当前提交对象的上一个提交对象，添加注释。项目的版本
    创建：
        echo '注释' ｜ git commit-tree tree-key -p (上个提交对象key)
            -p 在项目第一次提交时没有


    🌟 查看存储数据
        命令
            git cat-file -p 哈希值
                -p 返回内容
                -t 返回文件类型

    🌟 查看暂存区的文件
        git ls-files -s
