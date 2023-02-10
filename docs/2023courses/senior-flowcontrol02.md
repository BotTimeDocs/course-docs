# 第十八课(02)：知识点2--抛出异常&重新抛出异常

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

* 课程简介：知识点2--抛出异常&重新抛出异常（课程时长：4分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E5%85%AB%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B92--%E6%8A%9B%E5%87%BA%E5%BC%82%E5%B8%B8%26%E9%87%8D%E6%96%B0%E6%8A%9B%E5%87%BA%E5%BC%82%E5%B8%B8.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

> 场景：当流程走到某处出现错误时，希望流程能够主动抛出异常。

<br><br>

### 一、**抛出异常组件**

<br>

> **举例：** 在一个`条件（If）`组件或`Switch`组件中，当条件不符合预期时，流程能够主动地抛出异常。这种时候就需要用到抛出异常组件。

<br><br>

**第1步：** 

* 创建一个`string`类型的变量`variable1`(或者V1), 并拖入一个`Try-catch`组件。
* `Catch`中添加一个捕获条件，并拖入一个`Swtich`组件。
* 然后在表达式处填写`V1`,在`Swtich`中填填写4个`case`（用例）：东、南、西、北。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758424648554.jpg"/>


<br><br><br>

**第2步：** 

* 在`Default`中拖入一个抛出异常的组件，并填写一个`Exception`类型的表达式。

<br>

> **参考：** 
> `new Exception("主动抛出的异常")`， 括号里面的文本是`Exception`里面的`Message`, 可以在`Catch`板块中通过`exception.Message`进行输出。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758424585528.jpg"/>


<br><br>

**第3步：** 在`Catches`中捕获异常并写入日志。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758424530849.jpg"/>

<br><br><br>


**第4步：** 运行流程。

<br>

* 可以发现流程在`Switch`组件处抛出了异常，并在捕获异常后，在`Catches`组件中通过日志显示异常。

<br><br>

> **流程逻辑复盘：**
首先，判断变量`v1`是什么？若是东南西北中的一个，就走对应的分支，每个分支中都可以使用一些其他组件，代表不同处理流程可以继续运行下去。但若不是这4个字当中的一个，那么流程就会走到`Default`分支中，然后主动抛出异常。这样流程就不会走`Switch`执行成功的写入日志组件，会直接进入`Catch`组件中。

<br><br><br>

### 二、重新抛出异常组件

<br>


> **与抛出异常组件类似，但需要注意的是：**
> 
> 重新抛出异常需要在
> `Try-Catch`的`Catches`板块中使用，它会把`Catches`已经捕获到的异常，再次抛出。
> 
> **举例：** 需要记录流程异常信息，将信息通过写入日志打出后，依旧像将异常抛出，且不想让流程继续运行时，就可以在写入日志后拖入再次抛出这个异常组件，结束流程。


<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16758423223864.jpg"/>

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)