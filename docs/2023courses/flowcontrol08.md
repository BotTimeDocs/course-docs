# 第八课(08)：学生考试“成绩统计”

<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

通过对下列知识点的学习，最终完成一个简单的“学生考试--成绩统计”小任务。
* 判断类组件: （流程控制、条件 if、条件Switch）
* 循环类组件 :（循环操作 While、循环操作 Do While、循环操作 For Each、终止循环、继续循环...）


<br><br>

**课时内容：**

> * RPA第八课 (2023年)
> * 课程时长：23分钟 ,8节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--流程控制“定义” (课程时长:2分钟)
> * 知识点2--3个分支结构组件(决策判断) (课程时长:8分钟)
> * 知识点3--循环控制(For Each) (课程时长:2分钟)
> * 知识点4--继续循环 & 终止循环 (课程时长:3分钟) 
> * 知识点5--重复操作 (课程时长:2分钟)
> * 知识点6--循环操作 (While)的用法 (课程时长:4分钟)
> * 知识点7--"Do While"与"While"区别 (课程时长:2分钟)
> * RPA小任务--学生考试“成绩统计” (课程时长:5分钟)

<br><br><br>



##  二、学习内容：
<br>

* 课程简介：RPA小任务--学生考试“成绩统计” (课程时长:5分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B91--%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6%E2%80%9C%E5%AE%9A%E4%B9%89%E2%80%9D.mp4"> </video>

<br><br><br>

### 2.2 文档教程



#### 一、RPA小任务概览：

<br>
<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733505548165.jpg"/>
<br><br>

<br><br>

#### 二、RPA任务--流程搭建步骤

<br><br>
**第1步：** 定义一个名为所有成绩的数组变量，且数组中的类型为Int。

<br>
<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733512006815.jpg"/>
<br><br>

![]()


<br><br>
**第2步：** 在变量的默认值中输入C#代码new int[]{此处填入30个有效成绩}。

<br>
<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733512408792.jpg"/>
<br><br>



<br><br>
**第3步：** 再定义一个类型为Double的结果变量（最后的占比结果可能存在小数点）。

<br>
<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733512922263.jpg"/>
<br><br>
 

<br><br>
**第4步：** 再新建一个Int类型变量为：超过90分的数量，用于统计成绩大于90分的学生数量，默认值设置为0。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733513207300.jpg"/>
<br><br>


<br><br>
**第5步：** 拖入循环操作（For each）组件至面板，循环体为所有成绩。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507481202.jpg"/>
<br><br><br><br>


**第6步：** 拖入条件（If）组件至For each组件中，输入判断条件：item＞90。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507434270.jpg"/>
<br><br><br><br>



**第7步**：在条件成立板块拖入赋值组件，为变量“超过90分的数量”赋值为：超过90分的数量+1。 条件不成立则不做处理。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507360024.jpg"/>
<br><br>


<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507385380.jpg"/>
<br><br>


**第8步：** 在循环组件后再拖入赋值组件，为结果赋值；值为：超过90分的数量*1.0/所有成绩.Length()*100。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507318587.jpg"/>
<br><br>


**第9步：** 拖入写入日志组件，将结果打印出来。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507275548.jpg"/>
<br><br>

**第10步：** 运行该流程，即可在日志中看到分数超过90分的学生比例。

<br>
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733507233111.jpg"/>
<br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)

