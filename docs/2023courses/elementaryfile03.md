<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

* 通过对基础文件/文件夹分类组件的学习，完成一个文件自动化RPA流程
* 任务名称：读取txt文件A的内容到txt文件B。

<br><br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/05/16729117059516.jpg"/>

<br><br>

**课时内容：**
<br>

> * RPA第六课 (2023年)
> * 课程时长：  25分钟 ,5节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>

**目录：**

> * 知识点1：组件--新建文件/文件夹 (课程时长:5分钟)
> * 知识点2：组件--删除文件/文件夹 (课程时长:2分钟)
> * 知识点3：组件--压缩&解压文件   (课程时长:3分钟)
> * 知识点4：相对路径 VS 绝对路径 (课程时长:5分钟)
> * RPA小任务：读取txt文件 (课程时长:5分钟)

<br><br>

## 二、学习内容：

* 课程简介：组件--压缩&解压文件   (课程时长:3分钟)
* 学习目标：掌握 ★★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br>


### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%85%AD%E8%AF%BE/%E7%BB%84%E4%BB%B6%EF%BC%9A%E5%8E%8B%E7%BC%A9%E8%A7%A3%E5%8E%8B%E6%96%87%E4%BB%B6.mp4"> </video>



### 2.2 文档教程：

<br>

### （1）组件：压缩文件/文件夹

<br><br>

#### 一、组件概述

<br>

该组件实现对指定的文件/文件夹压缩成 ZIP 文件。

<br><br>

#### 二、组件属性

<br><br>

**<1>.输入**

- 列表模式：选择所需压缩的类型，支持文件和文件夹类型。
- 路径列表：所需压缩的文件/文件夹路径（可多选），支持相对路径和绝对路径。
- 压缩文件路径：压缩后的文件/文件夹的保存路径，文件名需以 zip 结尾。


<br><br>

**<2>.可选项**

  - 密码：输入压缩密码，可接变量，也可与设置密码组件配合使用。
  - 同名替换：默认不勾选，勾选时将替换同名文件。

<br>

<br><br>

**<3>.使用示例**

此流程执行逻辑：将桌面上的 `test.xlsx` 文件压缩成 `test.zip` 文件保存至桌面上。

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736087307600.jpg"/>

<br><br>

执行结果：

<img width = '100'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736090135537.jpg"/>


<br><br><br>

> **Tips:**
> 
> Q：压缩文件/文件夹组件的【路径列表】属性，使用变量时怎么设置值？
> 
> A：【路径列表】的数据类型是 List，变量值设置格式为 new List (){"路径 1", "路径 2", "路径 3"}，其中的路径 1、路径 2 和路径 3 为你需要压缩的具体文件/文件夹路径。

<br><br>


### （2）组件：解压缩文件

<br><br>

#### 一、组件概述

<br>
对指定的ZIP或 RAR 压缩文件进行解压缩。。

<br><br>

#### 二、组件属性

<br><br>

**<1>.输入**

* 解压至文件夹：选择或输入需要解压到的文件夹路径，支持相对路径或绝对路径。
* 压缩文件路径：选择需要被解压的压缩文件路径，支持相对路径或绝对路径。

<br><br>

**<2>.可选项**

* 密码：输入压缩密码，可接变量。可与 设置密码 组件配合使用。
* 同名替换：有同名文件是否替换。

<br>

**<3>.使用示例**

此流程执行逻辑：将桌面上的`test.rar文件`，解压至桌面。

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736091628247.jpg"/>

<br><br>

**执行结果：**

<img width = '100'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736091759352.jpg"/>

<br><br>

### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>
