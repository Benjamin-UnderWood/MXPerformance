# hexo部署教程

## 第一步：部署hexo前提准备 
1. 到node.js 网站 https://nodejs.org/en/  下载node.js 直接安装，安装完，查看版本 ，node -v 
2. 到homebrew 网站  http://brew.sh/index_zh-cn.html 使用下面的命令安装,如果安装失败，使用sudo 
 
``` 
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" 
 
``` 
 
## 第二步：开始部署hexo 
 
1. 使用下面的命令，一条一条来，如果不行，用sudo 
 
``` 
npm install hexo-cli -g 
hexo init blog 
cd blog 
npm install 
hexo server 
``` 
 
2. 直接访问本地部署好的hexo 
 
## 第三步：利用hexo发布文章 
 
1. 新建文章，先进入hexo文件 
 
``` 
hexo new " 新文章" 
``` 
 
2. 写好文章后，生成静态文件 
 
``` 
hexo g  
``` 
 
3. 生成静态文件后，上传到github 
 
``` 
hexo d 
``` 
 
#### hexo 技巧 
 
1. 因为hexo生成的静态文件是放在public文件夹下面的，如果你部署github的时候，使用的git destop版本来上传代码的话，你可以clone你的git下来的时候，clone到hexo文件下，且改名为public，那么下次hexo生成静态文件的时候就会直接生成到clone下来的git文件夹里面，那你用git desktop上传代码的时候，就可以直接commit上传了 
