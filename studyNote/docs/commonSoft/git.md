# git命令

### 创建本地分支并切换

```
git checkout -b branchName
```

### 推送本地分支到远端

```
git push origin branchName
```

### 建立追踪关系，在现有分支与指定的远程分支之间

git push --set-upstream origin branchName

### 查看远端分支

```
git branch -r
```

### 列出所有本地分支

```
git branch
```

### 列出所有本地分支和远程分支

```
 git branch -a
```

### 删除分支

```
 git branch -d [branch-name]
```

### 删除远程分支

```
git push origin --delete [branch-name]
```

### 提交本地代码

```
git add .` `git commit -m ``"first commit"
```

### 查看文件修改情况

```
git status
```

### 查看具体的内容修改

```
git diff
```

### 提交本地仓库