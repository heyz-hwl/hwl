---
title: macOS Sierra 安装MongoDB
---

## 使用brew安装
> brew install mongodb
这个时候终端就会开始下载和安装mongodb

### 下载完以后,需要创建一个目录,为mongo默认的数据写入目录

```
sudomkdir -p /data/db
```
### 然后给该目录可读可写的权限

```
sudo chown `id -u` /data/db
```
### 这个时候可以修改目录,也可以不修改,修改的话是这样

```
// /data/db 目录是mongo的默认目录，如果你想使用其他目录，可以使 --dbpath 参数
mongo --dbpath dir_name
// dir_name 为你的目录名字
```
### 这时候就可以`mongod`启动mongodb了

## 如果有一天你发现你的数据库突然启动不了了，可能是你为正常关闭导致的，你可以删除掉mongod.lock文件，然后重新启动，如果还是不可以，你可以查看一下进程，然后杀掉：

```
ps -aef | grep mongo
```
如下：
![](media/14816011194739/14816082518188.jpg)

然后根据进程ID杀掉进程：

```
sudo kill 6955
```

重新启动mongodb服务，即可：

```
mongod
```


