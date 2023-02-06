# 第十六课(05)：实战技能3--多层嵌套表格

<br><br>

## 一、课程简介

<br>

**【课程目标】**

* 恭喜你，晋级为RPA高手只差一步之遥! 本节课程讲带大家学习云扩编辑器中选择器定位元素的实际业务中会遇到的经典业务场景~ 

<br>

* 从Xpath开始，一起挑战下拉框、多选复选框勾选、多层iFrame嵌套网页吧~

<br>

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

* 课程简介：实战技能3--多层嵌套表格（课程时长：25分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 文档教程 

<br>

我们在流程开发中往往会遇到web页面的很多table类元素进行处理的问题，一般我们在网页上需要获取的table（例如`n*m`类型）表格时，我们可以很方便地借助编辑器中的`获取结构化数据`组件来实现`table`获取。

但是我们也会遇到`多层table嵌套`导致无法一次性获取整个table然后进行数据处理的情况，下面我们将对这种情况进行探讨。

<br><br>

> <font color =red >**重点：**  获取结构化数据不成功？</font> 
> 
> 页面看起来是一个表格，实际上网页结构不规则 存在多级层级嵌套 如何解决 ？ 应该如何解决？
> 
> <br>
> 
> 注意：本节课内容属于高级自动化课程，面向高级RPA实施或企业内部有一定开发代码基础的技术流程开发者。


<br><br><br>

#### 一、准备工作 


* 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的[硬件&软件要求](https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?%EF%BC%89%E3%80%82)
* 打开[云扩官网](https://www.encoo.com/)下载编辑器并安装。

<br><br><br>

#### 二、案例介绍

用云扩RPA来进行多层 table 嵌套的 web 表格处理，表格举例如下：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753330141450.jpg)

网页源码：
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753335062713.jpg)


在上述例子中，假设我们需要获取网页中这个表格的最后一列，**如果我们使用`获取结构化数据`组件来处理，则无法实现整个`table`数据的正常获取**，此时我们就可以使用如下思路来解决问题。

<br><br><br>

#### 三、操作流程

<br>


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753914986975.jpg)


<br><br><br>

#### 四、操作步骤

<br>

* **第1步**：打开云扩编辑器，新建项目


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753926549536.jpg)

<br><br>

* **第2步**：添加`打开浏览器`组件，配置需要处理的网页URL



![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753926799195.jpg)

<br><br>

* **第3步**：添加`获取元素`组件，获取整个table最外层元素信息


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753926937173.jpg)

<br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753927026006.jpg)

<br><br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753927068958.jpg)


<br><br>

* **第4步**：将获取元素的输出结果赋值给新`变量h`(选中`变量h`，按`Ctrl+B`可以快速自动创建`变量h`)


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753927568230.jpg)


<br><br>

* **第5步**：为了更明显地展示从web端获取的数据，这里新建一个`datatable`，配置一个列(`string`类型，我们假设只需要获取网页中一列数据)，来接收网页`table`获取的所有结果

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753927871105.jpg)

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753927923799.jpg)
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753927978055.jpg)

<br><br>

* **第6步**：通过C#代码来处理获取`table`的元素(即`变量h`)

<br>

```
try
{
  // 使用Html Agility Pack开源组件来进行Html解析
  string htmlCode = (h.GetProperty("innerHTML")).ToString();
  HtmlAgilityPack.HtmlDocument doc = new HtmlAgilityPack.HtmlDocument();
  doc.LoadHtml(htmlCode);
  // 遍历需要获取的信息的节点
  // 此处的SelectNodes中Xpath为页面获取元素的这段源码中，需要获取的节点信息的xpath路径
  // 请实际使用中用谷歌F12+ Ctrl + F在最下面的输入框中进行调试
  foreach (HtmlNode row in doc.DocumentNode.SelectNodes("//table//table//table//tr")) 
  {  
    //将节点信息添加到数组中
    string[] tdArr = row.SelectNodes("td").Select(td => td.InnerText).ToArray();
    // 通过判断条件进行数据信息筛选，此处我们假设我们需要筛选数据内容是字符"2"结尾的内容
    if (Convert.ToInt32(tdArr[0].Substring(tdArr[0].Length - 1)) == 2)
    {
    // 将筛选内容添加到datatable中
    table.Rows.Add(tdArr);
    }    
  }
}  
catch(System.Exception e)
{
  Console.WriteLine(e.Message.ToString());
}
```


<br><br>


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753928347098.jpg)


<br><br>

* **第7步**：我们使用组件`预览数据表`来查看处理结果

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753928531436.jpg)

<br>

至此，从多层嵌套的table中获取不固定数据的流程已开发完成，保存并运行流程并查看“结果对比”：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753928633394.jpg)


<br><br><br>

#### 五、后续操作步骤

<br>

我们看到执行过程只是简单的进行对多层table这一段源码进行遍历操作，使用的是节点筛选，当我们这里需要处理多个页面时，只要保证这个table嵌套的架构一致，

那么我们网页中的节点td(也就是说最后一列的数据)可以是动态的，可以是1行数据，也可以是100行数据，我们都可以通过Xpath模糊查询的结果来进行筛选出来。

<br>

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753928937668.jpg)


<br><br>

综合上面所讲的，我们可以发散，这不仅仅是table可以这样操作，我们这个html的思路，可以使用到任何html页面中想爬取的类似结构，例如下图中情况：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753929837494.jpg)


<br><br><br>

#### 六、课后练习

<br>

>  * 本节课时 ，针对训练网站 —— [云扩RPA闯关，第12题《获取多表格嵌套数据》](http://rpatest.chinaeast2.cloudapp.chinacloudapi.cn/main/topicdetail/8) 
> 
>
>  ![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/03/16753331649591.jpg)

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)