# 第九课(02)：知识点2--选择文件/文件夹 


<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

* 通过对文件自动化组件的进一步学习，结合之前学过的知识点：最终完成“批量重命名文件并另存”以及“在Chrome下载文件至指定路径”两个RPA流程搭建，过程中请熟悉与掌握流程构建的设计思路。


<br><br>

**课时内容：**

> * RPA第九课 (2023年)
> * 课程时长：30分钟 ,6节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--文件/文件夹是否存在 (课程时长:2分钟)
> * 知识点2--选择文件/文件夹 (课程时长:3分钟)
> * 知识点3--遍历文件夹 (课程时长:2分钟)
> * 知识点4--获取文件/文件夹列表 (课程时长:3分钟)
> * RPA小任务1--批量重命名文件并另存 (课程时长:6分钟)
> * RPA小任务2--Chrome下载文件至指定路径 (课程时长:14分钟)


<br><br><br>



##  二、学习内容：
<br>

* 课程简介：知识点2--选择文件/文件夹 (课程时长:3分钟)
* 学习目标：掌握 ★★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E4%B9%9D%E8%AF%BE/%E7%AC%AC%E4%B9%9D%E8%AF%BE%2802%29%EF%BC%9A%E7%9F%A5%E8%AF%86%E7%82%B92--%E9%80%89%E6%8B%A9%E6%96%87%E4%BB%B6%E6%96%87%E4%BB%B6%E5%A4%B9%20.mp4"> </video>

<br><br><br>

### 2.2 文档教程

#### 一、组件概述

<br>

* 某些场景下，需要先人工在流程运行中选择文件，再进行后续的操作。


<br><br>

#### 二、组件属性

<br>

**<1>.输出**

* 选择文件和选择文件夹组件会在运行时弹出选择框，然后返回被选择的文件或文件夹的绝对路径作为输出。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736099780934.jpg"/>


<br><br><br>

**<2>.可选项**

- 文件筛选：确定筛选的文件类型。

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736100304088.jpg"/>

<br><br><br>


**<3>. 描述**：所输内容为弹框提示语，如下图左上角所示。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736100423954.jpg"/>


<br><br>

**<3>.使用示例**

此流程执行逻辑：指定一个固定的文件路径，判断该文件路径是否存在，将返回结果保存至 exists 变量中。

<img width = '600'  src =""/>

<br><br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)





