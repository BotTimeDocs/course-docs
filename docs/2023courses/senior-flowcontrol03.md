# 第十八课(03)：知识点3--重试&终止流程

<br><br>

## 一、课程简介

<br>

**【课程目标】**

通过本期课程一起学习：如何使用容错组件对错误进行相应的处理，组件的失败后继续属性，以及两个特殊的处理流程。


<br><br>

**课时内容：**

> * RPA第十八课 (2023年)
> * 课程时长：30分钟 ,5节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--TryCatch(容错组件)的定义及作用（课程时长：5分钟）
> * 知识点2--抛出异常&重新抛出异常（课程时长：4分钟）
> * 知识点3--重试&终止流程（课程时长：3分钟）
> * 知识点4-异常处理&终止处理流程（课程时长：3分钟）
> * RPA小任务--数据标记识别（课程时长：15分钟）

<br><br><br>



##  二、学习内容：

<br>

* 课程简介：知识点3--重试&终止流程（课程时长：3分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B93--%E9%87%8D%E8%AF%95%26%E7%BB%88%E6%AD%A2%E6%B5%81%E7%A8%8B.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

### 一、重试

重试组件中可以拖入其他组件。重试组件有一个属性是条件属性，当满足了设置的条件以后，这些拖入的组件一旦发生了错误，重试组件就会起作用。

可以设置重试次数来决定最多重试几次。

<br><br>

**可选项：**
- 条件：当满足设置的条件后，设置的组件发生错误时，重试组件就会起作用。
> 为“True”时表示执行重试，为“False”时表示不执行重试。
- 重试次数：填写需要让组件重试的次数。
- 重试间隔：填写每次重试的时间间隔。


<br><br>

**第1步：** 

> 拖入`trycatch`组件，并在`Try`中拖入重试组件。
>
>在重试组件中拖入写入日志组件，输入“重试测试”。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758457935278.jpg"/>


<br><br><br>

**第2步：**

> 在写入日志后拖入一个抛出异常组件，输入`new Exception(“重试Test”)`。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758457890117.jpg"/>


<br><br><br>

**第3步**：在`catch`中承接异常。

拖入写入日志组件到`Catch`中，输入`Exception.Message`。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758457834837.jpg"/>

<br><br>

**第4步：** 点击运行。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758457449443.jpg"/>

<br><br>

可以看到重试测试被打印了三次，第一次是流程正常运行至写入日志，后两次是重试组件的效果。所以“重试测试”一共被打印了三次。

第二次进入重试组件以后，抛出异常，这时重试组件的2次重试机会用尽，就进入了`trycatch`的`catch`块了。

<br><br><br><br>

### 二、失败后继续

<br>

如果组件出错了，但我们并不想让它抛出异常怎么办？

组件右侧的属性中基本都有一个失败后继续的选项。
该选项默认为：“否”，若改成“是”，即使出现错误，异常也不会被抛出，流程会继续执行。


<br>

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758457394983.jpg"/>

<br><br><br>


### 三、终止流程(组件)

<br>

**作用：** 遇到终止流程组件时，流程将被强行停止运行。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758457339455.jpg"/>


<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)