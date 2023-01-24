

<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>
本节课程主要通过对选择器的内容节点信息的深入学习，带大家一起学会选择器的基本编辑与使用、什么是动态元素、如何寻找稳定元素特征值？


<br><br>

**课时内容：**

> * RPA第十二课 (2023年)
> * 课程时长：58分钟 ,7节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>

**目录：**

> * 知识点1-- (实战必学)选择器&自动化原理（课程时长：6分钟）
> * 知识点2-- 找不到元素? 初识"动态元素"（课程时长：5分钟）
> * 知识点3-- 元素不稳定?巧用"元素探测器"（课程时长：5分钟）
> * 知识点4--选择器必知必会-3个用法（课程时长：2分钟）
> * 知识点5--选择器方法1-通配符（课程时长：2分钟）
> * 知识点6--选择器方法2-变量（课程时长：8分钟）
> * 案例实战：抓取电商平台商品数据（课程时长：30分钟）


<br><br><br>



##  二、学习内容：
<br>

* 课程简介：知识点2-- 找不到元素? 初识"动态元素"（课程时长：5分钟）
* 学习目标：熟悉 ★★
* 难易程度：较难 ★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%89%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B92--%20%E6%89%BE%E4%B8%8D%E5%88%B0%E5%85%83%E7%B4%A0%20%E5%88%9D%E8%AF%86%E5%8A%A8%E6%80%81%E5%85%83%E7%B4%A0.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

> 【思考】
> * 🤔在录制Web元素时，编辑器会自动使用内置特征值提取算法，提取出精简可以唯一定位元素的特征值，可以供用户直接使用；
> 
> * 但是当Web网站更新、或者目标元素动态变化时，自动算法提取的特征可能无法保证继续稳定定位目标元素，这时候就需要用户手动来寻找目标元素的稳定特征值；
> 
> * 本节课程内容，我们会介绍快速寻找Web自动化中目标元素稳定特征值的方法，并结合相关案例手把手教会你怎么使用这些方法；

<br><br>

### （1）首先介绍特征值基本概念：
<br>

Web元素特征值主要包含两方面：
1. web元素节点属性特征； 
2. web元素节点位于HTML Dom树中的结构特征。

以下方表单录入窗口为例，假使现在我们的目标元素是姓名输入框：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743839144386.jpg)

**1. Web元素节点属性特征；**
即目标元素上的自身节点属性信息；如图上的 目标节点tag = input; name=name; type=text; class='form-control clo-sm-8'；
<br>

**2. Web元素节点结构特征；**
即目标元素在Dom树中的位置信息，如上图中目标元素所在的div父标签，位于form元素中的位置索引是1；
 
<br><br>

### （2）寻找目标元素的稳定特征值方法介绍

1. 从目标元素节点属性上寻找稳定的定位特征值；
2. 结合目标元素结构特征值完成稳定定位；
3. 借助具有稳定定位特征的邻居节点、兄弟节点、子节点来完成对目标节点的定位；

<br><br>

### （3)选择合适的方式来描述目标元素特征值

* a). Web自动化定位元素支持 普通Selector 以及Xpath两种模式；这两种模式都可以用来描述目标元素特征；区别如下

* b).普通Selector:云扩根据经验总结提取出10+常见属性特征以及云扩自定义属性，可以供用户快速使用，降低用户的使用门槛，适合绝大多数场景下的元素元素定位需求；

* c).Xpath模式：Xpath是标准的结构化查询语言，内置丰富的语法、高阶函数可以提供非常强大的目标元素特征描述能力，当然有一定的使用门槛；

<br><br>

### （4）实战举例

#### 小案例1：通过“百度一下”了解什么是特征值？什么是稳定特征值？

>【场景描述】
>* 先举一个简单的例子：定位 百度搜索页面的 “百度一下”这个button:
>* 假定 这个ID是动态变化的，这时候就需要人为介入，来寻找特征值；

<br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743843916311.jpg)


编辑器自动采集到的特征值：
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743844073168.jpg)

**假定这个ID是动态变化的，这时候就需要人为介入，来寻找特征值；**

* 观察发现 目标节点上的“百度一下”文字比较稳定，即便网页改版，这个文字 一般情况是不会变化的；
* 所以就可以确定Input 这个tag + 百度一下 这个文字可以作为稳定的特征值；

    * 选择器编辑器下： 文本特征对应sinfo —— 适合新手的办法
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743844158131.jpg)

    - xpath模式下可以用xpath的语法来完成定位 —— 适合进阶熟悉之后的使用办法
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743844215399.jpg)


<br><br><br>

#### 小案例2： [云扩RPA闯关](http://rpatest.chinaeast2.cloudapp.chinacloudapi.cn/main/topicdetail/5) 动态元素变化怎么办？



<br>

>【场景描述】
> * 定位姓名这个输入框，自动录制后刷新页面，会发现运行就会找不到元素；
> * 我们打开选择器看一下发现ID 是一直动态变化；
> * 具体网址，请登录后查看： http://rpatest.chinaeast2.cloudapp.chinacloudapi.cn/main/topicdetail/5

<br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743848229938.jpg)


<br><br>

打开F12看下目标节点的特征：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743849250830.jpg)

<br><br>

会发现在dom结构上，目标元素是处在 这个是个table布局的表单内，姓名是出现在第一行，而且比较稳定；

所以 该元素的特征值即使 tag + 表格第一行(结构特征)

<br><br>

* 选择器办法 —— 适合新手的办法
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743849401511.jpg)

<br><br>

* Xpath办法—— 适合进阶熟悉之后的使用办法
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/22/16743849533954.jpg)


<br><br><br><br>


### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)