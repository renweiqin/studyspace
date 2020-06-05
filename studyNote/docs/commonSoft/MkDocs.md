# MkDocs预览与编辑工具

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

### 发布MkDocs

中文文档：https://markdown-docs-zh.readthedocs.io/zh_CN/latest/

命令行跳转至新建的MkDocs目录

输入以下命令以开始一个新项目.

```
$ mkdocs new my-project
$ cd my-project
```

我们看一下已经创建的初始化项目.

![The initial MkDocs layout](https://markdown-docs-zh.readthedocs.io/zh_CN/latest/img/initial-layout.png)

有一个配置文件 `mkdocs.yml`, 和一个包含文档源码的 `docs` 文件夹. 在 `docs` 文件夹里包含了一个名为 `index.md` 的文档.

MkDocs 包含了一个内建的服务器以预览当前文档. 控制台切换当前目录到 `mkdocs.yml` 配置文件相同文件夹, 输入 `mkdocs serve` 命令以启动内建服务器:

```
$ mkdocs serve
Running at: http://127.0.0.1:8000/
```

在浏览器中打开 http://127.0.0.1:8000/ , 你将看到以下页面:

![The MkDocs live server](https://markdown-docs-zh.readthedocs.io/zh_CN/latest/img/screenshot.png)

内建服务器支持在配置文件,文档目录或主题发生改变时自动载入并重新生成文档.

编辑 `docs/index.md` 文件并保存. 刷新浏览器你将看到文档被同步更新.

现在可以开始编辑配置文件 `mkdocs.yml` 了. 把 `site_name` 改成其他内容并保存文档.

![Editing the config file](https://markdown-docs-zh.readthedocs.io/zh_CN/latest/img/initial-config.png)

刷新浏览器你将看到网页标题已发生改变.

![The site_name setting](https://markdown-docs-zh.readthedocs.io/zh_CN/latest/img/site-name.png)

#### 添加页面

编辑 `doc/index.md` 文档, 将默认标题改为 `MkLorum`, 刷新浏览器即可看到标题变化.

现在为文档添加第二个页面:

```
$ curl 'jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
```

要为文档添加导航条, 只需在配置文件中添加导航条需要的标题和排序即可:

```
site_name: MkLorum
pages:
- [index.md, Home]
- [about.md, About]
```

刷新浏览器即可看到 `Home` 和 `About` 导航栏目.

#### 配置主题

可以在配置文件中修改文档主题. 在 `mkdocs.yml` 中添加如下内容:

```
site_name: MkLorum
pages:
- [index.md, Home]
- [about.md, About]
theme: readthedocs
```

刷新浏览器即可看到 ReadTheDocs 主题已被应用.

![Screenshot](https://markdown-docs-zh.readthedocs.io/zh_CN/latest/img/readthedocs.png)

#### 站点生成

我们现在已经可以发布 `MkLorum` 文档了. 通过以下命令生成文档.

```
$ mkdocs build
```

该命令创建了一个 `site` 新目录. 可以通过以下命令浏览该目录内容:

```
$ ls site
about css fonts img index.html js
```

注意源码被分别输出为 `index.html` 和 `about/index.html`. 主题中的其他文件也被复制到了 `site` 目录中.

如果你使用 `git` 等版本控制系统, 你可能不希望提交构建之后的文档到版本库. 在 `.gitignore` 中添加 `site/` 即可忽略该目录.

```
$ echo "site/" >> .gitignore
```

如果你使用其他版本控制系统则需要查阅相关文档以确定如何忽略指定目录.

一段时间后, 可能有文件被从源码中移除了, 但是相关的文档仍残留在 `site` 目录中. 在构建命令中添加 `--clean` 参数即可移除这些文档.

```
$ mkdocs build --clean
```

#### 发布

MkDocs 生成的文档只包含静态文件, 因此你可以将文档部署到任意地方. [GitHub project pages](https://help.github.com/articles/creating-project-pages-manually) 和 [Amazon S3](http://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html) 是不错的选择. 只需上传 `site` 目录到你需要发布的位置即可.