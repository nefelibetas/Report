#### 高级技巧

##### 精灵图 CSS sprites

使用目的：减少服务器收发次数，提高页面加载

主要针对背景图片使用，利用手法：![image-20220127153210386](D:\报告\Report\pic\\image-20220127153210386.png) 



##### 字体图标iconfont

1.灵活性    2.轻量级    3.兼容好   但一般只能做比较简单的小图标

字体库

 ![image-20220127154915959](D:\报告\Report\pic\\image-20220127154915959.png)

![image-20220127154929206](D:\报告\Report\pic\\image-20220127154929206.png) 

使用：下载后，引入自带的.css文件并在给出样式文档中复制对应字符，修改对应代码即可使用

修改：![image-20220127160139256](D:\报告\Report\pic\\image-20220127160139256.png)

##### CSS三角

做法： 宽高为0 ，设定边框即可

![image-20220127160719297](D:\报告\Report\pic\\image-20220127160719297.png)  ![image-20220127160729480](D:\报告\Report\pic\\image-20220127160729480.png) 

 简化写法：![image-20220127160838896](D:\报告\Report\pic\\image-20220127160838896.png) 红框内代码保证兼容

直角三角形

 ![image-20220127182806872](D:\报告\Report\pic\\image-20220127182806872.png) 



##### 用户界面样式

1.更改用户鼠标样式

语法：![image-20220127162628693](D:\报告\Report\pic\\image-20220127162628693.png) li用来做示范，可以放在别的样式内

![image-20220127162644121](D:\报告\Report\pic\\image-20220127162644121.png) 

2.表单轮廓

轮廓线ouline![image-20220127162953741](D:\报告\Report\pic\\image-20220127162953741.png) 

语法：![image-20220127163011039](D:\报告\Report\pic\\image-20220127163011039.png)

 3.防止表单域拖拽

防拖拽resize![image-20220127163426660](D:\报告\Report\pic\\image-20220127163426660.png)



##### vertical-align属性应用

![image-20220127163735599](D:\报告\Report\pic\\image-20220127163735599.png) 

语法![image-20220127163911709](D:\报告\Report\pic\\image-20220127163911709.png) 

![image-20220127163927078](D:\报告\Report\pic\\image-20220127163927078.png) 

![image-20220127164031319](D:\报告\Report\pic\\image-20220127164031319.png) 

清除图篇下方空隙：

![image-20220127165145958](D:\报告\Report\pic\\image-20220127165145958.png) 或者 ![image-20220127170838697](D:\报告\Report\pic\\image-20220127170838697.png) 



##### 溢出变省略

###### 单行文本

![image-20220127171054065](D:\报告\Report\pic\\image-20220127171054065.png) 

###### 多行文本

缺陷![image-20220127171421728](D:\报告\Report\pic\\image-20220127171421728.png) 

![image-20220127172459679](D:\报告\Report\pic\\image-20220127172459679.png) 

#### 布局技巧

##### margin负值

![image-20220127173346502](D:\报告\Report\pic\\image-20220127173346502.png) 

margin-left为负值时表示向左

解决盒子边框变色不全

![image-20220127174454916](D:\报告\Report\pic\\image-20220127174454916.png) 



##### CSS初始化

常用初始化代码：

**清除默认边界**

~~~css
{
     margin: 0;padding: 0;
}
~~~



**清除li前的点** 

~~~css
li 
{
    list-style: none;
}
~~~



**border为了照顾低版本浏览器**

**取消图片底侧有空白**

~~~css
 img 
{
    border: 0;
    vertical-align: middle;
}
~~~



**将鼠标变成手型** 

~~~css
button
{
cursor: pointer；
}
~~~



**修饰链接** 

~~~CSS
a 
{
    color: #666;
    text-decoration: none;
}
~~~



**改变鼠标经过时的颜色** 

~~~css
a:hover
{
    color: ;
}
~~~



**隐藏** 

~~~CSS
.hide,.none 
{
    display: none;
}
~~~



**清除浮动** 

~~~CSS
.clearfix:after 
{
    visibility: hidden;
    clear: both;
    display:block;content:".";
    height: 0;
}

.clearfix 
{
    *zoom: 1;
}
~~~



#### 规范

首页名称定位index.html 样式定为 style.css

##### 书写顺序

![image-20220120225132231](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220120225132231.png) 

例：![image-20220120225424544](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220120225424544.png) 

位置、自身、文本、其他 

##### 布局思路

![image-20220120231026785](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220120231026785.png) 

![image-20220120232338460](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220120232338460.png)  

