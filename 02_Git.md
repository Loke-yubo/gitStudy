# Git安装

    傻瓜式安装
    查看安装版本：
        git --version

## git初始化

    git 配置的三个级别：
        --system 操作系统
        --global 当前用户
        --local(默认) 当前项目，不写即是当前项目，同时优先级最高，依次向上优先级逐渐降低
    配置：
        git config --global user.name 'user.name'
        git config --global user.email 'user.email'
    查看配置：
        git config --global(--system/--local) --list

## 区域

    工作区： 
    暂存区
    版本库

## 对象

    Git对象
    树对象
    提交对象
