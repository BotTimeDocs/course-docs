# 第十一课(05)：RPA小任务1--读取csv文件学生信息并另存

<br>

**【课程目标】**

<br>

* 结合上节课中数据表知识在搭建数据表基础上进阶学习，本节课主要强化大家对一个业务不同实现方式；

* 实现过程中重点考察前面初级课程中，大家对变量类型的掌握与灵活使用程度；

* 本次课程希望大家用心学习，可以帮助大家进一步巩固RPA流程搭建的设计思路，属于向专业的RPA业务开发能力迈进的基础知识。


<br><br>

**课时内容：**

> * RPA第十二课 (2023年)
> * 课程时长：52分钟 ,7节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--读取区域VS读取行/列数据（课程时长：5分钟）
> * 知识点2--读取区域+遍历行>>实现遍历表（课程时长：10分钟）
> * 知识点3--读取区域+循环操作(ForEach)>>实现遍历表（课程时长：7分钟）
> * 知识点4--读取行/列数据+循环操作(ForEach)>>实现遍历表（课程时长：5分钟）
> * RPA小任务1--读取csv文件中已成年的学生信息并另存（课程时长：5分钟）
> * RPA小任务2--商品信息抓取后”单表”数据去重（课程时长：10分钟）
> * RPA小任务3--商品信息抓取后”多表”合并后数据去重（课程时长：10分钟）

<br><br><br>



##  二、学习内容：
<br>

* 课程简介： RPA小任务1--读取csv文件中已成年的学生信息并另存（课程时长：5分钟）
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E5%8D%81%E4%B8%80%E8%AF%BE/RPA%E5%B0%8F%E4%BB%BB%E5%8A%A11--%E8%AF%BB%E5%8F%96csv%E6%96%87%E4%BB%B6%E5%AD%A6%E7%94%9F%E4%BF%A1%E6%81%AF%E5%B9%B6%E5%8F%A6%E5%AD%98.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>



#### 一、案例目标：

* 从CSV中读取并处理数据表，随后将数据写回CSV文件。

<br>

**（1）** 如图，该demo.csv文件记录了学生的姓名、性别和年龄。<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736152165259.jpg"/>

<br><br>


<br>

**（2）** 目标：添加一列“是否成年”，并根据年龄是否>=18，在该列填写“是”或“否”。<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736152214566.jpg"/>

<br><br>



#### 二、具体搭建步骤 ：

<br>

**第1步：**

* 添加【读取CSV文件】组件至面板，读取demo.csv，并将其保存到数据表的变量dataTable中；
* 因为这个csv文件里面包含中文，且编码方式是“GB2312”，所以读取的时候编码方式也选择“GB2312”。
 <img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154514230.jpg"/>

<br><br>


**第2步：**

* 拖入【添加数据列】组件，添加列名为：“是否成年”列，数据类型为：String。
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154464567.jpg"/>

<br><br>


**第3步：**

* 添加【遍历行】组件，设置“当前行索引”保存到“currentIndex”变量中。


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154412972.jpg"/>

<br><br>


**第4步：**

* 添加【获取单元格的值】组件至遍历行组件中， 行索引为：currentIndex，列索引为：2，并将结果保存至变量“currentAge”中。


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154376024.jpg"/>

<br><br>

**第5步：** 

* 添加【条件 (if)】组件，判断条件为：currentAge<18。

* (1) 条件成立时，使用【设置数据行的值】组件，对第4列（列索引为：3）设置：“否”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154314796.jpg"/>

<br><br>


* (2) 同样条件不成立则设为“是”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154264576.jpg"/>

<br><br>




**第6步：**
* 添加【保存为CSV文件】组件，将处理后的数据表保存到demo2.csv文件中（也可选择覆盖原csv文件）。
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736154221907.jpg"/>

<br><br>


**第七步：**

* 点击运行。流程运行结束后打开新的csv文件，即可看到修改后的数据。


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736152214566.jpg"/>

<br><br><br><br>


### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)





