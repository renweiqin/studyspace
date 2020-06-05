# 预览与编辑工具

Typora+Mkdocs+Github  安装

#### 安装MkDocs

我推荐安装`chocolatey`,chocolatey是一个windows上的包管理器，类似于ubuntu的apt，centos的yum。`chocolatey`的安装非常简单，管理员运行cmd，一行代码：

```bash
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

而后，使用chocolatey安装MkDocs：

```
choco install mkdocs
```

#### 安装Typora

Typora是一款优美的MarkDown文档编辑器，使用起来比VSCode要强不少。
访问 https://www.typora.io/ 下载安装包，之后安装即可。

### 使用

1.初始化一个MkDocs文档集

进入你要存档文档的目录，执行如下命令：

```
mkdocs new MyNotebook
```

该命令会在该目录下生成一个叫做`MyNotebook`的文件夹，里面包含mkdocs.yml文件与docs文件夹。

MkDocs可以将文档转换成html，mkdocs.yml是mkdocs编译时所需的配置文件，包含目录结构、主题名等配置字段。

2.Typora打开文件夹

打开Typora，菜单中选择`文件`->`打开文件夹`，之后选择刚刚创建的文件夹即可。

如果左栏中没有出现文件夹层级树，可以选择`视图`->`文件树视图`，此时界面显示如下：

![typora](https://pic-cdn.azimiao.com/wp-content/uploads/2019/05/typoramain.jpg)

左栏目录结构处，可以直接`管理`文件或文件夹，或者打开已经存在的文件。

3.编辑文本，插入图片

在Typora左栏中新建一个文件夹用来存放图片，命名为`images`。

- 所需的图片为文件模式，直接拖入该文件夹，使用相对路径引入到文档：

```markdown
    ![image](./images/test.jpg)
```

Markdown

- 使用截图工具截取图片，在预览模式下直接粘贴。粘贴后，Typora提示`复制图片到……`，点选上文中的`images`文件夹，Typora会自动复制文件并插入路径。

4.上传GitHub私人仓库

通过sourcetree或其他git软件，将本地目录上传到私有仓库即可。

转自：https://markdown-docs-zh.readthedocs.io/zh_CN/latest/