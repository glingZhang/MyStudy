## sass安装以及环境配置
　　Sass 是一款强化 CSS 的辅助工具，它在 CSS 语法的基础上增加了变量 、嵌套 、混合 、导入 等高级功能，这些拓展令 CSS 更加强大与优雅。使用 Sass 以及 Sass 的样式库（如 Compass）有助于更好地组织管理样式文件，以及更高效地开发项目。sass是Ruby语言开发的一个用于动态编程css文件的框架,所以sass的运行依赖Ruby环境

#### sass和scss的区别
　　SCSS 是Sass 3 引入新的语法，其语法完全兼容 CSS3，并且继承了 Sass 的强大功能。主要的就是sass是靠缩进表示嵌套关系，scss是花括号

#### 1、安装sass
可以用gem也可以用npm安装，这里我用的gem安装的。    

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
更换镜像源，先移除镜像源    

```
$ gem sources --remove https://rubygems.org/ 
```    
再添加镜像源    

```
$ gem sources -a https://ruby.taobao.org/
或者    
$ gem sources -a http://gems.ruby-china.com/
```

#### 2、在webstorm里面配置开发环境
　　webstorm --> preferences--> tools--> File Watches 点击“+” 依次添加 Sass 和 Scss .一路点击“OK”就好了。



#### 3、安装gulp    
　　gulp 是一个前端自动构建工具，由于gulp是基于node.js开发的，所以你在使用gulp之前，必须要先安装node。gulp是基于Nodejs的自动任务运行器，基本流程就是先安装nodejs，通过nodejs的npm全局安装和项目安装gulp，其次在项目里安装所需要的gulp插件，然后新建gulp的配置文件gulpfile.js并写好配置信息（定义gulp任务）。    
##### ① 安装gulp：

```
$ npm install -g gulp
// 或者 ↓
$ sudo npm install gulp --unsafe-perm -g
```


##### ② 安装插件
　　在cmd项目目录下开始本地安装gulp各种插件，在这里找你需要的插件。以下四个是用得最多的。  
　　　　语法检查   （gulp-jshint）    
　　　　合并文件   （gulp-concat）    
　　　　压缩代码   （gulp-uglify）    
　　　　文件重命名   （gulp-rename）

　　例如：gulp-jshint，在cmd项目目录下输入:      
```  
$ npm install gulp-jshint --save-dev
```    
　　其他同理
##### ③ 本地项目安装gulp
　　全局安装完成之后，还需要在每个要使用的gulp项目中都单独安装一次，把目录切换到项目文件夹中，使用--save-dev，将通知计算机在package.json中添加依赖。    
```
$ npm install --save-dev  gulp
$ gulp -v
```

　　安装gulp-sass（把sass转换成css）:    
```
$ npm install gulp-sass  
```

　　新建一个gulpfile.js    
gulpfile.js： 
   

```
// 导入工具包，require('node_modules里对应模块'
var gulp = require('gulp');    
var sass = require('gulp-sass');
// gulp.task定义一个testsass任务
gulp.task('demo', function () {
	
	// gulp.src该任务针对的文件
    gulp.src('sass/demo.scss') 
    
    	// 该任务调用的模块
        .pipe(sass()) 
        
        // gulp.dest将会在src/css下生成index.css
        .pipe(gulp.dest('css')) 
});
//定义默认任务 elseTask为其他任务，该示例没有定义elseTask任务
gulp.task('default',['demo']); 
```
　　生成package.json    
　　在项目目录下，输入命令生成package.json：
    
```
$ gulp init //这种是自定义初始化。
$ gulp init -y  //这种自动初始化。
```



#### 附：

gulp基本操作：
>https://www.cnblogs.com/thomaspha/p/5884230.html




