# Git 撤销

- 撤销工作目录修改
  - git checkout --(filename)
- 撤销暂存区修改
  - git reset [--mixed] HEAD (filename)
- 撤销提交
  - git commit --amend
  
## reset命令

- git reset --soft commitHash
  - 重置HEAD

- git reset [--mixed] commitHash
  - 重置HEAD
  - 重置暂存区

- git reset --hard commitHash
  - 重置HEAD
  - 重置暂存区
  - 重置工作目录
