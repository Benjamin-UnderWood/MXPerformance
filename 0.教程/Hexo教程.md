# Hexo教程

# 一、部署域名

1.新建CNAME文件，没有后缀 

2.在文件内部填写申请后的域名 

3.CNAME文件放在hexo中的source文件夹中

# 二、常用命令

## 初始化tag和category页面
```
// 初始化 tag、category页面，在主目录下执行命令
hexo new page tag
hexo new page category
hexo new page books
hexo new page about

进入页面目录
cd source/tag
增加layout字段
// source\tag\index.md
---
title: Tag
layout: tag
---
category页面同理，layout字段键值为category。 

```



# 三、用过的主题

https://github.com/Siricee/hexo-theme-Chic