## 边距重叠
>原文链接：https://segmentfault.com/a/1190000012265930
## 父子元素边界重叠
~~~
<style>
    .parent {
        background: #E7A1C5;
    }
    .parent .child {
        background: #C8CDF5;
        height: 100px;
        margin-top: 10px;
    }
</style>
<section class="parent">
    <article class="child"></article>
</section>
~~~
为期待的效果：

在这里父元素的高度不是110px，而是100px，在这里发生了高度坍塌。原因是如果块元素的 margin-top 与它的第一个子元素的margin-top 之间
没有 border、padding、inline content、 clearance 来分隔，或者块元素的 margin-bottom 与它的最后一个子元素的margin-bottom 之间
没有 border、padding、inline content、height、min-height、 max-height 分隔，那么外边距会塌陷。子元素多余的外边距会被父元素的外
边距截断。

## 兄弟边界重叠
~~~
<style>
    #margin {
        background: #E7A1C5;
        overflow: hidden;
        width: 300px;
    }
    #margin>p {
        background: #C8CDF5;
        margin: 20px auto 30px;
    }
</style>
<section id="margin">
    <p>1</p>
    <p>2</p>
    <p>3</p>
</section>
~~~

可以看到1和2,2和3之间的间距不是50px，发生了边距重叠是取了它们之间的最大值30px。

## BFC原理
解决上述问题的其中一个办法就是创建BFC。BFC的全称为Block Formatting Context，即块级格式化上下文。一个BFC有如下特性：

* 处于同一个BFC中的元素相互影响，可能会发生margin collapse；
* BFC在页面上是一个独立的容器，容器里面的子元素不会影响到外面的元素，反之亦然；
* 计算BFC的高度时，考虑BFC所包含的所有元素，包括浮动元素也参与计算；
* 浮动盒的区域不会叠加到BFC上；

## 创建BFC
创建BFC的方法如下：

* 浮动（float的值不为none）；
* 绝对定位元素（position的值为absolute或fixed）；
* 行内块（display为inline-block）
* 表格单元（display为table、table-cell、table-caption等HTML表格相关属性）；
* 弹性盒（display为flex或inline-flex）；
* overflow不为visible；
