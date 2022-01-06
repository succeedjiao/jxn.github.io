# Git学习

## 一、git配置

### 配置用户名和邮箱

```git
git config global user.name "您的姓名"
git config global user.email "您的邮箱"
```

### 查看配置信息

```git
git config --list
```

## 二、提交步骤

```git
git init 初始化仓库
git status 查看文件的状态
git add 文件列表  追踪文件，将文件添加到暂存区
git commit -m 描述信息  向仓库中提交代码
git log  查看提交记录
git checkout 文件  向暂存区中的文件覆盖工作目录中的文件;切换分支
git rm --cached 文件; 将文件从暂存区中删除
```

## 三、恢复记录

```git
git rest --hard commitID; 将git仓库中指定的更新记录恢复出来，并且恢复暂存区和工作目录
```
