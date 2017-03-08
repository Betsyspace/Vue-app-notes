# Vue-app-notes
开发饿了么项目的总结

####1、垂直居中布局
```
<li>
   <span>
     单人精彩套餐
   </span>
</li>
- 如果想让span子元素在li元素中垂直居中
- 样式设置：
li{ display:table; }
span{ display:table-cell;vertical-align:middle; }
```
####2、flex布局
```
<div class="wrapper">
	<div class="icon"></div>
	<div class="text"></div>
</div>
-左边栏固定宽度,右边自适应
-样式设置
.wrapper{ display:flex; }
.icon{ flex: 0 0 80px; width:80px; }
.text{ flex: 1 }
```

####3、移动端1px像素边框
```
-scss写法
第一步：
@mixin border1px($color){
  position: relative;
  &:after{
    display: block;
    position: absolute;
    left: 0;
    bottom: 0;
    width:100%;
    border-top: 1px solid $color;
    content:' ';
  }
}
第二步：媒体查询设置border-1px样式
@media (-webkit-device-pixel-ratio: 1.5),(min-device-aspect-ratio: 3/2){
  .border-1px{
    &::after{
      -webkit-transform: scaleY(0.7);
      transform: scaleY(0.7);
    }
  }
}

@media (-webkit-device-pixel-ratio: 2),(min-device-aspect-ratio: 4/2){
  .border-1px{
    &::after{
      -webkit-transform: scaleY(0.5);
      transform: scaleY(0.5);
    }
  }
}

-调用 在需要加边框的元素调用mixin，同时加上border-1px的class
@include border1px(rgb(0,0,0));
```

####4、在某个情况下添加某个样式highlight
```
<div :class="{ 'highlight':totalCount>0 }"></div>
- 写法
- :class = "{ '样式' : 条件 }"
```

####5、所有需要即时改变的数据都是写在computed计算属性当中

####6、访问DOM元素用v-el，通过this.$els访问

####7、访问子组件用v-ref，通过this.$refs访问

####8、点击事件防止事件冒泡写法：@click.stop.prevent="xxx"

####9、图片和文字对齐方式 分别设置display:inline-block;vertical-align:top;
