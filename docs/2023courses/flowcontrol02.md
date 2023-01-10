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

* 课程简介：知识点2--3个分支结构组件(决策判断) (课程时长:8分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="hhttps://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B92--3%E4%B8%AA%E5%88%86%E6%94%AF%E7%BB%93%E6%9E%84%E7%BB%84%E4%BB%B6%28%E5%86%B3%E7%AD%96%E5%88%A4%E6%96%AD%29.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

#### 一、流程判断

<br><br>

**（1）组件功能**


流程判断组件的功能，主要是根据Condition中的变量（Boolean类型）判断Ture/False，从而决定分支走向。课程接下来将用一个案例，带大家学会流程判断组件的使用。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733464255353.jpg"/>

<br><br><br>


**（2）学习目标：** 使用流程判断组件设置变量，从而打印出：执行True分支。

<br>

* **第1步：** 拖入流程判断组件至面板中。<br>

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733470053097.jpg"/>

<br><br>

* **第2步：** 指定一个Boolean类型的变量v1，填写至右侧属性栏的Condition中，并点击创建变量。<br>

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733470117444.jpg"/>


<br><br>

* **第3步：** 在流程判断组件的True和False分支分别添加一个写入日志组件，并填写所需打印出的信息。<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733470215542.jpg"/>


<br><br>

* **第4步：** 将变量v1的默认值设置为True。<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733470303423.jpg"/>


<br><br>

* **第5步：** 运行该流程, 即可在运行日志中看到流程打印出“执行True分支”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733470337919.jpg"/>

<br><br><br>

> **注意：** 流程判断组件仅支持在流程图中使用

<br><br><br>

#### 二、条件(If)

**（1）组件功能**
* 与流程判断组件功能类似，条件（If）组件可以根据条件的True/False决定流程走向；
* 与流程判断组件不同的是：条件（If）组件既可用在流程图中，也可以用在序列中。

<br><br>

**（2）学习目标：**

利用条件（If）组件，使流程运行False分支，打印出：不成立。

**第1步：** 拖入条件(If)组件至面板中。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471181834.jpg"/>

<br><br><br>

**第2步：** 双击组件，出现属性面板。
* 判断条件即等同于流程判断组件中的Condition，在此处创建一个Boolean类型的变量v1。
* 条件成立=True分支；条件不成立=False分支。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471246698.jpg"/>

<br><br><br>

**第3步：** 在条件成立和不成立面板分别添加一个写入日志组件，并填写所需打印出的信息。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471296889.jpg"/>

<br><br><br>
 
**第4步：** 将变量v1的默认值设置为False。<br><br>

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471349692.jpg"/>

<br><br><br>

**第5步：** 运行该流程。
即可在运行日志中看到流程打印出“不成立”。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471397194.jpg"/>



<br><br><br>

> **补充：**
> 
> 在Condition/判断条件中也可写入其它类型变量或表达式进行判断。如下图所示：
> 第1步：创建一个Int32类型的变量v2，默认值为3;
> 
> 第2步：在判断条件中对v2是否等于3进行判断;
> 
> 第3步：运行该流程后，日志打出成立，则证明v2=3。

<br><br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471482093.jpg"/>

<br><br>


> **提问：**
> 
> * 在条件（If）组件或流程判断组件中，都只有true/false，成立/不成立两个选择，那是否有可能遇到2个以上的选择呢？该怎么办呢？
> 
> * 用多个If组件嵌套即可解决该问题，但也可以使用另一个更简单直观的组件，那就是条件（Switch）组件。

<br><br><br>


#### 三、条件（Switch）

<br><br>

**（1）组件功能:** 
* 根据表达式判断执行用例。可在表达式处输入变量，并对变量进行判断。
* 将可能的选择写入用例（Case）中，当所有用例都无法执行时，系统则会默认执行Default。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471690814.jpg"/>

<br><br>

**（2）学习目标：** 通过使用条件(Switch)组件判断变量数值。

**第1步：** 拖入条件(Switch)组件至面板中。

<br><br><br>

**第2步：** 在Expression中输入一个表达式，创建一个类型为Int32的变量v1，默认值设置为5。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471737819.jpg"/>

<br><br><br>

**第3步：** 点击添加新的用例，在case中输入1。
并在该用例中拖入写入日志组件，输入：“数字是1”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471858711.jpg"/>


<br><br><br>

**第4步：** 再添加一个新的用例，在case中输入3;并在该用例中拖入写入日志组件，输入：“数字是3”; 重复该操作并输入5。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733471998205.jpg"/>

<br><br><br>

**第5步：** 在Default栏点击添加组件，并拖入写入日志组件，输入“数字不是1，不是3，也不是5”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733472091831.jpg"/>

<br><br><br>


**第6步：** 运行该流程。即可看到流程日志打印出：“数字是5”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733472165449.jpg"/>

<br><br><br>


若把变量默认值改为6，流程则会进入Default分支，打印出：“数字不是1，不是3，也不是5”。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/10/16733472238214.jpg"/>

<br><br><br>

#### 四、流程判断组件的区别

<br>

<table style="undefined;table-layout: fixed; width: 569px">
<colgroup>
<col style="width: 57px">
<col style="width: 128px">
<col style="width: 384px">
</colgroup>
<thead>
  <tr>
    <th></th>
    <th>组件名称</th>
    <th>使用区别</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>（1）</td>
    <td>流程判断</td>
    <td>有两个分支走向，仅支持在流程图中使用</td>
  </tr>
  <tr>
    <td>（2）</td>
    <td>条件（If）</td>
    <td>有两个分支走向，在流程图和序列中均可使用。</td>
  </tr>
  <tr>
    <td>（3）</td>
    <td>条件（Switch）</td>
    <td>可以设置多个分支。</td>
  </tr>
</tbody>
</table>

<br><br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)
