


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

* 课程简介：知识点3--遍历文件夹 (课程时长:2分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E4%B9%9D%E8%AF%BE/%E7%AC%AC%E4%B9%9D%E8%AF%BE%2803%29%EF%BC%9A%E7%9F%A5%E8%AF%86%E7%82%B93--%E9%81%8D%E5%8E%86%E6%96%87%E4%BB%B6%E5%A4%B9.mp4"> </video>

<br><br><br>

### 2.2 文档教程


#### 一、组件概述

<br>

* 用于遍历指定的文件夹并获取文件路径，可在此组件范围内根据实际业务需要拖入其他组件。

<br><br>

#### 二、组件属性

<br>

**<1>.输入**

* - 文件夹 ：输入要遍历的文件夹路径，支持绝对和相对路径，可承接变量。

<br><br><br>

**<2>.可选项**

- 文件筛选 ：输入所需筛选的文件类型，默认为空即获取所有文件；该项支持通配符`*` 和 `?`或指定文件名称，例如：`*.xls` 或 `?.jpg`
- 遍历子文件夹 ：默认不勾选，勾选后将遍历指定“文件夹”下的子文件夹。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736104414586.jpg"/>

<br><br>

* 如下图所示，遍历文件夹实则为一个循环体，可遍历该路径下的所有文件，进行相对应的操作。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736104591838.jpg"/>

<br><br>


* 放入写入日志组件，即可打印出每一个filePath。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736104770383.jpg"/>

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736104821372.jpg"/>

<br><br><br>



![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)






