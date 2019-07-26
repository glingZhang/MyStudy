## CSS的position属性的用法和区别

position的四个属性值：
* static
* absolute
* fixed
* relative

主要从relative和absolute来讲述
1. 外面的div没设置position，里面的div设置relative
~~~
<div style="width: 1000px;position: absolute;margin: 10px 10px;left: 100px;">
    <div style="height: 100px;background-color: red;">box1</div>
    <div style="height: 100px;background-color: yellowgreen;position: absolute;top: 50px;left: 50px;">box2</div>
    <div style="height: 100px;background-color: blue;">box3</div>
</div>
~~~
这种情况，外层div相对于body绝对定位，里层div相对于外层div绝对定位，脱离文档流，box3会往上移，此时，box3的宽度为文字的宽度，


