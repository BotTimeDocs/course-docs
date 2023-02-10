# 第十八课(01)：知识点1--TryCatch(容错组件)的定义及作用

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

* 课程简介：知识点1--TryCatch(容错组件)的定义及作用（课程时长：5分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B91--TryCatch%28%E5%AE%B9%E9%94%99%E7%BB%84%E4%BB%B6%29%E7%9A%84%E5%AE%9A%E4%B9%89%E5%8F%8A%E4%BD%9C%E7%94%A8.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

### 一、 什么是容错组件？

<br>

> **定义：** 
> 
> 当流程的组件在运行中出错时，会抛出一个异常；如果不去处理，流程即会中止。 
> 
> 如果我们不希望流程中止，就要让流程自己去处理错误，这时候就需要用到容错组件。
> 
> 首先我们来了解学习“错误捕获组件”（Try-Catch）

<br><br>

**什么是错误捕获（Try-Catch）？**

`Try-Catch`组件由三个部分构成，分别是`Try`、`catch`和`finally`。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758402761547.jpg"/>

<br><br>

* `Try`：一般放置常规要去执行的流程，若在执行的过程中出现错误，那么流程就会进入到Catch环节，在`Catch`中针对报错进行处理。

* `Catches`：放置对所捕获错误进行的相应处理。

* `Finally`：在`try-catch`执行完后去执行（不管`try`里面是正常执行完还是报错跳进了Catch里）。通常会放一些对流程进行清理的组件，比如：关闭某些应用程序...

<br><br>


> **注意：** 如果在`try`中放了三个组件，当执行到第二个组件时遇到报错会立马进入`Catch`中，第三个组件就不会执行了。

<br><br><br>

### 二、错误捕获（Try-Catch）使用说明

<br>

**第1步：** 拖入`写入日志`组件。

<br>

创建一个`string`类型的变量`variable1（v1）`，不填写默认值（人为创造一个报错）。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758402880406.jpg"/>


<br><br><br>

**第2步：** 尝试打印出变量`v1`的`Substring`（从第二个字符开始的`string`）。
<br>若`v1`的值为：`123`，则`v1.Substring(1)`会打印出23。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758402970223.jpg"/>


<br><br><br>

**第3步：** 运行流程，发现报错。
<br>因为没有设置`v1`的默认值，所以当写入日志获取其`Substring`时，是无法获取到值的。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758403116261.jpg"/>

<br><br><br>

**第4步：** 将报错组件放入`Try-Catch`组件的`Try`板块。
并在`Catches`中选择需要捕获的`Exception（错误）类型`。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758403205670.jpg"/>

<br><br>

> **注意：** 当无法确定流程的报错类型时，可以选择获取所有异常的System.Exception。

<br><br><br>

**第5步：** 拖入写入日志组件至`Catches`，作为错误提醒。
并在写入日志中填写提醒信息：`"流程出现异常：" + exception.Message`

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758403352598.jpg"/>

<br>

> **注意：** 在`Catches`中抓到的错误会被放入如图右上方的`Exception`载体中，可以通过`exception.Message`提取错误信息。

<br><br><br>

**第6步：** 拖入写入日志组件至`Finally`，执行清理动作。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758403475607.jpg"/>


<br><br><br>

**第7步：** 运行该流程。
即可看到流程捕获的错误信息及`Finally`中日志打印的`“清理流程”`。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758403521566.jpg"/>

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)