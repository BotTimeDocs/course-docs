

<br><br>

## 一、课程简介

<br>

**【课程目标】**

* 恭喜你，晋级为RPA高手只差一步之遥! 本节课程讲带大家学习云扩编辑器中选择器定位元素的实际业务中会遇到的经典业务场景~ 
* 从Xpath开始，一起挑战下拉框、多选复选框勾选、多层iFrame嵌套网页吧~
* 最后，我们一起学习一下如何根据实际业务场景把一些复杂的业务流程直接打包成组件给一线业务非RPA开发人员使用哦~ 一起让RPA在业务里RUN起来~ 




<br><br>

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

* 课程简介：实战技能4--日期选择控件（课程时长：40分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 文档教程 

<br> 

此流程我们主要通过以下6个环节，手把手带大家搭建：
> * 环节1、流程思路搭建讲解
> * 环节2、日期参数赋值&流程结构搭建
> * 环节3、日期选择-年份
> * 环节4、日期选择-月份
> * 环节5、日期选择-天数
> * 环节6、运行流程查看结果

<br> <br>  



有些页面上的日期选择框可以直接用输入文本组件进行操作。本文主要针对那些不支持直接输入，必须通过点击才能操作的日期选择框。下面我们正式开始介绍具体流程搭建步骤。

> 本文以 AntDesign 基础日期选择框为例，选择指定日期。

<br> <br>  <br> <br>  


#### 环节1.流程思路搭建讲解

<br>

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/1.%E6%B5%81%E7%A8%8B%E6%80%9D%E8%B7%AF%E6%90%AD%E5%BB%BA%E8%AE%B2%E8%A7%A3.mp4"> </video>

<br><br>

**(1).操作思路**
* 指定日期后，在页面中依次选择年，月和日。

<br>

**(2).前提条件**
* 已打开[AntDesign](https://ant.design/components/date-picker-cn/)基础日期选择框。

<br><br><br>

#### 环节2.日期参数赋值&流程结构搭建

<br>

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/2.%E6%97%A5%E6%9C%9F%E5%8F%82%E6%95%B0%E8%B5%8B%E5%80%BC%26%E6%B5%81%E7%A8%8B%E7%BB%93%E6%9E%84%E6%90%AD%E5%BB%BA.mp4"> </video>

<br>

把我们需要指定的时间分别保存在 `年`，`月`，`日` 三个变量中。
* 拖入`流程图`组件，重命名为获取年月日：
* 在流程图中，设置字符串型变量`年`与参数`年份增量`。
* 拖入`赋值`组件，赋值左侧为变量`年`，右侧为 `System.DateTime.Now.AddYears(年份增量).ToString(*yyyy*) `

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756669504472.jpg)

<br>

* 以同样方法指定月份及日期。添加以下变量：
    * 月；
    * 日；
    * 月份增量；
    * 日期增量。

<br>


赋值代码为：
* 月：`System.DateTime.Now.AddMonths(月份增量).ToString("MM").TrimStart('0')`
* 日：`System.DateTime.Now.AddDays(日期增量).ToString("dd")`

<br><br>

> **说明：**
> 
> 本案例中打开的网页支持显示日为“01”的格式，若打开的网页不支持显示此格式，需使用`System.DateTime.Now.AddDays(日期增量).ToString(*dd*).TrimStart('0')`，以去除个位上的`0`。

<br>

点击日期选择框，拖入`点击组件`，指定日期输入框元素。分别拖入3个`点击组件` ，完成`年`、`月`、`日`的三次点击指定。

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756676996080.jpg)

<br><br><br>

#### 环节3.日期选择-年份

<br>

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/3.%E6%97%A5%E6%9C%9F%E9%80%89%E6%8B%A9-%E5%B9%B4%E4%BB%BD.mp4"> </video>

<br> 

* 拖入点击组件，点击年份,打开年份选项框。

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756684408503.jpg)

<br><br>

* 拖入获取结构化数据组件，获取该面板所有年份。查看指定年份是否包含在内。如果不包含，则点击上一页或者下一页按钮翻页）：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756684608885.jpg)

<br><br>

* 拖入C#组件，从上步获取的数据表中循环查找指定年份。如果包含，则赋值isTrue为true，为下一步做准备：
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756684941754.jpg)

<br>

【附】查找年份代码：


```
isTrue=false;
for(int&nbsp;i=0;i\<dt.Rows.Count;i++){
    for(int&nbsp;j=0;j\<dt.Columns.Count;j++){
        if(dt.Rows[i][j].Equals(年)){
        i=i+1;
        j=j+1;
        isTrue=true;
        break;
    }else{
        continue;
        }
    }
}
```

<br>

* 使用流程决策组件，根据 isTrue 判断下一步操作： 

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756686136772.jpg)

<br><br>

* 如果isTrue为真（上步中查询到预期年份），则直接点击选中年份; 如果未查到年份，则点击翻页。

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756686926701.jpg)


<br><br><br>

#### 环节4.日期选择-月份

<br>


<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/4.%E6%97%A5%E6%9C%9F%E9%80%89%E6%8B%A9-%E6%9C%88%E4%BB%BD.mp4"> </video>

* 使用赋值组件，拼接月份： 

 <br>
 
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756687248881.jpg)


<br><br>

* 打开月份选择框： 

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756687847427.jpg)

<br><br>

* 点击指定月份: 
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756688312267.jpg)

<br><br><br>

#### 环节5.日期选择-天数

<br>

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/5.%E6%97%A5%E6%9C%9F%E9%80%89%E6%8B%A9-%E5%A4%A9%E6%95%B0.mp4"> </video>

<br>

点击指定日期：

<br>
 
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756688596375.jpg)



<br><br>

**注意：** 

当日期界面同时存在 两个日期 如下图所示 ，需要使用到我们之前学习的Xpath语言，具体代码示例，如下:

```//table[@class='ant-picker-content']//td[contains(@class,'ant-picker-cell-in-view')]/div[text()='{{日}}']```

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/06/16756700025474.jpg)


<br><br><br>

#### 环节6.运行流程查看结果

<br>

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E6%97%A5%E6%9C%9F%E6%8E%A7%E4%BB%B6%E9%80%89%E6%8B%A9/6.%E8%BF%90%E8%A1%8C%E6%B5%81%E7%A8%8B%E6%9F%A5%E7%9C%8B%E7%BB%93%E6%9E%9C.mp4"> </video>

至此，整个流程已完成

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)