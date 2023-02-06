# 第十五课(04)：方式3_“非表单数据”获取

<br><br>

## 一、课程简介

<br>

**【课程目标】**



<br><br>

**课时内容：**

> * RPA第十五课 (2023年)
> * 课程时长：30分钟 ,6节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--获取结构化数据-定义(课程时长：4分钟)
> * 小任务1--方式1_整表获取“直观表格”(课程时长：5分钟)
> * 小任务2--方式2_DIY数据获取规则(课程时长：5分钟)
> * 小任务3--方式3_“非表单数据”获取(课程时长：8分钟)
> * 知识点2--结构化数据原理(课程时长：5分钟)
> * 知识点3--数据抓取如何停止？(课程时长：3分钟)




##  二、学习内容：

<br>

* 课程简介：小任务3--方式3_“非表单数据”获取(课程时长：8分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<br>

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/%E7%AC%AC%E5%8D%81%E4%BA%94%E8%AF%BE%20%E8%8E%B7%E5%8F%96%E7%BB%93%E6%9E%84%E5%8C%96%E6%95%B0%E6%8D%AE/%E5%B0%8F%E4%BB%BB%E5%8A%A13--%E6%96%B9%E5%BC%8F3_%E2%80%9C%E9%9D%9E%E8%A1%A8%E5%8D%95%E6%95%B0%E6%8D%AE%E2%80%9D%E8%8E%B7%E5%8F%96.mp4"> </video>

<br><br><br>


### 2.2 文档教程 

<br>

类似如下图这样，店铺名、评分、人均价格都是在固定的位置出现的非表单数据，同样也可以使用`获取结构化数据`组件来抓取假设我们需要抓举该页面的店名和人均.

该怎么操作呢？抓取数据的方式与获取表单类型数据大致相同。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756756161719.jpg"/>

<br><br>

**第1步：**

> 同样点击指定数据源。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756757689374.jpg"/>

<br><br><br>

**第2步：**

> 依旧根据提示框进行操作，点击：下一步。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756757889779.jpg"/>


<br><br><br>

**第3步：**

> 选择第一家店名作为第一个元素。点击下一步。
> 
> 按照提示，选择同类型的第二家店店名作为抓取的第二个元素，生成自动匹配规则。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756757935233.jpg"/>

<br><br><br>


**第4步：**

> 修改文本列名称后，点击：下一步--继续获取相关数据。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756757979515.jpg"/>



<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756758006185.jpg"/>

<br><br><br>


**第5步：**

> 选择第一家餐厅的人均价格，并根据提示抓取第二季餐厅的人均作为第二个元素。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756758062437.jpg"/>

<br><br><br>


**第6步：**

> 抓取完成后，修改文本列名称，然后点击：下一步。即可看到提取的所有数据。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756758118702.jpg"/>


<br><br><br>

**第7步：**

> 如图，获取的人均与真实人均不一致，应该是网页做了一些反爬处理。可以点击：F12，查看网站源代码，进行验证。

- 定位到人均，可以看到，代码对后两位数字进行了特殊处理，因此该网页的人均是无法自动获取的。


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756758185156.jpg"/>

<br><br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756758220309.jpg"/>


<br><br>

- 若网页不存在反爬机制，那么获取的数据则类似下图。


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756758314468.jpg"/>


<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)