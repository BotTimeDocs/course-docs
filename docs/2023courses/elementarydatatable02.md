# 第十课(02)：知识点2--搭建数据表

<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

* 本周内容主要对常见的数据表组件进行学习及使用,数据表一般在excel、网页自动化、流程循环设计中都会用到；
* 第十课请掌握基本用法，第十一课我们将一起用数据表与excel搭配结合，一起和大家通过案例提升与加强流程设计思路。

> 注意：数据表datatable为一个流程中处理构建数据的中枢载体至关重要。


<br><br>

**课时内容：**

> * RPA第十课 (2023年)
> * 课程时长：29分钟 ,10节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--数据表基础概念(课程时长:2分钟)
> * 知识点2--搭建数据表(课程时长:6分钟)
> * 知识点3--获取单元格的值 >> 获取数据表中王五的姓名(课程时长:5分钟)
> * 知识点4--设置数据表的值 >> “更改王五的年龄”(课程时长:2分钟)
> * 知识点5--添加数据行 >> 陈某数据信息加入数据表(课程时长:2分钟)
> * 知识点6--添加数据列 >> 数据表添加一列年龄信息(课程时长:2分钟)
> * 知识点7--移除行&移除列(课程时长:3分钟)
> * 知识点8--移除重复行(课程时长:2分钟)
> * 知识点9--筛选(课程时长:2分钟)
> * 知识点10--遍历行(课程时长:3分钟)

<br><br><br>



##  二、学习内容：
<br>

* 课程简介：知识点2--搭建数据表(课程时长:6分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E5%8D%81%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B92--%E6%90%AD%E5%BB%BA%E6%95%B0%E6%8D%AE%E8%A1%A8%E8%A1%A8.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>


#### 一 、搭建数据表

按照自定义结构生成一张新的数据表，首先需要定义列信息，并可同步预览定义的列并进行编辑。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736133635060.jpg"/>

<br><br>


**(1).输出**

数据表：可构建变量，将搭建的数据表存储在此变量中。
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736133756957.jpg"/>

<br><br>


**(2).列信息**

点击“新加列”自动生成一个默认信息行，可对默认信息进行修改。
  - 列名：数据表的列名。
  - 数据类型：目前仅支持 String、Int 和 Boolean 类型。
  - 默认值：当前列新增数据时的默认值。
  - 唯一值：是否允许该列存在重复信息。
  - 值可为空：是否可不填写，系统默认可为空。
  - 整形自动加一：若列数据类型为Int，可勾选，在新增行时自动将数据加一。
  - 最大长度：最大支持长度，可为空。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736133816481.jpg"/>

<br><br>


**(3).编辑行值**


* 将列信息放至列头，以便为搭建的数据表添加初始值。(以下表为例，姓名为string类型，年龄为int类型，并随机插入了两条信息)

    * 由于勾选了整形自动加一，年龄列新增的第二行数据为第一行数据+1。
    * 红框中的三个按键可用来删除行数据，或调整行数据位置。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736133880046.jpg"/>

<br><br>


#### 二 、预览数据表

在流程运行至该组件时，将数据表内的数据以弹框形式展现，使数据更加直观。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736133915635.jpg"/>

<br><br>



### END:

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)




