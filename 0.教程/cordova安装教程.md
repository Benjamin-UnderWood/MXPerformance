# cordova安装教程

## Cordova安装（Mac环境）

* 安装Cordova
* 安装git
* 安装Node.js

### 安装Cordova

* 在终端执行 
```
sudo npm install -g cordova 
```

* 等待一段时间即可安装完毕，使用 
```
cordova -v 
```

* 查看安装是否成功,此外还有更新Cordova的命令
``` 
sudo npm update cordova -g
```

* Cordova 更新完成后，还需要更新平台（比如更新ios） 
```
cordova platform update ios
```

----

### 安装git

* 安装git , macOS 和linux都自带git，使用命令 
```
git --version 
```

* 检查git,如果没有安装可以到[git官网][3]下载安装一个git客户端。 

-----

### 安装Node.js

* 要安装Cordova，需要先安装Node.js。在[Node.js官网][2]上下载并安装即可。  
运行命令 正常输出信息则安装成功 

```
node -v`
npm -v 
```

