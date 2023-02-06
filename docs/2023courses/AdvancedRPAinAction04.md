# 第十六课(04)：实战技能2--多选复选框

<br><br>

## 一、课程简介

<br>

**【课程目标】**

* 恭喜你，晋级为RPA高手只差一步之遥! 本节课程讲带大家学习云扩编辑器中选择器定位元素的实际业务中会遇到的经典业务场景~ 

<br>

* 从Xpath开始，一起挑战下拉框、多选复选框勾选、多层iFrame嵌套网页吧~

<br>

* 最后，我们一起学习一下如何根据实际业务场景把一些复杂的业务流程直接打包成组件给一线业务非RPA开发人员使用哦~ 一起让RPA在业务里RUN起来~ 




<br><br>

**课时内容：**

**课时内容：**

> * RPA第十六课 (2023年)
> * 课程时长：130分钟 ,6节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 选择器方法3-“XPath”（课程时长：30分钟）
> * 宝藏网址”云扩RPA闯关”（课程时长：5分钟）
> * 实战技能1--下拉框选项（课程时长：15分钟）
> * 实战技能2--多选复选框（课程时长：15分钟）
> * 实战技能3--多层嵌套表格（课程时长：25分钟）
> * 实战技能4--日期选择控件（课程时长：40分钟）


<br><br><br>


##  二、学习内容：

<br>

* 课程简介：实战技能2--多选复选框（课程时长：15分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 文档教程 

<br>

在网页自动化操作过程中，有时会遇到勾选多个复选框的场景，当我们需要勾选的复选框不固定时，如果流程中直接通过点击组件的`指定元素`勾选复选框不利于复用流程，在这种情况下，我们需要自定义勾选复选框参数，那么，具体怎么操作呢？

<br>

接下来，我们介绍流程开发的详细步骤及思路。

<br><br>

#### 一、准备工作

* 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的[硬件&软件要求](https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?%EF%BC%89%E3%80%82)
* 打开[云扩官网](https://www.encoo.com/)下载编辑器并安装。

<br><br><br>

#### 二、流程设计图示：

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753307841565.jpg"/>

<br><br><br>

#### 三、结果预期：

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753308202751.jpg"/>

<br><br><br>

#### 四、流程操作步骤：

<br>

* **第1步**：创建项目，命名为“勾选复选框”：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753308622554.jpg)


<br><br>

* **第2步**：拖入打开浏览器组件，并配置需要选择复选框的网页：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753308769994.jpg)

<br><br>

* **第3步**：拖入赋值组件，来接收自定义参数的列表内容：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753308926590.jpg)

<br><br>


* **第4步**：拖入循环操作（For Each） 组件，来遍历每一个需要勾选的参数值：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753309076399.jpg)


<br><br>

* **第5步**：观察网页中每个复选框的xpath路径：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753309386162.jpg)


<br><br>

* **第6步**：拖入赋值组件，来接收每次拼接的xpath内容：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753309561244.jpg)


<br><br>

* **第7步**：拖入勾选组件，并设定元素xpath，xpath为上步操作的拼接值，其中包含变量：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/02/16753309953524.jpg)

<br><br>


* **至此，** 勾选多个用户指定复选框的流程已开发完成，保存并运行查看结果。

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)