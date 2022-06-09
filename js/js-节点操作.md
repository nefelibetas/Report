### 节点操作

#### 父节点

![image-20220505215000943](D:\报告\Report\pic\\image-20220505215000943.png) 

父节点：element.parentNode

parentNode得到的是离元素最近的父级节点，找不到则为空。

#### 子节点

![image-20220505215749703](D:\报告\Report\pic\\image-20220505215749703.png) 

![image-20220505220446782](D:\报告\Report\pic\\image-20220505220446782.png) 

会包括全部节点（文本节点和元素节点）

获取子元素节点：![image-20220505221055461](D:\报告\Report\pic\\image-20220505221055461.png) 

![image-20220505221138589](D:\报告\Report\pic\\image-20220505221138589.png) 

两种方法获取子元素，其中下方children写法更适用；

##### 第一个节点和最后一个节点

firstChild：获取第一个节点，不管是元素节点还是文本节点。

lastChild：获取最后一个节点，不分元素节点还是文本节点。

![image-20220505221920229](D:\报告\Report\pic\\image-20220505221920229.png) 

firstElementChild:第一个元素节点

lastElementChild:最后一个元素节点

![image-20220507170831643](D:\报告\Report\pic\\image-20220507170831643.png) 

常用写法![image-20220507170952094](D:\报告\Report\pic\\image-20220507170952094.png) 

#### 兄弟节点

nextSibling：下一个节点（包含文本节点在内）

previousSibling：上一个节点（包含文本节点）

![image-20220507171817700](D:\报告\Report\pic\\image-20220507171817700.png) 

nextElementSibling：下一个兄弟元素节点，找不到返回null

previousElementSibling：上一个兄弟元素节点，找不到返回null

![image-20220507172138124](D:\报告\Report\pic\\image-20220507172138124.png) 

自己封装：

<img src="D:\报告\Report\pic\\image-20220507172313237.png" alt="image-20220507172313237" style="zoom:50%;" /> 

注：**el.nodeType===1**表示节点类型为元素节点

找到一个元素节点时就进行返回

#### 创建节点

document.createElement('tagname')

![image-20220507172839082](D:\报告\Report\pic\\image-20220507172839082.png) 

例子：![image-20220507174224935](D:\报告\Report\pic\\image-20220507174224935.png) 

添加节点：node.appenChild(child)  **插入到末尾**![image-20220507173127953](D:\报告\Report\pic\\image-20220507173127953.png) 

例子：![image-20220507174252282](D:\报告\Report\pic\\image-20220507174252282.png) 

node.insertBefore(child,指定元素)   **插入到前头**

![image-20220507175301546](D:\报告\Report\pic\\image-20220507175301546.png) 

例子：![image-20220507175537035](D:\报告\Report\pic\\image-20220507175537035.png)

![image-20220507175544410](D:\报告\Report\pic\\image-20220507175544410.png) 

----

##### 三种方式及其区别

document.write()：在文档中写入![image-20220510212853336](D:\报告\Report\pic\\image-20220510212853336.png) 

缺点：做成JS时，会重新制作一个HTML文档，导致之前的网页元素丢失。

![image-20220510213814430](D:\报告\Report\pic\\image-20220510213814430.png) 

document.HTML   和    document.appenChild()

![image-20220510213911361](D:\报告\Report\pic\\image-20220510213911361.png) 



document.HTML:![image-20220510214405856](D:\报告\Report\pic\\image-20220510214405856.png) 

document.appenChild():![image-20220510214453063](D:\报告\Report\pic\\image-20220510214453063.png) 

使用时效果差别不大，但是时间差别较大。

document.createElement():![image-20220510215140401](D:\报告\Report\pic\\image-20220510215140401.png) 

优化：

document.HTML：![image-20220510214858272](D:\报告\Report\pic\\image-20220510214858272.png) 

先放入数组中![image-20220510215231016](D:\报告\Report\pic\\image-20220510215231016.png) 

总结：innerHTML的效率比createELement高

---



#### 删除节点

node.removeChild(child)

![image-20220507184839588](D:\报告\Report\pic\\image-20220507184839588.png) 

从父节点中删除一个子节点

![image-20220507185355262](D:\报告\Report\pic\\image-20220507185355262.png) 

点击按钮即可删除第一个元素，当ul内children的长度为0时，让点击禁用。

#### 复制节点

node.cloneNode()

![image-20220507191411946](D:\报告\Report\pic\\image-20220507191411946.png) 

![image-20220507191417316](D:\报告\Report\pic\\image-20220507191417316.png) 

意思是，如果括号内不填参数就只复制节点，不复制节点内的内容。

![image-20220507191535365](D:\报告\Report\pic\\image-20220507191535365.png) 

参数为false和true两个，填写true时可以顺便将内容拷贝