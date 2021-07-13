

*This doc is a learning record.*
**Author:Pan** 
*Create Time 2021/7/6*

---



#### Day1  July.6

##### HTML头部：

meta:基本元数据，例如：默认链接 编码格式 文档作者

```<meta name="author" content="CHOKE">```
title：标题
link:内外资源关系
style:渲染 装饰页面

##### HTML超链接：(link_test.html)

基本格式：  ```<a>连接文本</a>```

设置一个链接指向百度的超链接：```<a href="http://www.baidu.com">点击链接</a>```

要设置超链接格式，在其中加入<kbd>"target="</kbd>

其中：_blank:新窗口打开  _top:跳出框架 _self：本框架 _parent:父框架
注：target的格式和href后面的url，如果未声明（href=""   target缺失）则缺省值为head元素中meta已设定的值

##### CSS：(style_test.html)

在head元素内 预设各种文本风格
例如 body的背景元素 body {background-color:aqua;}
     段落，各级标题的颜色
     p {color:blue;}
     h1{color:blueviolet;}
     设置一个蓝色 居右 并且与右侧相距20pix单位距离的段落：
```html
 <p style="color:blue; text-align:right;margin-right: 20px;">这是一个居右段落</p>
```



​     设置一个红色 居中的段落
     <p style="color:red; text-align:center;">这是一个居中段落</p>

​     style中设置文本大小：<kbd>font-size="20px"</kbd>（设置文本字体大小为20px)

---



#### Day2 July.7

##### HTML图片：(img_test.html)

插入图片的格式为 ```<img src="" alt="" width="" height=""> ```

src:图片源，可以为文件名，也可以为url
alt:图片说明，若网页不能加载，则会显示此文本，对于纯文本浏览器很重要 
width，height:图片的大小，单位为像素(px)

设置图片的浮动(位置):使用CSS的float 例如： 

``` html
 <p style="color: blue;">
      <img src="wallpaper.png" style="float:right" width="64" height="64">图片位于文本后方 
 </p>
<!--以上的代码 把wallpaper.jpg放在了文本的右侧-->
<!-- wallpaper的pid:87215848-->
```

设置图像链接，使点击图片成为一个超链接：在```<a>```和 ```</a>```的中间插入超链接 例如：

``` html
<p>有边框的创建图片链接(点击进入百度):
     <a href="http://www.baidu.com">
          <img border="10" src="pic/pan.jpg" alt="百度官网" width="32" height="32">
     </a></p> 
<p>无边框的图片链接（点击进入新浪）:
     <a href="http://www.sina.com.cn">
     <img border="0" src="pic/pan.jpg" alt="新浪官网" width="32" height="32">
     </a></p> 
```

以上的代码，生成了两个超链接，超链接文本为插入的图片(pan.jpg)，在插入图片时可以通过设置border来改变图片是否有边框
border为10：有边框   border为0：无边框

创建图像映射：
把图片分为不同的部分，每一部分为不同的超链接 例如：

``` html
<img src="planets.gif" width="145" height="126" alt="Planets" usemap="#planetmap">
```

创建区域：

``` html
  <area shape="rect" coords="0,0,82,126" alt="Sun" href="https://www.runoob.com/images/sun.gif">
//创建一个矩形(rect)的区域，coords后面的数字代表对角线端点(左上和右下)的作标，并且链接到指定的url
     <area shape="circle" coords="90,58,3" alt="Mercury" href="https://www.runoob.com/try/demo_source/merglobe.gif">
     <area shape="circle" coords="124,58,8" alt="Venus" href="https://www.runoob.com/images/venglobe.gif">
//创建两个圆形(circle)的区域，coords后面的数字代表圆形的圆心和坐标(单位为像素px)，并且链接到指定的url
</map>
```

以上的代码，在插入的图片里创建了三个区域，分别链接到不同url

##### HTML表格：（table_test.html)

创建表格标准格式:

``` html
      <tr>
          <th>...</th>
     </tr>
     <tr>
          <td>...<td>
     </tr>
</table>
```

其中:border可以缺省，表示表格无边框，若border为1，则有边框，如果大于1，边框会变粗
tr:表格的行  th：表头  td:表格内元素

---



#### Day3 July.8

##### HTML表格：

表格标题的添加：在行内容（<tr>）前加入<caption>标题</caption>
跨行，跨列的单元格：在表头或者普通内容标签后加入 colspan(列)或者rowspan(行) 例如：<th rowspan="2">表头1</th> //跨两列的表头
单元格边距：单元格边框到单元格内文本的空白距离大小  例如```<table border="1" cellpadding="10">```

单元格间距：不同单元格之间的距离 例如```<table border="1" cellspacing="10">```
表格是可以嵌套的，单元格的内容可以为其他表格，也可以为列表，段落等等

