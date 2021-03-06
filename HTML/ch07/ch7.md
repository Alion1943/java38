# 标准文档流和浮动

  html标签按照其默认的样式在浏览器中按从上至下，从左往右的顺序依次渲染html元素，最终形成我们看到的网页效果。

  - 块元素

  ```
    一个块元素会独占网页的一行显示。
    块元素能够设置其宽度和高度；能够设置其盒子模型；
  ```
  - 内联元素
  
  ```
    内联元素在网页中默认不会换行显示，多个内联元素默认按水平方向从左往右一次排列。直到容器宽度不足容纳新的内联元素时才会换行显示。
    内联元素不能够手动指定其宽度和高度；内联元素的宽度和高度默认由其内容撑起来。
    内联元素的宽度和高度默认为auto * auto
  ```
  学习布局的目的，就是为了改变某些标签的样式、在标准文档流中的显示方式从而达到我们的效果。

## 实现块元素和内联元素的切换

  通过`display`属性实现；

```css
    /*display属性具有的值*/
    display:block;  /*块元素的默认值*/
    display:inlie;  /*内联元素的默认值*/
    display:inline-block;  /*同时具备块元素和内联元素的特点*/
    display:none;   /*隐藏元素*/

    display:table;  /*相当于表格布局，表格中具有行和列*/
    display:item;
```

## 浮动

  在css3的flex布局出现之前，通常通过浮动对网页进行布局。浮动的元素会<font color="red">脱离标准文档流</font>。通过设置方向，可以指定浮动的方向。
  浮动的使用的场景非常的丰富，因为很多的网页中都需要对列表进行横向排列称为导航。
  浮动的元素会脱离文档流，因此某些从父容器中继承到的样式就不能够有效。所以通常情况下，浮动的元素需要单独设置其宽度和高度。

```css
    float:left;  /*元素脱离文档流，并靠左浮动*/
    float:right; /*元素脱离文档流，并靠右浮动*/
```

## 清除浮动

    浮动的元素脱离了文档流，因此父级容器的高度会出现塌陷的问题（高度为0）。
    通过清除浮动就能够解决浮动之后的元素顶着显示的问题。

```css
    clear:left;  /*清除左浮动*/
    clear:right; /*清除右浮动*/
    clear:both;  /*清除左右两侧的浮动*/
```

## 溢出处理

    当唯一个为文本的容器设置了一个固定的宽高以后，期内的文本如果过多，默认显示会超出容器。
    overflow相当于是一种补救措施。为了不影响页面中其他部分的元素，所以只能够让溢出部分隐藏起来。

```css
    overflow:visible;  /*默认值，默认不做处理*/
    overflow:hidden;  /*溢出部分隐藏显示*/
    overflow:scroll; /*加滚动条*/
    overflow:auto;  /*没有溢出，则没有滚动条，溢出则加上滚动条*/
```

    溢出处理overflow能够对布局做补救措施，文本也有专用的一个样式属性，可以实现更加直观的效果。

```css
    /*控制文本，溢出后隐藏，并显示省略号*/
    overflow: hidden;
    white-space: nowrap;/*文本换行方式，超出文本不换行*/
    text-overflow: ellipsis;/*超出的文本显示为省略号*/
```