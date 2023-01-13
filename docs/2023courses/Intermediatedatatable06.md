# 第十一课(06)：RPA小任务2--商品信息抓取 >>”单表”数据去重

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

* 课程简介：RPA小任务2--商品信息抓取后”单表”数据去重（课程时长：10分钟）
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E5%8D%81%E4%B8%80%E8%AF%BE/%E5%8D%81%E4%B8%80%E8%AF%BE%2806%29%EF%BC%9ARPA%E5%B0%8F%E4%BB%BB%E5%8A%A12--%E5%95%86%E5%93%81%E4%BF%A1%E6%81%AF%E6%8A%93%E5%8F%96%20%E2%80%9D%E5%8D%95%E8%A1%A8%E2%80%9D%E6%95%B0%E6%8D%AE%E5%8E%BB%E9%87%8D.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

#### 一、案例目标

* 重复抓取某网页上的数据，并把多次获取的数据合成为一张数据表，同时去除重复行。

<br>

#### 二、具体搭建步骤：

<br>

**第1步：**

用搭建数据表组件创建2个数据表。
   
- 表1、总表

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736159757066.jpg"/>

<br><br>


- 表2、本次抓取结果

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736159806523.jpg"/>

<br><br><br>


**第2步：**

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736159902853.jpg"/>

<br><br>


* 使用【合并数据表】组件，将“本次抓取结果”的数据表作为源数据表，合并到目标“总表”中。
* 此时添加【预览数据表】组件，即可看到合并后的总表数据。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736159974382.jpg"/>

<br><br>


> **注意：** 被合并的两表需要保持结构一致。


<br><br><br><br>

**第3步：**
* 使用【移除重复行】组件，将重复的“IQQO 8”移除。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736160092744.jpg"/>

<br><br><br>

**第4步：**
* 添加【预览数据表】组件，用于展示结果。

<br><br><br>

**第5步：**

* 点击运行。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736160172696.jpg"/>


<br><br><br>

### END:

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)





