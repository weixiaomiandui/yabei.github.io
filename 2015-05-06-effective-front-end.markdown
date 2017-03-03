对于如何编写高质量的HTML和CSS代码，已经有大牛nid进行了归纳总结，下面是在Bootstrap中文网上贴出来的翻译文章：编写灵活、稳定、高质量的 HTML 和 CSS 代码的规范，挺不错的。

关于编写高质量的javascript代码，找了一本电子书《Effective Javascript》，里面提出了68个有效的方法提高javascript的质量代码。可以在我的百度云盘--前端资源2015找到。

另外最近兴起的Gulp:新一代前端构建利器，gulp中文网，可以很好地用自动化构造工具增强我们的前端开发流程。自己写了一套gulp.js模板，就以这个例子来简单说说。

gulp.js的核心部分应该是在gulpfile.js文件，我自己的模板的这个文件在这个位置。

var gulp = require('gulp');
var jshint = require('gulp-jshint');
var less = require('gulp-less');
var concat = require('gulp-concat');
var uglify = require('gulp-uglify');
var rename = require('gulp-rename');
var minifycss = require('gulp-minify-css');
var lessPluginAutoPrefix = require('less-plugin-autoprefix');
// var imagemin = require('gulp-imagemin');
// var pngquant = require('imagemin-pngquant');
gulp是基于node.js的，开头部分我们引入了N个模块。主要是gulp本身，检测javascript语法是否有错误的jshint模块，压缩javascript文件的uglify模块，CSS预处理语言LESS模块，CSS浏览器兼容前缀自动补充的autoprefix模块，压缩CSS文件的minify-css模块，文件的合并模块concat以及文件的重命名模块rename,最后还有图片的压缩模块imagemin。可以说基本把前端开发的 js / css / image 压缩合并工作都包括进去了。

所以在我们的 index.html 文件中，可以看到我们只是简单地引入了一个all.min.css样式文件，一个all.min.js脚本文件，因为gulp已经自动化地帮我们把所有的css和js文件压缩和合并起来了。

另外在这里提一下 HTML5 Boilerplate，这个网址下可以看到这样的介绍：“HTML5 Boilerplate 帮你构建 快速, 健壮, 并且 适应力强 的web app或网站。这个小小的源码包集合了100位开发者的经验，你可以将这些经验运用在你的项目中。”更多的细节可以自己看看。我给出的gulp.js的基本模板也是根据这个HTML5 Boilerplate改装的，可以在我的mylib中下载。

恼人的命名冲突以及烦琐的文件依赖英国是前端模块化出现的最主要原因吧。使用sea.js(当然也可以是require.js啦)可以很好地解决这方面的问题。前端模块化开发的价值很详细地说到了这方面的问题，sea.js对于团队慢慢的壮大，前端代码的管理确实很重要。sea.js初尝试是我之前写的一篇sea.js学习文章，通过看了不少教程填了一些坑总结出来的。
