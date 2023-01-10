# 第八课(06)：循环操作 (While)的用法

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

* 课程简介：知识点6--循环操作 (While)的用法 (课程时长:4分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B91--%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6%E2%80%9C%E5%AE%9A%E4%B9%89%E2%80%9D.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

**（1）组件功能：** 在满足循环条件的前提下，执行重复的操作。

<img width = '400'  src =""/>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733501315322.jpg)

<br><br>

**（2）组件使用步骤：**
<br><br>

**第1步：** 拖入循环操作（While）组件，创建一个类型为Int的变量count_num, 默认值设置为0。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733502216028.jpg"/>

<br><br>

**第2步：** 将循环操作（While）组件的条件设置为：number < 3, 表示在number小于3的情况下，重复执行该组件内流程。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733502255331.jpg"/>

<br><br>

**第3步：** 拖入写入日志组件至循环操作（While）中，日志内容为count_num.ToString()

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733502299799.jpg"/>


<br><br>

> **注意：** 
> * 由于count_num默认值为0，永远小于3，则流程进入死循环;
> * 在日常流程设计中，一定要注意避免流程进入死循环！有些特殊情况下，可能需要死循环，需要根据业务情况来决定...

<br><br><br>

**第4步：** 拖入赋值组件，变量名为count_num, 值为count_num+1, 作用是改变count_num的值。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733502372064.jpg"/>

<br><br><br>

**第5步：** 运行该流程，即可输出小于3的数字。

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733502447945.jpg"/>

<br><br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)

