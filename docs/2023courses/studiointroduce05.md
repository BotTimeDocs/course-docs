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

* 课程简介：调试流程并发布控制台 (课程时长:3分钟)
* 学习目标：掌握 ★★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br>

### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E8%B0%83%E8%AF%95%E6%B5%81%E7%A8%8B%E5%B9%B6%E5%8F%91%E5%B8%83%E6%8E%A7%E5%88%B6%E5%8F%B0.mp4"> </video>

<br><br><br>

### 2.2 文档教程：

<br><br>

想要调试流程，需要先设置一个断点。

断点(作用):在流程调试时，可使流程停在设置断点的组件上。

<br><br>


**知识点1、如何设置断点？**

第1步：在该流程中，右击条件（If）组件即可在菜单页找到“断点”。也可通过点击组件+F9设置断点。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967277621.jpg"/>


<br><br>

第2步：当组件左侧出现如下图标，说明断点设置成功。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967359315.jpg"/>


<br><br>

第3步：点击上方工具栏的调试按钮或左侧边框的调试标签，即可切换到调试面板。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967451351.jpg"/>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967485781.jpg"/>

<br><br>

> 注意：在调试面板中会显示当前用到的变量；下方则会显示设置的断点数量。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967572342.jpg"/>


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967605461.jpg"/>


<br><br>

第4步：进入调试模式后，可根据需求在上方工具栏的调试按钮中进行选择。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723967687895.jpg"/>


- **继续**：流程继续运行。
- **停止**：停止调试。
- **单步执行（F11）**：指一步步执行组件，包括在序列或者流程图内包含其他组件的容器型组件，单步执行可以执行容器类组件内的组件。
以条件（If）组件为例，单步执行可由条件（If）组件跳至其内的写入日志组件。
- **单步跳过**：不会对序列或者流程图中容器类组件内部的组件进行调试。
- **单步跳出**：跳出当前范围。
- **重试 & 忽略**：在流程报错时才可使用。

<br>

> **注意：** 调试过程中可对变量的值进行更改。

<br><br>

第5步：再调试中修改v1的值为：11。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723968072974.jpg"/>


<br><br>

第6步：重新运行流程，即可在输出日志中看到不同的内容。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723968156458.jpg"/>


<br><br><br><br>

**知识点2、流程发布**

编辑好流程并且调试完毕后，即可发布流程，支持发布到控制台、流程市场和机器人。

<br>

**如图，发布按钮在最上面的菜单栏。**

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723968304498.jpg"/>



<br><br>

**那么，如何将流程发布到控制台？**

**第1步：** 点击发布，选择控制台。

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723968579222.jpg"/>



<br><br>

**第2步：** 填写弹窗内容并点击发布。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/30/16723968677278.jpg"/>



<br><br>

**第3步：** 系统验证流程有效性，通过即会在页面右下角进行显示"流程发布成功"。

<br><br>

### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>


