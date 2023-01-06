<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

了解编辑器的界面，并尝试编辑一个简单流程后发布至控制台~ 你可以哒 学起来

<br><br>

**课时内容：**

> * RPA第二课 (2023年)
> * 课程时长：  21分钟 ,4节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> 01. 了解编辑器界面及项目基本操作 (课程时长:6分钟)<br>
> 02. RPA组件类别介绍 (课程时长:6分钟)<br>
> 03. 了解3个不同基本流程类型 (课程时长:3分钟) <br>
> 04. 简单实现一个流程并运行 (课程时长:3分钟)<br>
> 05. 调试流程并发布控制台 (课程时长:3分钟) <br>



<br><br>


## 二、学习内容：

* 课程简介：了解编辑器界面及项目基本操作 (课程时长:6分钟)
* 学习目标：熟悉 ★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br>

### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%BC%96%E8%BE%91%E5%99%A8%E7%95%8C%E9%9D%A2%20%E9%A1%B9%E7%9B%AE%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C.mp4"> </video>

<br><br><br>

### 2.2 文档教程：


<br><br>

#### 知识点1、新建项目
在编辑器开始页可以选择新建流程项目或导入项目。
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723954601793.jpg"/>



<br><br>

**第1步：** 点击新建流程项目，会出现如下弹框。


- 名称：填写该流程的项目名。项目名即为该项目所属的文件夹名。
- 位置：填写该项目在电脑上的存储位置。
- 类型：有三种可以选择，这里选择的类型决定了流程的入口文件类型，一般默认为流程图。
点击高级设置，可以选择类型和桌面录制技术（高级设置一般不需要修改）。

<img width = '400'  src =""/>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723954699684.jpg)
<br><br>

- 桌面录制技术：推荐选择UIA3。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723954792923.jpg"/>

<br><br>

**第2步：** 点击创建，即可进入编辑页面。页面正中为设计面板，左侧为构建流程所需的组件，拖拽组件进入设计面板，即可开始构建流程。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723954910176.jpg"/>


<br><br>

**第3步：** 点击左侧边栏的项目图标，即可看到该流程的项目树。
以下图为例，最顶层是项目名称“RPA基础”，下方的Main.xaml 为主流程，也是流程运行的主入口。
所有流程文件都是以xaml作为扩展名的。

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955005911.jpg"/>


该项目树属于文件夹结构，同样支持多个文件的操作，例如：文件的复制粘贴。

<br><br>

#### 知识点2、项目中的基础操作:

<br><br>

**基础操作1：项目名**

如下图所示，选中项目名，右键，即可看到菜单页。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955285279.jpg"/>



- 打开文件夹：用于打开项目所存储的文件夹
- 添加：可添加各类型的子流程或文件夹
- 导入文件：支持导入所有类型的文件
- 重命名：用于更改项目名称，完成更改后对应的文件夹也会更新为新名称
- 导出项目：可将项目导出为dgs的格式（与之对应，在开始页有导入项目，可将dgs格式的项目导入编辑器）

    <img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955404625.jpg"/>



- 引用项目：可对其他项目进行引用，之后使用调用流程组件（引用项目），来调用被引用项目内的xaml文件
- 关闭项目：点击后会关闭项目并且回到开始界面
- 项目设置：点击会出现弹框，可以设置流程的执行权限和自动化的部分通用参数

    <img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955502217.jpg"/>



- 属性：可对作者、版本号等一些基本信息进行修改

    <img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955649854.jpg"/>



<br><br><br>

**基础操作2：XAML文件：**

双击xaml文件即可在流程编辑区域打开并编辑流程文件。如图所示，右键菜单也有一些功能。
- 运行文件和调试文件：支持运行或者调试单个xaml文件。
- 从项目中排除：可将xaml文件排除到项目外，排除后将不再显示在项目树中。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955809711.jpg"/>



<br><br><br>

**基础操作3：三个点图标** 

如下图所示的三个点图标，其中有三个按钮。
- 刷新：会同步项目文件夹和项目树的文件，将文件夹中有（比如手动从其他文件夹复制过来的文件）但是项目树上没有的文件展示出来。
- 显示所有文件：可将包括在项目中和未包括在项目中的所有文件都展示出来。
- 删除未使用的屏幕截图：用来清理由自动化操作生成但没有使用的截图。

    <img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723955934873.jpg"/>





<br><br>

### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>


