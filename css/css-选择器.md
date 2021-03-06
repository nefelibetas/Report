#### 选择器

选择器分为**基础选择器**和**复合选择器**

![image-20220111120139766](D:\报告\Report\pic\\image-20220111120139766.png) 

##### 基础选择器

![image-20220111134342338](D:\报告\Report\pic\\image-20220111134342338.png) 

![image-20220111120400824](D:\报告\Report\pic\\image-20220111120400824.png) 

###### 标签选择器

选取对象是html标签名

语法：![image-20220111120730681](D:\报告\Report\pic\\image-20220111120730681.png)  

标签选择器只能全选此类标签，不太方便；

###### 类选择器

可以实现单独选择某个标签的选择器

![image-20220111121112771](D:\报告\Report\pic\\image-20220111121112771.png) 

语法：![image-20220111121205960](D:\报告\Report\pic\\image-20220111121205960.png)

 调用：![image-20220111121253703](D:\报告\Report\pic\\image-20220111121253703.png) 

定义样式用  **.** 调用时再标签后带class=""调用样式即可，如同结构体（类名自定义），此外，**不能占用保留字** 

**多类名：** 同时使用多个类选择器，方式 ![image-20220111132734887](D:\报告\Report\pic\\image-20220111132734887.png) ，两个不同的类之间加入空格即可。（模块化程序设计)

###### id选择器

可以指定特有id的html元素指定特定的样式

![image-20220111133449521](D:\报告\Report\pic\\image-20220111133449521.png) 

 语法：![image-20220111133526210](D:\报告\Report\pic\\image-20220111133526210.png) 

**id选择器只能调用一次** 

![image-20220111133920515](D:\报告\Report\pic\\image-20220111133920515.png) 



###### 通配符选择器

**用来全选标签**

![image-20220111134117953](D:\报告\Report\pic\\image-20220111134117953.png) 

语法：![image-20220111134144866](D:\报告\Report\pic\\image-20220111134144866.png)  无需调用，直接适配所有

#### 复合选择器

![image-20220114135851135](D:\报告\Report\pic\/image-20220114135851135.png) 

![image-20220114150715864](D:\报告\Report\pic\/image-20220114150715864.png) 

##### 后代选择器

又称包含选择器，可以选择父元素内的子集。

写法：外层写在外，内层写在后，空格隔开。![image-20220114140144048](D:\报告\Report\pic\/image-20220114140144048.png) ，此效果为把 ol 内的 li 改颜色

![image-20220114140843113](D:\报告\Report\pic\/image-20220114140843113.png) 语法如上

如果出现多层后代（如dl' dt dd），就一层层套娃即可；

 ![image-20220114141249293](D:\报告\Report\pic\/image-20220114141249293.png)  ![image-20220114141216857](D:\报告\Report\pic\/image-20220114141216857.png)  元素一二不受限制，可以是基础选择器。

![image-20220114141540872](D:\报告\Report\pic\/image-20220114141540872.png) 

![image-20220114142314167](D:\报告\Report\pic\/image-20220114142314167.png) 



##### 子选择器

只能选择作为最近的子元素；

语法： ![image-20220114141757542](D:\报告\Report\pic\/image-20220114141757542.png) 

例如：![image-20220114141855197](D:\报告\Report\pic\/image-20220114141855197.png) 

![image-20220114142435804](D:\报告\Report\pic\/image-20220114142435804.png) 



##### 并集选择器

用来选择多组标签，同时定义样式。使用情况：标签不同，但样式要求一致时方便声明

语法![image-20220114143054549](D:\报告\Report\pic\/image-20220114143054549.png) ，注：英文逗号；

![image-20220114143015477](D:\报告\Report\pic\/image-20220114143015477.png) 

任何选择器都能被选择：![image-20220114143301770](D:\报告\Report\pic\/image-20220114143301770.png) 究极套娃；

##### 伪类选择器

###### 链接伪类

元素1 ：元素2![image-20220115151902003](D:\报告\Report\pic\/image-20220115151902003.png) 

元素1和元素2可以是别的选择器

用于想某些选择器添加特殊效果，例：链接加上选中变色的效果

![image-20220114144818729](D:\报告\Report\pic\/image-20220114144818729.png) 

写法：

a : link![image-20220114144933188](D:\报告\Report\pic\/image-20220114144933188.png) 没点过的链接黑色

a :  visited ![image-20220114145054850](D:\报告\Report\pic\/image-20220114145054850.png)访问过的链接边橙色

a : hover ![image-20220114145158482](D:\报告\Report\pic\/image-20220114145158482.png) 鼠标经过的链接变天蓝

a : acitve   ![image-20220114145421410](D:\报告\Report\pic\/image-20220114145421410.png) 鼠标按下未松开时变色

以上除开 **颜色操作** 外，也能进行其他操作。

注：1.必须按照顺序写 2.链接需要单独指定样式

实际开发写法：![image-20220114150030216](D:\报告\Report\pic\/image-20220114150030216.png)  

###### 聚焦伪类

:focus

一般针对input类

![image-20220114150533238](D:\报告\Report\pic\/image-20220114150533238.png) 被选取中输入框时，背景变颜色。