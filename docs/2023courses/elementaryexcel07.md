<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

通过对EXCEL基础RPA组件的学习及使用，完成一个经典RPA自动化流程。通过RPA将网页上EXCEL表格抓取后存入本地Excel。

<br><br>


<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728188101649.jpg"/>



**课时内容：**

> * RPA第五课 (2023年)
> * 课程时长：  27分钟 ,7节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)



<br><br>

**目录：**

> 知识点1：EXCEL基础概念 (课程时长:2分钟)
> 
> 知识点2：“打开新建”组件 (课程时长:6分钟)
> 
> 知识点3：“读取区域”组件 (课程时长:5分钟)
> 
> 知识点4：“写入区域”组件 (课程时长:5分钟)
> 
> 知识点5：“获取末行号”组件 (课程时长:3分钟)
> 
> 知识点6：3种常见EXCEL处理方式 (课程时长:3分钟)
> 
> RPA小任务：数据录入EXCEL (课程时长:3分钟)

<br><br><br>



## 二、学习内容：

* 课程简介：RPA小任务—— 数据录入EXCEL (课程时长:3分钟)
* 学习目标：掌握 ★★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”


<br><br>


### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%E5%B0%8F%E4%BB%BB%E5%8A%A12%EF%BC%9A%E6%95%B0%E6%8D%AE%E5%BD%95%E5%85%A5EXCEL.mp4"> </video>

<br><br><br>

### 2.2 文档教程


<br>

#### 一、案例概述：

<br>

**（1）案例流程概述：** 从网页获取的数据并存储到本地Excel文件中

<br>


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728303015852.jpg"/>

<br><br>

如上图这种表格式的数据就比较适合存储到Excel中，因为它肉眼看上去就是excel表格的格式。人工手动操作获取填写非常浪费时间,但用RPA组件可以轻松并且高效地自动获取~

<br><br>

**（2）RPA自动化流程步骤梳理：**

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728302739518.jpg"/>



<br><br>

**（3）涉及组件**
- 打开/新建
- 打开浏览器
- 点击
- 获取结构化数据
- 保存数据

<br>

<img width = '300'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728306316110.jpg"/>



<br><br>

#### 二、具体操作步骤

<br>

**第一步：打开浏览器界面**

打开浏览器并进入需要转换为Excel的网页；

<br><br>

**第二步： 网页数据抓取_获取结构化数据**

* 【步骤说明】此步骤主要实现从网页中用获取结构化数据组件获取到相应数据，输出的是一个数据表:可以用预览数据表查看数据正确性；

* 【具体实现过程】
    - 涉及组件：获取结构化数据
    - 操作步骤：拖入获取结构化数据组件，在网页中框选需要抓取的表格类数据，系统会自动识别相似元素，抓取成Datatable。

<br><br>

**第三步：把数据存入Excel文件**
<br>

存储到Excel文件中,文件的名字规则可以自己定义,打开/新建组件勾选新建文件；

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728306641844.jpg"/>


<br><br>

**第四步：Excel数据处理**

<br>

对数据进行相应的处理,比如：排序，设置单元格格式,透视表...都有相应的组件;

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/04/16728308958493.jpg"/>




<br><br>

**（5）案例小节**

<br>


> **补充说明:**
> 若需要获取网页表格类数据对应的链接，可以尝试使用f12，侧边栏可以看到href，之后点击获取更多数据-新增，选择href即可。
> 
> **注意要点:**
> 使用Excel相关组件时需要先关闭Excel。



<br><br>


### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>
