##### 循环精灵图

分析，通过js将计算图标的距离，利用代码改动。

![image-20220423215328076](D:\报告\Report\pic\/image-20220423215328076.png) 

注意：此处样式的修改是字符串。

~~~js
var lis=document.querySelectorAll('li');
for(var i=0;i<lis.length;i++)
{
    var index=i*44;
    //此处44是间距，根据不同的换
    lis[i].style.backgroudPosition='0 -'+ index +'px';
    //此处的 '0 -'也是根据不同进行调整
}
~~~



-------



##### 显示隐藏文本框内容（新事件）

需要表单事件：![image-20220423220059387](D:\报告\Report\pic\/image-20220423220059387.png) 

![image-20220423220753142](D:\报告\Report\pic\/image-20220423220753142.png)![image-20220423220804886](D:\报告\Report\pic\/image-20220423220804886.png) 

--------



##### 密码框验证信息

![image-20220423222235695](D:\报告\Report\pic\/image-20220423222235695.png) 

----

##### 排他思想

思路：

1.先清除其他干扰样式

2.单独设置需要的样式

如下：按钮点击案例，做到点击即可变色而不干扰其他。

![image-20220425160729294](D:\报告\Report\pic\/image-20220425160729294.png) 

循环思想：每点击一次就执行循环，并且让点击的位置变为当前的 this

~~~js
var btns=document.getElementsByTagName('button');
for(var i=0;i<btns.length;i++)
{
    btns[i].onclick=function()
    {
        for(var j=0;j<btns.lenght;i++)
            btns[j].style.backgroudColor=' ';
    }
    this.style.backgroundColor='skybule';
    //这里放自己指定的颜色
}
~~~



其他案例：点击换皮肤

事件变量用类名加标签名寻找不易出错

 ![image-20220425161506520](D:\报告\Report\pic\/image-20220425161506520.png) 

.baidu应该是一个存放图片的盒子，用选择器选择盒子里面的图片标签。

点击后修改背景图片的url为对应点击的图片即可。



**切换栏**

