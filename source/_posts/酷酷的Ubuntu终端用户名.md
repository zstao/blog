title: 酷酷的Ubuntu终端用户名
date: 2015-08-31 22:21:43
tags: Ubuntu
---
>Ubuntu系统终端上的用户名有时很长，或者是不想显示用户名，或者是想设置个性化的用户名，这时我们可以通过修改特定文件的内容已达到修改的目的。

<!--more-->


#### 1. `Ctrl+alt+T`打开终端，用**vim**或者**gedit**打开`Home`目录下的`.bashrc`文件
```
sudo vim ~/.bashrc 或者 sudo gedit ~/.bashrc
```


#### 2. 在.baserc文件的有这样的一句`export PS1='\u@\h \w:\$ '`，其中`\u`表示用户名，`\h`表示主机名
可修改为`export PS1='^-^ \w:\$ '`、`export PS1=':) \w:\$ '`，则效果分别如下图所示：
![](http://7xktjr.com1.z0.glb.clouddn.com/ubuntu_terminal_1.png)
![](http://7xktjr.com1.z0.glb.clouddn.com/ubuntu_terminal_2.png)


