title: Ubuntu 重装Unity桌面
date: 2015-08-15 22:44:04
tags: Ubuntu
---
#### 1. `Ctrl+alt+T`启动终端或者`Ctrl+alt+F1`登录字符界面，执行以下命令重新安装Ubuntu unity：
```
sudo apt-get install ubuntu-desktop
sudo apt-get install unity
sudo apt-get install unity-common
sudo apt-get install unity-lens*
sudo apt-get install unity-services
sudo apt-get install unity-asset-pool
```
`备注：后面两行命令执行时如果提示已经安装过了，那就不需要了。`
<!--more-->

#### 2. 更新ubuntu及组件
```
sudo apt-get update
sudo apt-get upgrade
```


#### 3. 移除所有无效的包和缓存
```
sudo apt-get autoremove
sudo apt-get autoclean
```

