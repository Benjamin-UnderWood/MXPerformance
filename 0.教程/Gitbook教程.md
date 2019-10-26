# Gitbook教程

# 一、安装使用gitbook
* 安装node
* 安装gitbook
```
npm install gitbook-cli -g
```

----
# 二、gitbook初始化

* 初始化书籍
```
gitbook init
```

* 其他命令

```
// 查看地址:直接访问localhost:4000 
gitbook serve // 启动服务
gitbook build // 编译构建你的书籍
gitbook pdf // 生成书籍为pdf
gitbook -V // 查看gitbook版本
```

* 目录介绍
	* SUMMARY.md就是自己要写文章章节目录

----

# 三、gitbook样式配置

* 在书籍下面都可以创建一个book.json

```
  "plugins": [ 
    "splitter@^0.0.8",/*使侧边栏的宽度可以自由调节*/
    "expandable-chapters-small@^0.1.7",//使左侧的章节目录可以折叠
    "anchors@^0.7.1",//添加 Github 风格的锚点样式
    "github@^2.0.0",//添加github图标
    "-lunr", 
    "-search", 
    "search-plus@^0.0.11",//支持中文搜索, 需要将默认的 search 和 lunr 插件去掉。
    "advanced-emoji@^0.2.1",//支持emoji表情
    "-sharing", 
    "sharing-plus@^0.0.2",//分享当前页面，比默认的 sharing 插件多了一些分享方式。
    "anchor-navigation-ex@0.1.8",//添加Toc到侧边悬浮导航以及回到顶部按钮;本插件只会提取 h[1-3] 标签作为悬浮导航
    "tbfed-pagefooter@^0.0.1",//为页面添加页脚
    "favicon@^0.0.2",//更改网站的 favicon.ico
    "copy-code-button"//为代码块添加复制的按钮。
  ],
```

* 如果配置了插件，需要使用安装命令
```
gitbook install ./
```

* 目录配置注意事项
	* 每个新增的目录中加入README.md否则菜单则为不可折叠
	* 同个目录下的文件采用自然排序来决定菜单生成的前后顺序, 故在文件或目录前加入 "数字-" 如 "0-" 或 "1-" 来排序菜单的前后顺序.
	* 菜单由目录自动生成, 菜单名称依赖md文件中的标题, 故每个md文件中必须添加标题, 否则无法生成目录.

# 四、Hexo博客集成GitBook

注意：执行下面脚本的位置是，进入books目录，脚本sh是放到hexo的根目录，所以执行的位置和放sh的位置不一样。

1. [参考链接](https://callmewing.com/2017/04/17/Hexo%E5%8D%9A%E5%AE%A2%E9%9B%86%E6%88%90GitBook/)
2. 我使用GitBook主要是用于整理归档的，记录的内容相对比较系统一点，零散的内容就以博客的形式发布。构建博客使用的Hexo和GitBook是相对独立的两套程序，需要自己手动集成起来。将博客发布到github，其实就是将public目录更新到github上面，只要在执行hexo g之后，hexo d之前，将GitBook的内容生成到public目录就可以了。 在博客的根目录建立文件夹books，GitBook的内容就存放在这里，每个子目录存放一本电子书的内容，在books目录下执行如下的GitBook构建脚本，即可将电子书的内容集成到Hexo博客当中。

```
#!/bin/bash

source=../public/books
for dir in *;
do
  #删除gitbook生成的内容
  if [ -d $source/$dir ]; then
    rm -r $source/$dir
  fi
  #重新生成gitbook的内容
  if [ -d $dir ]; then
    gitbook build $dir $source/$dir
  fi
done
```

# 五、生成pdf文件
1. 需要安装ebook-convert，Debian系统中，这个程序是包含在calibre包中。

```
sudo apt-get install calibre
gitbook pdf
```

# 六、gitbook几种主题区别

https://juejin.im/post/5cacbf3b5188251af11b2b04

## API 文档

* 如果文档本身是普普通文档模式,切换成 api 文档模式后并不会有太大变化,除非一开始就是接口文档,那样使用 theme-api 插件才能看出效果.

## theme-comscore 主题

* default 默认主题是黑白的,而 comscore 主题是彩色的,即标题和正文颜色有所区分.

## theme-default 主题

* theme-default 是 3.0.0 引入的默认主题,大多数插件针对的都是默认主题,如果切换到其他主题或者自定义主题,可能会造成某些情况下不兼容,甚至报错.


## FAQ 文档

* theme-faq 可以帮助我们构建问答中心,预设好常见问题以及相应答案模式,同时为了方便搜索到问题或答案,一般需要搜索插件的配合.
* 帮助中心没有工具栏,因此涉及到工具类的插件一律失效或主动移除,同时默认搜索插件也会失效.