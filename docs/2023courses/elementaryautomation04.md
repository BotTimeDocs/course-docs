<br><br>

## 一、课程简介

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728023567035.jpg)

<br>



**课时内容：**

> * RPA第四课 (2023年)
> * 课程时长：  14分钟 ,4节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)







<br><br>

**目录：**

> 知识点1：指定元素及录制浮窗(课程时长:4分钟) 

> 知识点2：浏览器插件安装 (课程时长:2分钟)

> 知识点3：什么是选择器？(课程时长:2分钟) 

> RPA小任务：浏览器“搜索新闻”并展示 (课程时长:6分钟)

<br><br><br>



## 二、学习内容：

* 课程简介：RPA小任务——浏览器“搜索新闻”并展示 (课程时长:6分钟)
* 学习目标：掌握 ★★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”


<br><br>


### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%E5%B0%8F%E4%BB%BB%E5%8A%A1%EF%BC%9A%E6%B5%8F%E8%A7%88%E5%99%A8%E2%80%9C%E6%90%9C%E7%B4%A2%E6%96%B0%E9%97%BB%E2%80%9D%E5%B9%B6%E5%B1%95%E7%A4%BA.mp4"> </video>

<br><br><br>

### 2.2 文档教程

#### 一、练习目标：

* 自动打开bing网站，在搜索栏中搜索【今日新闻】，并抓取第一条的内容标题进行弹框展示。从而实现机器代替人工操控网页的功能。

#### 二、具体操作步骤

**第一步：**

打开云扩RPA编辑器，点击新建流程项目，项目名称为：新闻抓取。

<br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728106820958.jpg"/>

<br><br><br>


**第二步：**

在左侧组件栏中搜索【打开浏览器】，并拖入流程中。
<br>

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728106773288.jpg"/>

<br><br><br>


**第三步：**

在弹窗中的网址文本框，填写要操作的网页地址："www.bing.com"，并在组件右侧属性框中选择浏览器类型。

<br>

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728106653224.jpg"/>

<br><br>

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728106689068.jpg"/>

<br><br><br>




**第四步：**

在组件搜索框中搜索“输入文本”组件，并拖入至“打开浏览器”组件中。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728106605144.jpg"/>

<br>



<br>
<br>

> **说明：**
> 
> “打开浏览器”组件是一个容器类的组件，需要先双击“打开浏览器”组件，再把“输入文本”组件拖拽到其中。

<br><br><br>

> **提问：什么是元素？**
> * 在本Demo中，元素就是搜索框。
> * 元素是指在开发流程中拾取的界面按钮、文字、图标等内容,主要用途是模拟人类操作定位。
> 
> * 例如：若想点击”搜索“按钮，则需先拾取“搜索”按钮，在这里”搜索“按钮就是一个元素。
> 
> <br>
> 
> * 初次使用指定元素功能时，会出现弹框提示：请先安装并启用Chrome扩展；根据弹框提示操作，即可完成扩展安装。安装完成后，需要在浏览器中启用扩展（使用默认浏览器或云扩自研的浏览器 ，则无需安装扩展）。
> 
> 

<br><br><br>

**第五步：**

指定元素：搜索框。

将鼠标移至搜索框，框体高亮即代表可选中，鼠标单击，回到编辑器面板，在原【指定元素】位置出现了一张搜索缩略图，说明已经完成了搜索框定位。 

<br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728103426594.jpg"/>

<br><br><br>


**第六步：**

在文本处输入所需搜索的内容：今日新闻。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728103250210.jpg"/>

<br><br><br>


**第七步：**

拖入 【点击】组件，指定元素为搜索图标，以实现点击搜索效果。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728103173476.jpg"/>

<br><br><br>

**第八步：**

拖入【获取文本】 组件,指定元素为第一条新闻。
定位后组件出现报错 ，因为没有变量对获取到的文本进行承接。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728103096277.jpg"/>

<br><br><br>


**第九步：**

创建一个String类型的变量result，用于承接获取到的文本。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728103053015.jpg"/>

<br><br><br>


**第十步：**

拖入【确认框】组件 ，将获取到的内容用确认框弹出确认。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728103001410.jpg"/>

<br><br><br>




**第十一步：**

点击运行，出现确认框弹窗，说明流程运行成功。

<br>


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728102956872.jpg"/>


<br>


<br><br>


### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>

