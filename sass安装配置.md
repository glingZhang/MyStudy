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
