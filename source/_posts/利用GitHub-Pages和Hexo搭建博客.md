title: 利用GitHub Pages和Hexo搭建博客
date: 2015-09-01 00:27:02
tags: [Blog, 前端] 
---

## 一、Github Pages
[Github Pages](https://pages.github.com/)可以用来发布静态的网页，因此可以用来搭建博客，重要是完全免费而且无限流量，世界各地均可快速访问。事实上github官方也支持这种做法：
>Create a blog and spread your ideas. Whatever you want!   [GitHub Pages原文链接](https://github.com/blog/272-github-pages)

<!--more-->

#### 1. Github Pages创建
Github Pages创建有两种方式：创建一个仓库名字为`github用户名.github.io`，或者在一个项目中例如blog下创建`gh-pages`分支，如果对应位置有网页时，输入githu用户名.github.io或者github用户名.github.io/blog就能够访问对应的内容。

| Type of GitHub Pages site| Host location on GitHub   |  How the page is redirected  | Example custom domain |
| --------   | :-----:  | --------- | :------: |
| User Pages site | username.github.io | Automatically redirected to the custom domain that has been set for it | user.example.com |
| Organization Pages site | orgname.github.io | Automatically redirected to the custom domain that has been set for it | org.example.com |
| Project Pages site owned by a user account | username.github.io/projectname | Automatically redirected to a subdirectory of a User Pages site custom domain (user.example.com/projectname) as well as any custom domain specified by the user | project.example.com |
| Project Pages site owned by an organization | orgname.github.io/projectname | Automatically redirected to a subdirectory of a Project Pages site custom domain (org.example.com/projectname) as well as any custom domain specified by the organization|project.example.com |

#### 2. 绑定域名
如果个人拥有域名，则可以绑定域名。首先可以用`ping username.github.io`的方式获得ip地址，在域名管理中心绑定域名。
![截图](http://7xktjr.com1.z0.glb.clouddn.com/domain_1.png)

在对应项目下添加**CNAME**文件，里面填写域名，例如在*username.github.io*下**CNAME**中填写`xxx.com`，在*blog*的**gh-pages**分支下**CNAME**中填写`blog.xxx.com`，则访问`xxx.com`和`blog.xxx.com`就分别转到*username.github.io*和*blog*的**gh-pages**分支下。

#### 3. tk域名
[tk域名](http://www.dot.tk/zh/index.html?lang=zh)，网络上最容易申请到的免费域名之一，是南太平洋岛国托克劳的顶级域名，同.cn一样为顶级国别域名，全球通用。可免费注册，亦可付费正式注册。以TK结尾，与COM、NET、CN一样同属顶级域名，TK意为TALK或者是TALKer（滔客：由英文单词Talker而来，意思是：说话的人，健谈的人，在网络上理解为互相聊天说话讨论的一群人，与闪客，黑客有异曲同工之妙。） [^来自百度百科]

## 二、Hexo
[hexo](http://)是一款基于Node.js的静态博客框架，支持**Markdown**和所有[Octopress](http://octopress.org/)的插件。`Hexo`简单优雅, 而且拥有众多的主题, 适合程序员搭建个人博客,而且支持多平台的搭建。
#### 1. Hexo搭建
>安装的前提是必须先安装`Node.js`，这里是Node.js的[官网](https://nodejs.org/)和[github](https://github.com/nodejs/node)，安装可参考[RUNOOB.com](http://www.runoob.com/nodejs/nodejs-install-setup.html)。

安装Node.js之后，可以参考Hexo的[官网](https://hexo.io/)安装`Hexo`。
```
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server  或   hexo s    //运行hexo服务
```
还有一些基本操作命令：
```
hexo new "xxx"      //新建博客，目录在source下的_post
hexo generate  或   hexo g     //编译Markdown生成静态的html，目录在public下，路径可在配置文件_config.yml下修改
hexo deploy    或   hexo d     //可将博客上传到github上，前提是在_config.yml下配置路径，并安装hexo-deployer-git
```
#### 2. Hexo主题
>Hexo拥有众多漂亮的主题，本博客的主题是[Yilia](https://github.com/litten/hexo-theme-yilia)，作者是`litten`。

在这里可以看到`Hexo`的[主题](https://github.com/hexojs/hexo/wiki/Themes)，如果想快速找到好看的主题，可以参考知乎上的问题[有那些好看的hexo主题？](http://www.zhihu.com/question/24422335)，当然问题发布已久，最高票数提到各主题在github上的**Star**数已发生变化。

主题会下载到`theme`目录下,修改`_config.yml`指定位置可更改主题：
```
# Extensions
## Plugins: http://hexo.io/plugins/
## Themes: http://hexo.io/themes/
theme: yilia      //填写主题的名字
```



