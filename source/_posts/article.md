---
title: 终于开始写博客啦！
date: 2020-11-15 18:41:26
tags: 其他
categories: 哔哔哔
---

{% asset_img 1.jpg  %}

> 小记：follow('7d651d09-69ef-41cb-a761-08d523685c8c')

> 终于开始写博客啦！

纯粹是想做个总结的技术备忘录，主要是方便自己查找，毕竟CS的东西这么多，还是需要有个地方记录一下的。

包含的内容主要也是看学习的进度，跟技术相关的应该都会记录下来。



## 如何使用Hexo

首先想记录一下如何使用Hexo来搭建博客的，毕竟现在我还是一头雾水，尽量尝试理清一下吧。



## 文章头设置

为了新建文章的时候可以偷懒一下，可以把`/scaffolds/post.md` 修改为以下代码：

```
--- title: {{ title }} 
date: {{ date }} 
top: false 
cover: false 
password: 
toc: true 
mathjax: true 
summary: 
tags: categories: 
---
```

官方文档对文章头变量的解释：https://github.com/blinkfox/hexo-theme-matery/blob/develop/README_CN.md

以及变量部分：https://hexo.io/zh-cn/docs/variables

## 添加页面

添加自已想要的页面，常用的有：

- 404
- “关于”页面增加简历
- 。。。



## 添加动漫人物

```
npm install --save hexo-helper-live2d
npm install live2d-widget-model-shizuku
```

然后在根目录配置文件中添加：

```
live2d: enable: true scriptFrom: local pluginRootPath: live2dw/ pluginJsPath: lib/ pluginModelPath: assets/ tagMode: false log: false model: use: live2d-widget-model-shizuku display: position: right width: 150 height: 300 mobile: show: true react: opacity: 0.7
```



## 图片添加水印



## 添加网易云音乐BGM



## 添加评论插件



## 添加百度和谷歌统计代码



## 修复代码块行号不显示bug



## SEO优化



## 添加雪花特效



## 动态标签栏



## 添加emoji表情支持



## 添加RSS订阅支持



## 添加在线聊天功能



## 修改社交链接

https://easyhexo.com/2-Theme-use-and-config/2-14-hexo-theme-matery/#%E9%85%8D%E7%BD%AE

示例：

```
<% if (theme.socialLink.github) { %>
    <a href="https://github.com/Lyle-Lyle" class="tooltipped" target="_blank" data-tooltip="访问我的GitHub" data-position="top" data-delay="50">
        <i class="fab fa-github"></i>
    </a>
<% } %>

<% if (theme.socialLink.qq) { %>
    <a href="tencent://AddContact/?fromId=50&fromSubId=1&subcmd=all&uin=1728559437 %>" class="tooltipped" target="_blank" data-tooltip="QQ联系我: <%= theme.socialLink.qq %>" data-position="top" data-delay="50">
        <i class="fab fa-qq"></i>
    </a>
<% } %>
```





### 写作

使用一下命令来创建一篇新文章

```
$ hexo new [layout] <title>
```

#### 资源引用

写个博客，有时候会想添加个图片或者其他形式的资源等等。有以下两种方式进行解决：

1. 使用绝对路径引用资源，在 Web 世界中就是资源的 URL
2. 使用相对路径引用资源

对于使用相对路径引用资源的，我们可以使用 Hexo 提供的**资源文件夹**功能。

使用文本编辑器打开站点根目录下的 `_ config.yml` 文件，将 `post_asset_folder` 值设置为 `true`。

修改之后会开启 Hexo 的文章资源文件管理功能。Hexo 将会在我们每一次通过 `hexo new <title>` 命令创建新文章时自动创建一个同名文件夹，于是我们便可以将文章所引用的相关资源放到这个同名文件夹下，然后通过相对路径引用。例如，你把一个 `example.jpg` 图片放在了这个同名文件夹中，使用相对路径的常规 markdown 语法 `![](./example.jpg)`即可访问 。



### 网站发布

首先执行下列命令生成相应的静态网页，生成的静态网页以及相关资源都会在`public`目录下

```
$ hexo generate
```

#### 使用hexo-server调试网站

hexo-server模块的主要命令如下，输入以下命令以启动服务器，您的网站会在 `http://localhost:4000` 下启动。在服务器启动期间，Hexo 会监视文件变动并自动更新，您无须重启服务器。

```
$ hexo server
```

如果您想要更改端口，或是在执行时遇到了 `EADDRINUSE` 错误，可以在执行时使用 `-p` 选项指定其他端口，如下：

```
$ hexo server -p 5000
```



#### 清除缓存文件

为了避免不必要的错误，在生成静态文件前，强烈建议先运行以下命令：

```
$ hexo clean
```



### 部署到Git上

```
$ hexo d
```







## 备份博客源文件

机制是这样的，由于`hexo d`上传部署到github的其实是hexo编译后的文件，是用来生成网页的，不包含源文件。

也就是上传的是在本地目录里自动生成的`.deploy_git`里面。

其他文件 ，包括我们写在source 里面的，和配置文件，主题文件，都没有上传到github





# 排错

不能直接拷贝之前的md文件，会缺少_config.yml文件自动在hexo n生成出来的md文件中的部分内容