# 第八课(04)：继续循环 & 终止循环

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

* 课程简介：知识点4--继续循环 & 终止循环 (课程时长:3分钟) 
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B91--%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6%E2%80%9C%E5%AE%9A%E4%B9%89%E2%80%9D.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

**（1）组件功能：** 可作用于所有的循环组件，决定流程是继续进行还是就此停止。

* 继续循环：在当前位置不再执行后续组件，跳出当前循环，执行下一个循环。
* 终止循环：跳出当前整个循环，执行循环后的组件。

<br><br>

**（2）组件使用步骤：**

**第1步：** 拖入循环操作(For Each)组件，在循环体中创建一个变量类型为String的数组。
变量类型设置为String[], 默认值填写new String[] { "第一个", "第二个","第三个" }

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733495676888.jpg"/>

<br><br>

**第2步：** 拖入条件（If）组件至循环操作（For Each）中，点击创建条件，左侧值输入item, 符号不变，右侧值填入”第二个”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733495723906.jpg"/>

<br><br>

**第3步：** 在条件成立板块拖入终止循环组件，条件不成立板块不做处理。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733495860892.jpg"/>

<br><br>

**第4步：** 拖入写入日志组件至循环操作（For Each）中，内容填写为：item。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733495915918.jpg"/>

<br><br>

**第5步：** 点击运行，即可看到终止循环起效，流程只打印出数组的第一个元素，循环就停止了。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733495963604.jpg"/>

<br><br>

若将终止循环改为继续循环，再次运行，即可发现流程打印出第一个和第三个，没有打印第二个。
<br>

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733496030565.jpg"/>

<br><br><br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)