![image-20220425175353186](D:\报告\Report\pic\//image-20220425175353186.png) 

![image-20220425175705886](D:\报告\Report\pic\//image-20220425175705886.png) 

基础操作获取属性，分步骤操作便于精准确认元素

![image-20220425175447740](D:\报告\Report\pic\//image-20220425175447740.png) 

清除其他的类名，以免影响显示。

设置自定义属性（index）作为索引号，便于后方索引显示对应内容。

![image-20220425175756956](D:\报告\Report\pic\//image-20220425175756956.png) 

清除其他的显示，然后仅显示当前点击。

~~~js
var tbl=document.querySelector('.tbl');
//tbl为总栏
var lis=tbl.document.querySelector('li');
//lis为tbl里面全部的ls
var items=document.querySelectorAll('.index');
for(var i=0;i<lis.lenght;i++)
{
    lis[i].setAttribute('index',i);
    //给每个li添加自定义属性index，属性值为i（循环改变）
    lis[i].onclick=function()
    {
        for(var i=0;i<lis.lenght;i++)
        {
            lis[i].className=' ';
        }
        this-className='current';
        //改为对应标签
        for(var i=0;i<items.lenght;i++)
        	items[i].style.display='none';
        //关闭其他板块
        items[index].style.display='block';
    }
}
~~~



----------



##### 隔行变色（新事件）

需要到的事件：![image-20220425161839061](D:\报告\Report\pic\//image-20220425161839061.png) 

思路：经过添加 单独 的类名，离开时 清除 类名

![image-20220425162241816](D:\报告\Report\pic\//image-20220425162241816.png) 

~~~js
var trs=document.querySelector('tbody').querySeletorAll('tr');
//选中tbody里面全部的tr（行）
for(var i=0;i<trs.lenght;i++)
{
    trs[i].onmouseover=function()
    {
        this.className='bg';
        //把鼠标经过的tr加上bg这个类名
    }
    trs[i].onmouseout=function()
    {
        this.className='';
        //设定鼠标离开时的取消全部类名
    }
}
~~~



-------

##### 全选按钮

需要用到input.check属性，让下方单选按钮的状态等于全选按钮的状态即可

循环赋值即可

![image-20220425162801854](D:\报告\Report\pic\//image-20220425162801854.png) 

单选全部选中时，全选自动勾上

思路：用循环单独勾选，当全部的状态为true时

![image-20220425171128746](D:\报告\Report\pic\//image-20220425171128746.png) 

~~~js
var cbAll=document.getElementById('cbAll')//全选按钮的id
var tbs=document.getElementById('tb')//表达内个别按钮的id
cbAll.onclick=function()
{
    for(var i=0;i<tbs.lenght;i++)
        tbs[i].checked=this.checked;
    //点中全选时让全部按钮都被选中
}
for(var i=0;i<tbs.lenght;i++)
{
    tbs[i].onclick=function()
    {
        var flag=true;
        //设定初始真值为真
    	for(var j=0;j<tbs.lenght;j++)
        {
            //当其中个别按钮有一个未被选中时进入条件语句
      	  	if(!tbs[i].checked)
    	 	{
            	flag=false;
            	break;
                //将标记置假
         	}
    	}
        cbAll.checked=flag;
        //取消全选
    }
}
~~~



----



##### 发言墙

![image-20220507183714173](D:\报告\Report\pic\//image-20220507183714173.png) 

思路：点击发言后，在ul后添加一个li，并且修改li里面更改文字并赋值给新加入的li即可；

ul.appenChild(li)将新创建的li插入到最后

ul.insertBefore(li,ul.children[0])将新创建的li插入到最前

删除按钮：在对li修改时，顺便添加一条删除的链接（a）![image-20220507190133757](D:\报告\Report\pic\//image-20220507190133757.png) 

**小知识1，阻止链接跳转：href='javascript:;'**

重点：**删除特定的li，此刻的li是a的父节点**

![image-20220507190905407](D:\报告\Report\pic\//image-20220507190905407.png) 

删除此刻ul里的点击的a的父节点-->即对应的li

~~~js
var btn=document.querySelector('button');
var text=document.querySelector('textarea');
var ul=document.querySelector('ul');
btn.onclick=function()
{
    if(text.value==' ')
    {
        alert('未输入')；
        return false;
    }
    else 
    {
        var li=document.createElement('li');
        li.innerHTML=text.value;
        //插入到最后ul.appendChild(li);
        ul.insertBefore(li,ul.children[0]);
        //也是插入头部
    }
}
var as=document.querySelector('a');
for(var i=0;i<as.length;i++)
{
    as[i].onclick=function()
    {
        ul.removeChild(this.parentNode);
        //删除对应的父节点（li）
    }
}
~~~



-------



##### 动态表格

thead做表头不操作，对tbody进行操作

每点击增加就在tbody内部添加行(tr)，然后再行内创建单元格(td),单元格数量为对象属性个数

**准备数据阶段：**![image-20220507192123204](D:\报告\Report\pic\//image-20220507192123204.png) 

构造函数更为实用，如下：

~~~js
function stu(name,sub,sco)
{
	this.name=name;
	this.subject=sub;
	this.score=sco;
}
var data=[];
var num=parseInt(prompt("请输入人数："));
//num为学生人数
for(var i=0;i<num;i++)
	data[i]=new stu(name,sub,sco);
~~~

**准备生成新的单元格：**![image-20220509171740837](D:\报告\Report\pic\//image-20220509171740837.png) 

**填充数据：**

下方代码为上方的优化![image-20220509175848064](D:\报告\Report\pic\//image-20220509175848064.png) 

js对象obj[i]得到的是属性名,如果是对象数组obj[i] [k]则可以遍历每一个对象的属性值（内部的数值并非属性名）

**删除操作：**![image-20220509180745670](D:\报告\Report\pic\//image-20220509180745670.png) 

创建新的单元格，然后改变内部标签样式，最后插入到表格末尾。

注：此段代码在最外层的for内

删除操作代码：![image-20220509181204207](D:\报告\Report\pic\//image-20220509181204207.png) 

在最外层for下方

注：**removeChild**删除的是父节点内的子节点，要删除的是tbody内的td，而此处获取的是所有的a标签，要求删除的对象则为此处a标签的父级（tr）的父级（td），不必担心删错，已经将能使用删除功能的链接限制在tbody里了



~~~js
function stu(name,sub,sco)
{
	this.name=name;
	this.subject=sub;
	this.score=sco;
}
var data=[];
var num=parseInt(prompt("请输入人数："));
//num为学生人数
for(var i=0;i<num;i++)
{
    var name=prompt();
    var sub=prompt();
    var sco=parseInt(prompt());
    data[i]=new stu(name,sub,sco);
}
//准备数据阶段
var tbody=document.querySelector('tbody');
for(var i=0;i<data.length;i++)
{
    //创建每一行
    var tr=document.createElement('tr');
    tbody.appendChild(tr);
    for(var k in data[i])
    {
        //创建每个单元格并且赋值内容
        var td=document.createElement('td');
        td.innerHTML=data[i][k];
        tr.appendChild(td);
    }
    var td=document.craeteElement('td');
    td.innerHTML='<a href="javascript:;">删除</a>';
    tr.appendChild(td);
    //创建完对应单元格后，在后面创建对应删除单元格
}
var as=document.querySelectorAll('a');
//选取所有的a标签
for(var i=0;i<as.length;i++)
{
    //当点击了某个a时
    as[i].onclick=function()
    {
        tbody.removeChild(this.parentNode.parentNode);
        //删除tbody内部这个节点内的父节点（td）的父节点（tr）
    }
}
~~~

