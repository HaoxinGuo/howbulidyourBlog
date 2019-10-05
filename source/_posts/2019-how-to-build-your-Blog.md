---
title: 怎么样创建你的Blog
top: false
cover: false
toc: true
mathjax: true
date: 2019-10-04 00:13:07
password:
summary:
tags:
- 软件
categories:
- 软件
---

# 我的博客源代码地址
大家可以直接素质二连，star&fork我的博客源代码：
https://github.com/HaoxinGuo/howbulidyourBlog ，然后改改配置就可以写文章啦。

为了减小源码的体积，将插件目录node_modules进行了压缩，大家下载完后需要解压。

- 首先运行```git clone git@github.com:HaoxinGuo/HaoxinGuo.github.io.git```将所有文件下载到本地。
- 解压node_modules.zip，然后删除node_modules.zip和.git文件夹。
- 安装下面要求配置你的文件。
# 快速搭建
- 根目录配置文件_config.yml和主题目录配置文件_config.yml中修改个人信息,推荐使用notepad++打开文件。
- 根目录配置文件中修改deploy一栏的repository。
![修改deploy一栏的repository](xiugai.png)
- 根目录配置文件中修改baidu_url_submit一栏的token([注册百度统计后怎么获取你的token](http://bbs.zhanzhang.baidu.com/thread-138808-1-1.html))。
![修改baidu_url_submit一栏的token和host](token.png)
- 主题配置文件中修改gitalk一栏，修改方法见正文。

**接下来安装流程配置环境后就可以发布你的Blog了**

***平时常用命令***：
```
hexo g  # 生成博客网页文件
hexo s  # 本地预览博客
hexo d  # 上传网页文件到github
#注：必须使用hexo d上传你的Blog
```

目录结构

- 安装Node.js
- 添加国内镜像源
- 安装Git
- 注册Github账号
- 安装Hexo
- 连接Github与本地
- 写文章、发布文章
- 绑定域名
- 备份博客源文件
- 博客源代码下载

# 安装Node.js
首先下载稳定版[Node.js](https://nodejs.org/en/)。
![node.js下载](xiazaishili.png)
安装选项全部默认，一路点击Next。
最后安装好之后，按Win+R打开命令提示符，输入node -v和npm -v，如果出现版本号，那么就安装成功了。
![node.js安装成功显示示例](npmshili.png)
# 添加国内镜像源
使用阿里的国内镜像进行加速。
```
npm config set registry https://registry.npm.taobao.org
```
# Git安装

为了把本地的网页文件上传到github上面去，我们需要用到分布式版本控制工具————Git[下载地址](https://git-scm.com/download/win)。
![安装GIT](gitxiazai.png)
**安装选项还是全部默认，只不过最后一步添加路径时选择Use Git from the Windows Command Prompt**，之后我们就可以直接在命令提示符里打开git了。

安装完成后在命令提示符中输入git --version验证是否安装成功。

# 注册Github账号
接下来就去注册一个github账号，用来存放我们的网站。[注册地址](https://github.com/)
注册完成后打开https://github.com/ ，新建一个项目，如下所示：
![新建项目](newrepository.png)
然后如下图所示，输入自己的项目名字，后面一定要加**.github.io**后缀，**勾选README初始化**。名称一定要和你的github名字完全一样，比如你github名字叫HaoxinGuo，那么仓库名字一定要是HaoxinGuo.github.io。
![仓库名字命名](chushihua.png)
# 安装Notepad++
安装[Notepad++]( https://notepad-plus-plus.org/downloads/ )，方便以后编辑Markdown文件。
# 安装Hexo
在合适的地方新建一个文件夹，用来存放自己的博客文件，比如我的博客文件都存放在C:\user\12101\desktop\blog目录下。
以管理员身份运行cmd，进到该目录下，关于cmd的操作命令可以参考该[链接1]( https://blog.csdn.net/LJFPHP/article/details/78818696 )[链接2]( https://blog.csdn.net/xiaosemei/article/details/79270904 ) ，输入
```
npm i hexo-cli -g
```
安装Hexo。可能会有几个报错，无视它就行。
安装完后输入hexo -v验证是否安装成功。
![hexo安装成功](hexo.png)
# 初始化网站
初始化我们的网站，输入```hexo init```初始化文件夹，接着输入```npm install```安装必备的组件。
这样本地的网站配置也弄好啦，输入hexo g生成静态网页，然后输入hexo s打开本地服务器，然后浏览器打开http://localhost:4000/ ，就可以看到我们的博客啦，效果如下：
![效果示例，可能和你的不一样](xiaoguo.png)
按ctrl+c关闭本地服务器。
# 连接Github与本地
首先右键打开git bash，然后输入下面命令：
```
git config --global user.name "Your Name of Github"
git config --global user.email "your email of Github"
```
用户名和邮箱根据你注册github的信息自行修改。
然后生成密钥SSH key：
```
ssh-keygen -t rsa -C "your email of Github"
```
打开github，在头像下面点击settings，再点击SSH and GPG keys，新建一个SSH，名字随便。
![settings](setting.png)
![SSH and GPG keys](SSH.png)
![新建一个SSH](NewSSH.png)
在git bash(右键git bash here )中输入```cat ~/.ssh/id_rsa.pub```或者打开如图所示的文件“id_rsa.pub”
![文件位置](RA.png)
将文件中的内容复制到框中，点击确定保存。
## 测试是否成功
输入```ssh -T git@github.com```，如果如下图所示，出现你的用户名，那就成功了。
![Git配置成功](chenggong.png)

# 创建你的Blog
## 克隆你的yourname.github.io项目到本地
```
git clone git@github/Yourname.github.io
```
## 克隆我的git项目到本地
```
git clone https://github.com/HaoxinGuo/howbulidyourBlog
```
删除我的项目的```.git```文件，其余的粘贴到你的**yourname.github.io**文件中，接下来修改配置文件
## 配置自己的文件
博客根目录下的_config.yml文件，这是博客的配置文件，在这里你可以修改与博客相关的各种信息。
### 修改最后一行的配置
```
deploy:
  type: git
  repository: https://github.com/HaoxinGuo/HaoxinGuo.github.io
  branch: master
```
**repository修改为你自己的github.io项目地址。**
## 写文章、发布文章
首先在博客根目录下右键打开git bash，安装一个扩展```npm i hexo-deployer-git```。
然后输入```hexo new post "article title"```，新建一篇文章。
然后打开```..\blog\source\_posts```的目录，可以发现下面多了一个文件夹和一个.md文件，一个用来存放你的图片等数据，另一个就是你的文章文件。

编写完markdown(注意编码为UTF-8，要不然打开网页后乱码)文件后，根目录下输入```hexo g```生成静态网页，然后输入```hexo s```可以本地预览效果，最后输入```hexo d```上传到github上。这时打开你的github.io主页就能看到发布的文章啦。

# 创建你特有的域名

