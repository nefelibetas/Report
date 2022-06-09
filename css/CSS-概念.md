####  CSS（层叠样式表）

标记语言

CSS作用：布局和美化网页，而html则是搭出大概布局。

##### 语法规范

![image-20220111114457676](D:\报告\Report\pic\\image-20220111114457676.png) 



css内容写到![image-20220111114619211](D:\报告\Report\pic\\image-20220111114619211.png) 中，例子![image-20220111115013463](D:\报告\Report\pic\\image-20220111115013463.png) h1标题变蓝，选择器后要带空格

#### CSS引入方式

按照书写位置（引入 的方式）的不同，CSS样式表分3类

1.行内样式表（行内式）

2.内部样式表（嵌入式）

3.外部样式表（链接式）

![image-20220111155828537](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111155828537.png) 

##### 内部样式表（嵌入式）

![image-20220111153107045](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111153107045.png) 

![image-20220111153418247](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111153418247.png) 

##### 行内样式表（行内式）

![image-20220111153534866](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111153534866.png) 

直接在标签内部写入style属性即可

![image-20220111153724627](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111153724627.png) **行内式引入**

##### 外部样式表（链接式）

![image-20220111153950995](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111153950995.png) 

彻底模块化设计....

步骤：

1.建立一个.css文件，在这个文件中写入css代码。![image-20220111155702015](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111155702015.png)（文件名自取)

2.在html页面中用link标签引入文件![image-20220111155652527](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220111155652527.png)  （href内跟入文件的路径)

#### 调试工具

![image-20220112155120622](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220112155120622.png) 

#### emmet语法

用来缩写，提高html和css代码编辑速度

![image-20220114134206406](C:/Users/nefilibata/AppData/Roaming/Typora/typora-user-images/image-20220114134206406.png) 

css方式同上，缩写取名称单词的第一个字母组合；

### CSS三大特性

##### 层叠性(就近采用)

若出现两个有相同属性的样式定义时，采用就近的属性样式定义![image-20220115152135278](D:\报告\Report\pic\/image-20220115152135278.png) 

**并不是全覆盖** 



##### 继承性(遵循继承权重)

子标签会继承父标签的某些样式，如：文本颜色和字号

![image-20220115152718068](D:\报告\Report\pic\/image-20220115152718068.png) 

###### 行高的继承

![image-20220115153046957](D:\报告\Report\pic\/image-20220115153046957.png) ![image-20220115153129446](D:\报告\Report\pic\/image-20220115153129446.png) div里继承了body的行高。

行高可以不写单位，不写时代表：行高当前文字大小的1.5倍

![image-20220115153424076](D:\报告\Report\pic\/image-20220115153424076.png) 

##### 优先级(按继承权重)

若选择器相同，则按叠层性。

若选择器不同，则优先级需判断选择器的权重

![image-20220115153845361](D:\报告\Report\pic\/image-20220115153845361.png) 

！important用法：![image-20220115154051963](D:\报告\Report\pic\/image-20220115154051963.png) 

权限比较：从左到右比较，相同则下一位，数值大的权限大

![image-20220115154715429](D:\报告\Report\pic\/image-20220115154715429.png) 

易错例子：![image-20220115154814875](D:\报告\Report\pic\/image-20220115154814875.png) p文字的颜色仍然为粉（**继承权重为0**) 

##### 权重叠加

复合选择器会有权重叠加

例：![image-20220115155345371](D:\报告\Report\pic\/image-20220115155345371.png) ![image-20220115155354708](D:\报告\Report\pic\/image-20220115155354708.png) 两段都让**li**的颜色变绿，在加上这条![image-20220115155707705](D:\报告\Report\pic\/image-20220115155707705.png) 

则让li里的文字边粉色

原因在于复合选择器权重有所叠加（ **ul + li 的权重**） （ **.nav + li 的权重**）

权重不进行进位

###### 练习

![image-20220115160123433](D:\报告\Report\pic\/image-20220115160123433.png) ![image-20220115160508346](D:\报告\Report\pic\/image-20220115160508346.png) 

继承权重为0，显示粉。      .nav li的权重高于 .pink 导致只加粗，未变色。