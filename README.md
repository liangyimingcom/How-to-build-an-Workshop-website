# 如何搭建一个Workshop网站

How to build an Workshop website

如何搭建一个Workshop网站，如https://mfgee.ml，参考下图：

![image-20210528120019229](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528120019229.png)



## 所需工具与服务：

**本地工具：**

- [ ] Typora：MD编辑工具IDE；
- [ ] Hugo： 是一款开源的使用 go 语言写的静态网站生成器

**云服务：**

- [ ] GitHub：源码共享，与团队编辑的版本控制；
- [ ] AWS Amplify：Amplify支持github提交后立刻发布新版本



# 第一步：本地编辑网站内容



1）下载Workshop Sample网站： workshop Sample网站源码在： https://github.com/liangyimingcom/MFGEEML-Workshop/tree/master ，需要下载到本地，并解压缩；

2）下载Typora：https://typora.io/

3）使用Typora编辑 Workshop Sample其中的页面，路径如下图，并查看编辑的效果：

![image-20210528150712306](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528150712306.png)

4）页面排序的规则说明如下

![image-20210528150848279](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528150848279.png)

5）详细说明，请参考这里：https://themes.gohugo.io//theme/hugo-theme-learn/en/cont/

https://themes.gohugo.io//theme/hugo-theme-learn/en/cont/pages/





# 第二步：通过Hugo实现可视化效果



1）安装Hugo ：

去到 [Hugo Releases](https://github.com/spf13/hugo/releases) 下载对应的操作系统版本的Hugo二进制文件（hugo或者hugo.exe），或者Mac下直接使用 `Homebrew` 安装：

```bash
brew install hugo
```

更多的hugo安装教程参考：https://www.gohugo.org/



2）运行Hugo：

在你的站点根目录执行 `Hugo` 命令进行调试：

```bash
$ hugo server 
```

![image-20210528152832619](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528152832619.png)



3)浏览器里打开： `http://localhost:1313`

![image-20210528152911969](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528152911969.png)



# 第三步：上传到GitHub



1）Git 基本操作原理分析：

Git 的工作就是创建和保存你项目的快照及与之后的快照进行对比。

Git 常用的是以下 6 个命令：**git clone**、**git push**、**git add** 、**git commit**、**git checkout**、**git pull**，后面我们会详细介绍。

![img](https://www.runoob.com/wp-content/uploads/2015/02/git-command.jpg)

**说明：**

- workspace：工作区
- staging area：暂存区/缓存区
- local repository：版本库或本地仓库
- remote repository：远程仓库

一个简单的操作步骤：

```
$ git init    
$ git add .    
$ git commit  
```

- git init - 初始化仓库。
- git add . - 添加文件到暂存区。
- git commit - 将暂存区内容添加到仓库中。

 

2）把修改后的sample workshop上传到GitHub，具体步骤请参考：http://lazynight.me/2898.html

3）如果对代码上传没兴趣，可以用IDE的Github Desktop鼠标搞定，下载地址在：https://desktop.github.com/

https://docs.github.com/cn/desktop/installing-and-configuring-github-desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop

![image-20210528154631387](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528154631387.png)



4）邀请team其他成员编辑 workshop 网站的内容，流程为：

1. 合作者 – 代码仓库的所有者可以为单个仓库增加具备只读或者读写权限的协作者。合作者方式比较实用，也很方便，新建一个Repository，完毕之后，进入Repository的Settings，然后在Manage Collaborators里就可以管理合作者了。

2. 其他合作者，命令行方式为：实用 ssh-keygen -C "YourEmail@example.com" （这里的email使用github账号）生成公钥和私钥，在Accounts Settings=》SSH keys 将公钥上传上去。上传完成后，可使用 clone remote Repository 使用SSH方式登录（这里的私钥使用刚才生成的） 这样，其他合作者就可以正常的PUSH代码了。

3. **其他合作者，图形界面方案为IDE的Github Desktop鼠标搞定（推荐）**

   图解如下：：

A、github发出邀请：

![image-20210528160650757](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528160650757.png)

B、合作者从邮件点击确认：

![image-20210528161431966](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528161431966.png)

C、接受邀请成功后，可以打开权限

![image-20210528161647773](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528161647773.png)

D、Github Desktop尝试编辑后提交成功；

![image-20210528163110821](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528163110821.png)





# 第四步：使用 Amplify进行网站发布



1）Amplify配置

![image-20210528163216279](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528163216279.png)

2）域名配置

![image-20210528163301823](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210528163301823.png)



3）可以尝试更新GitHub并刷新Amplify效果



**转载请注明源地址** https://github.com/liangyimingcom/How-to-build-an-AWS-Workshop-website







# 补充与附录

### 1）如何添加code一键复制的效果，如下图

![image-20210609122544978](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210609122544978.png)



步骤：

1）首先确定你的代码类型，如上类型是python代码；

2）在Typora中进入源代码模式：

![image-20210609122830289](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210609122830289.png)



**3）在代码开头位置，添加~~~前缀并加入关键字python，同时结尾处加入后缀，如下：**

![image-20210609123031763](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210609123031763.png)



**4）base/shell/dos的关键字可以参考如下：**

Some shell samples:

```sh
Shell:      console, shell
Bash:       bash, sh, zsh
PowerShell: powershell, ps
DOS:        dos, bat, cmd
```

Example:

~~~sh
```bat
cd \
copy a b
ping 192.168.0.1
```
~~~



**5）完整的关键字请参考这里：**

list of languages   https://github.com/highlightjs/highlight.js/blob/master/SUPPORTED_LANGUAGES.md
