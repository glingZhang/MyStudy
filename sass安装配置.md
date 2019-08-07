## sass安装以及环境配置
sass是Ruby语言开发的一个用于动态编程css文件的框架 所以sass的运行依赖Ruby环境
#### 安装sass
```
$ sudo gem install sass
```
查看sass是否安装好了
```
$ sass -v
```
查看sass镜像源
```
$ gem sources -l
```
移除镜像源
```
gem sources --remove https://rubygems.org/ 
```
添加镜像源
```
gem sources -a http://gems.ruby-china.com/
```

#### sass和scss的区别
SCSS 是 Sass 3 引入新的语法，其语法完全兼容 CSS3，并且继承了 Sass 的强大功能。也就是说，任何标准的 CSS3 样式表都是具有相同语义的有效的 SCSS 文件


#### 配置开发环境
点击File Watches 点击“+” 依次添加 Compass Sass 和 Compass Scss .一路点击“OK”就好了。


由于gulp是基于node.js开发的，所以你在使用gulp之前，必须要先安装node
gulp是基于Nodejs的自动任务运行器，基本流程就是先安装nodejs，通过nodejs的npm全局安装和项目安装gulp，其次在项目里安装所需要的gulp插件，然后新建gulp的配置文件gulpfile.js并写好配置信息（定义gulp任务），最后通过命令提示符运行gulp（webstorm神器更简单）。

#### 安装gulp
```
sudo npm install gulp --unsafe-perm -g
```
接着在cmd项目目录下开始本地安装gulp各种插件，在这里找你需要的插件。有四个是用得最多的，必备的

　　　　1、语法检查   （gulp-jshint）

　　　　2、合并文件   （gulp-concat）

　　　　3、压缩代码   （gulp-uglify）

　　　　4、文件重命名   （gulp-rename）

　　就拿gulp-jshint举例吧，在cmd项目目录下输入

npm install gulp-jshint --save-dev




作为项目开发依赖安装。

            全局安装完成之后，还需要在每个要使用的gulp项目中都单独安装一次，把目录切换到项目文件夹中输入cmd，然后在命令行中执行：

                npm install --save-dev  gulp
