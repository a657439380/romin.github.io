---
layout: post
author: cloud.eve
title: "往事如烟"
description: "利用Github搭建博客后,我写的第一篇博客"
catalog:    true
cover: "zzz"
tags:	Jekyll
---
这篇博文用于记录，自己在修改博客时具体的修改记录，如颜色设置、联系方式配置等信息，以便日后查看。

### 2016/07/02
不知不觉，已经放弃上一个博客主题好久了，现在福生还在使用我的主题[sunfusheng](http://sunfusheng.com/)

今天，终于有时间可以搞下博客了，这段时间都太忙了。


### 2016/03/27
项目主颜色设置在 less 目录下的 variables.less

### 2016/03/26
今天已经修改自己博客的主题为另一个主题了

### 2016/02/29
隐藏了post 页面的 tag、category 点击相应，因为 jekyll archive 不支持 Github Page
使用了新的代码高亮样式 减小了 padding 值

### 2016/02/26
指定引用图片的宽度大小，可通过如下方式

    <img src="/assets/over_draw_color_2.png" style="width: 50%;margin: auto;"><br>

###2016/01/20

修改代码块的主题样式在 _include/head.html 文件中修改

可以再 [bootcdn](http://www.bootcdn.cn/highlight.js/)下载

        <!-- thanks to http://www.bootcdn.cn/lightbox2/      -->
        <!-- thanks to http://www.bootcdn.cn/highlight.js/   -->
        <!-- thanks to https://highlightjs.org/static/demo/  -->
        <link  rel="stylesheet" href="//cdn.bootcss.com/highlight.js/8.5/styles/androidstudio.min.css">
        <link rel="stylesheet" href="//cdn.bootcss.com/lightbox2/2.8.2/css/lightbox.css">

修改代码块的padding font  在 _sass/_layout.scss

        pre code.hljs {
        	font-size: modular-scale(0);
        	padding: 1.5em;
        }


###2016/01/12

修改底部四个按钮大小 在 footer.html

    .fa-lg{
            font-size: 1.5em;
        }

设置顶部 Title(咕咚)的高度

      .logo {
        float: left;
        height: 4em;
        border:0px solid #000;
        padding-top: 0.6em;
        @include media ($tablet) {
        	padding-left: $em-base;
        }

设置底部的按分类查看为隐藏

      <p style="display:none;">
        <a href="{{ site.baseurl }}posts">View All Posts by Category</a>
      </p>

### 2015/12/5
为博文增加了一个开关，如下所示

    ---
    layout: post
    author: 咕咚
    title: "在Android5.0以上设备实现过度动画"
    description: ""
    categories: Technology
    publish: false
    tags: Android Animation
    ---

只要设置 publish 为 false ，那么这篇博文将不会出现在主页列表，不设置默认表示文章处于发布状态

### 2015/10/27

修改了默认的博客头部背景颜色设置。

在写博客时，在博客一开始指定cover时，现在可以有四种可选项了，

      cover: "assets/1024_programer.png"
      cover: "#f8f8f8"
      cover: "zzz"
      不设置

四种设置分别对应下面的四种表现

* 在博文中设置cover属性为assert下面的图片，必须是assets下面
此时文章头部背景将会是一张大图

        style="background-image: url(/////);"

* 在博文中设置cover属性为以#开头的颜色值
此时文章头部背景将会是纯色

        style="background-color:#xxxxxx;"

* 在博文中设置cover属性为"zzz"
此时文章头部背景将会是主题指色，这个颜色在config中指定

        theme_color: "#607D8B"

* 在博文中不设置cover属性
此时文章头部将不会显示任何大背景色，只有一个分割线

### 2015/10/25

当设置博客北京的conver属性后，如果没有设置图片，则会显示一个纯色的背景，这个纯色的背景的设置具体在/sass/layout.scss下面

      .scrim {
        padding: 3em 1em;
        &.has-cover {
          background-color: $action-color;
          padding: 6em 1em !important;
          @include media($tablet) {
            padding: 9em 1em !important;
          }
        }
      }

$action-color在/sass/base/variables.scss下面

    // Font Colors
    $base-background-color: #fff;
    $base-font-color: $dark-gray;
    $action-color: $blue;
    $highlight-color: tint($action-color, 33%);

真心佩服作者这种清晰明了的设置方案。

经验证 上面的方式有问题，background-color 必须为半透明颜色，还是改回来，换个颜色就行！