(以下的缩写笔记原文来自[HTML 列表 | 菜鸟教程 (runoob.com)](https://www.runoob.com/html/html-lists.html))

HTML列表：(list_test.html)
ul是unordered lists的缩写 (无序列表)
li是list item的缩写 （列表项目）
ol是ordered lists的缩写（有序列表）
dl是definition lists的英文缩写 (自定义列表)
dt是definition term的缩写 (自定义列表组)
dd是definition description的缩写（自定义列表描述）
nl是navigation lists的英文缩写 （导航列表）
tr是table row的缩写 （表格中的一行）
th是table header cell的缩写 （表格中的表头）
td是table data cell的缩写 （表格中的一个单元格)

列表分为：有序列表 无序列表 自定义列表
创建有序列表：    创建无序列表：     创建自定义列表

``` html
<ol>               <ul>            <dl>
<li> </li>       <li> </li>       <dt> </dt>  <dd> </dd>
</ol>              </ul>           </dl>
```

li:列表内容  dt:自定义内容 dd:描述
要改变有序列表的排序起点： ```<ol start="100"> ```  以100作为第一个数字开始排序
要改变有序列表的排序基准：```<ol type="A">```   以大写字母为基准排序，若type值为“a” 
                                      //则为小写字母  若type为I/I 则为大/小写罗马数字
要改变无序列表每个数值之前的形状：```<ul style="list-style-type: square;">``` //通过更改style的值来改变形状，此处改为了正方形
列表是可以嵌套的，即列表内容可以为其他列表

#### Day4 July.9

##### HTML区块：(block_test.html)

用<kbd><div></kbd> 和<kbd><span></kbd>分区块：<kbd><div></kbd> 元素是块级元素，它可用于组合其他 HTML 元素的容器 
<kbd><span></kbd> 元素是内联元素，可用作文本的容器
用div分区实例：

``` html
<div id="header" style="background-color: aquamarine; height:100px;">页头</div>
            <div id="menu" style="background-color:greenyellow; height: 200px; width: 200px;float: left; ">
                <b>菜单</b><br>
                菜单内容1<br>
                菜单内容2<br>
                菜单内容3</div>
            <div id="content" style="background-color: brown; height: 200px; width:calc(100% - 200px);float:left">此处为内容</div>
            <div id="footer" style="background-color:aqua; text-align: center;">制作:pan</div>
</div>
```

最上方的container覆盖了以下所有分区 并且规定了默认的宽度（width）
格式用style 使用CSS改变样式、
```calc()```为CSS函数，返回值为大小 此处calc(100% - 200px)为"最大值-200px"(内容前方的"标题"部分宽度为200px),最大值在最上方的container已经规定
```clear:both ```   清除浮动值

---



#### Day5 July.10

##### HTML表单：

表单是一个包含表单元素的区域。
表单元素是允许用户在表单中输入内容
表单使用表单标签 <form> 来设置,例如：

``` html
<form>
     input content...
</form>
```

创建 一个可以输入姓名的文本域

``` html
<form>
姓:<input type="text" name="last name"><br>
名:<input type="text" name="first name">
</form>
```

type="text" 代标输入类型为文本
若type="password" 输入的类型则为密码 不会明文显示

选项的创建：

``` html
<!--单选-->
            <input type="radio" name="char" value="a">A选项<br>
            <input type="radio" name="char" value="b">B选项<br>
            <input type="radio" name="char" value="c">C选项
<!--多选-->
            <input type="checkbox" name="string" value="aa">AA选项<br>
            <input type="checkbox" name="string" value="bb">BB选项<br>
            <input type="checkbox" name="string" value="cc">CC选项<br>
</form>
```

要确定多个选项在一个系列，name属性的值必须一致
若单选项name不一致,达不到单选效果（选取一个时，另一个会被取消选择）

创建按钮： ``` <input type="button" action=" " value="按钮"> ```
创建下拉菜单:

``` html
<form action="">
      <select name="chars">
          <option value="a" >A</option>
          <option value="b" selected>B</option>   <!--"selected"表示默认选项-->
          <option value="c">C</option>
          <option value="d">D</option>
     </select>
</form>


```

创建文本框

``` html
 <textarea rows="10" cols="30">这是一个文本框</textarea>  <!--rows cols代标文本框行和列（大小）-->
```

创建带边框的表单：

``` html
<form action="">
     <fieldset>
          <legend>这是表单标题</legend>
               ID:<input type="text" name="id" size="10"><br>
               NAME:<input type="text" name="name" size="10">
     </fieldset>
</form>  
```

<kbd><fieldset></kbd>标签表示将表单内容的一部分打包，生成一组相关表单的字段
<kbd><legend></kbd>标签为 fieldset 里文本的标题

---



#### Day6 July.12

##### HTML框架：可以嵌入框架，以达到同一个浏览器窗口显示多个网页的功能

创建框架：```<iframe src="URL"></iframe>```
可以通过改变width,height的值来改变内嵌框架大小(单位可以为像素px，也可为百分比%)
例如：```<iframe src="style_test.html" frameborder="0" width="200px" height="200px" ></iframe>```
可以通过设置name值，来使超链接跳转的页面显示在框架中，例如：

``` html
<iframe src="style_test.html" name="myframe"  width="80%" height="80%"></iframe><br>
<a href="http://www.baidu.com" target="myframe">点击此处 内容显示在框架内</a>
```

以上的代码，由于超链接的target值和框架name值一致，点击跳转后会显示在框架中

##### HTML脚本：

创建格式：```<script>....</script>```
可插入JS等脚本
比如:

``` html
<script>
            document.write("<p> 测试 </p>");
     </script>
 <noscript>抱歉，你的浏览器不支持 JavaScript!</noscript>
```

``` html
<script>
            document.write("<p> 测试 </p>");
</script>
```

若浏览器不支持JS 则会以<kbd><noscript></kbd>标签内的内容代替
脚本改变页面内容：例如

``` html
<p id="change">JS脚本测试</p>
<script>
     function myfun1()
     {
          x=document.getElementById("change");//通过ID查找元素
          x.innerHTML="改变后的值";//改变元素内容
     }
<button type="button" onclick="myfun1()">点击</button><br>
<B>点击上方按钮可改变第二行文本的内容</B><br>
```





