---
title: Mongodump 和 Mongorestore 
---

## mongodump
> mongodump -h dbhost -d dynamo -c collection -o dbdirectory -u uesrname -p pwd其中-h 是数据库地址，127.0.0.1  -d 是数据库名字 context  -o 存储的地址  如果省略就在当前目录下保存 -u 是用户名 -p 是密码

### 参数说明：
```
-h:指明数据库宿主机的IP
-u:指明数据库的用户名
-p:指明数据库的密码
-d:指明数据库的名字
-c:指明collection的名字
-o:指明到要导出的文件名
-q:指明导出数据的过滤条件
```
## mongorestore
> mongorestore -d context /Users/hwl/code/database/dump/context/contexts.bson
-h 数据库地址  默认为127.0.0.1 -c为collection

### 参数说明：
```
-h:指明数据库宿主机的IP
-u:指明数据库的用户名
-p:指明数据库的密码
-d:指明数据库的名字
-c:指明collection的名字
-o:指明到要备份的文件名
-q:指明备份数据的过滤条件
```


