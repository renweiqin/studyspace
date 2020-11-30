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



### 添加忽略文件

先在项目路径下添加.gitignore文件。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018110714531858.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2E3NDg0NDg2NjA=,size_16,color_FFFFFF,t_70)
二.编辑.gitignore文件，其实就是输入一些相对路径或者通配符来避免文件提交。
　2.1)首先查看自己的项目目录：
![项目目录](https://img-blog.csdnimg.cn/20181107150322228.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2E3NDg0NDg2NjA=,size_16,color_FFFFFF,t_70)
　 2.2)编辑.gitignore文件，建立下面的规则：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181107150202339.png)
上图利用路径来控制哪些文件夹被忽略。