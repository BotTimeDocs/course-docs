

<br>

**【课程目标】**

<br>

* 结合上节课中数据表知识在搭建数据表基础上进阶学习，本节课主要强化大家对一个业务不同实现方式；

* 实现过程中重点考察前面初级课程中，大家对变量类型的掌握与灵活使用程度；

* 本次课程希望大家用心学习，可以帮助大家进一步巩固RPA流程搭建的设计思路，属于向专业的RPA业务开发能力迈进的基础知识。


<br><br>

**课时内容：**

> * RPA第十四课 (2023年)
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

* 课程简介：RPA小任务3--商品信息抓取后”多表”合并后数据去重（课程时长：10分钟）
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E5%8D%81%E4%B8%80%E8%AF%BE/RPA%E5%B0%8F%E4%BB%BB%E5%8A%A13--%E5%95%86%E5%93%81%E4%BF%A1%E6%81%AF%E6%8A%93%E5%8F%96%20%20%E2%80%9D%E5%A4%9A%E8%A1%A8%E2%80%9D%E5%90%88%E5%B9%B6%E5%90%8E%E6%95%B0%E6%8D%AE%E5%8E%BB%E9%87%8D.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

#### 一、案例目标

* 所有数据都存在总表中，需要将已处理的子表内容从总表中剔除，余下不重复的数据部分。

<br><br>

#### 二、具体搭建步骤：

<br>

**第1步：**

* 使用【搭建数据表】组件创建2个数据表。

* (1)总表：

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165253303.jpg"/>

<br><br>

* (2)子表：

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165308442.jpg"/>

<br><br>

> **提问1：** 如果使用【遍历行】组件，是无法移除正在遍历的行的。那么该怎么循环呢？
> 
> --可以使用【循环操作 While】组件。
> 
> 
> **提问2：** 循环操作时，移除行会导致后面的行顺序发生变化，譬如我们从数据表的第1行循环到最后1行，当移除第2行时，第3行就会变成第2行，第4行就会变成第3行...该怎么办呢？
> 
> --反过来，从最后1行开始循环，到第1行结束。

<br><br>

**第2步：**
* 创建变量“currentNumber”，用于记录当前所在行，使用【赋值】组件为其赋值。
“总表.Rows.Count”会返回当前行数，“总表.Rows.Count-1”则为当前行索引。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165378310.jpg"/>

<br><br><br>

**第3步：**
* 使用【循环操作 While】组件，条件是currentNumber≥0。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165418058.jpg"/>

<br><br><br>

**第4步：**
* 使用【获取单元格的值】组件，获取第currentNumber行第1列的数据内容，拿到当前数据行的“商品名称”，并把结果存储到“商品名称”变量里

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165457403.jpg"/>

<br><br><br>

**第5步：**
* 使用【筛选】组件对子表进行筛选，查看是否存在总表提取出的商品名称。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165503864.jpg"/>

<br><br><br>

**第6步：**
* 拖入【条件（If）】组件，条件是“筛选结果.Rows.Count > 0”，这证明两表存在一致的商品名称。当条件成立时，执行【移除行】组件，移除第currentNumber行。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165547536.jpg"/>

<br><br><br>

**第7步：**
* 使用赋值组件，将“currentNumber-1”，否则流程将陷入循环。
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165588590.jpg"/>

<br><br><br>

**第8步：**
* 拖入【预览数据表】组件展示结果。

<br><br><br>

**第9步：** 
* 点击运行，最后结果就出来啦~

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736165629444.jpg"/>


<br><br><br><br>

### END:
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)





