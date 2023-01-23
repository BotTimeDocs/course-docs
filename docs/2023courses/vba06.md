# 第十四课(06)：RPA小任务2--Excel 大文件分割

<br><br>

## 一、课程简介

<br>

**【课程目标】**

通过对Excel内容宏的学习及掌握，最后完成一个较难的Excel大文件分割流程搭建。


<br><br>

**课时内容：**

> * RPA第十二课 (2023年)
> * 课程时长：40分钟 ,6节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1- 宏基础及 "录制办法"（课程时长：6分钟）
> * 知识点2--“宏”Sub定义 & Function函数（课程时长：4分钟）
> * 知识点3--执行宏(外部宏)--设置单元格格式（课程时长：5分钟）
> * 知识点4--执行宏(内部宏)-列宽自适应（课程时长：4分钟）
> * RPA小任务1--多条件筛选并写入新表（课程时长：6分钟）
> * RPA小任务2--Excel 大文件分割（课程时长：15分钟）

<br><br><br>

##  二、学习内容：
<br>

* 课程简介：RPA小任务2--Excel 大文件分割（课程时长：15分钟）
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<br>

> 本节课时，暂无视频。请仔细阅读下方文档教程，加油~

<br><br><br>

### 2.2 文档教程

<br>

### 一、案例背景概述

#### (1).这节课我们来说说如何用云扩RPA来切割有很多行数据的Excel文件。

> * 就像此前，在实际项目实施中，我们拿到一个有 50000 多行数据的 Excel 文件，我们在处理时，将其分隔成了多个 5000 行的文件。
> 
> * 为什么需要做这样的分割呢？一种情况是，文件太大可能会影RPA在读写文件时的速度（当然影响速度并不是RPA本身的问题，我们可以尝试手动打开一个有这么多行数据的Excel文件，速度也会很慢。）
> 
> * 另一种情况是，有些业务系统只支持一次性处理数据量有限制，比如：企查查批量查询企业信息时明确写着一次最多处理5000条数据。
> 
> * 在本课程中，你可以将已准备好的一个包含 50000+ 行数据的 Excel 文件按照用户自定义的数据行数切割为多个文件。
> 
> * 原文件包含在流程文件中，名为 `5.1万数据.xlsx`。流程运行完成后（假设文件按5000行/文件进行切割），切割为11个小文件，如图：

<br>

![image](https://alidocs.oss-cn-zhangjiakou.aliyuncs.com/res/E8K4ny5ZZZ5onLbj/img/375ab5cb-941d-44c2-8347-999f5d97db44.jpg)

如果你希望获取示例流程文件，点击[分割过大 Excel 文件](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SplitExcel/%E5%88%87%E5%89%B2%E8%BF%87%E5%A4%A7Excel%E6%96%87%E4%BB%B6.dgs)获取。

<br><br>


#### (2).流程具体实现逻辑

<br>


示例流程中使用的是如下图所示的实现逻辑，你可以参考这样的逻辑，甚至实现运行效率更高的流程逻辑。

> * 第1步、打开云扩编辑器，新建项目
> * 第2步、更改原文件名
> * 第3步、计算分割文件数
> * 第4步、从前一个文件中读取需要分割的部分
> * 第5步、新建文件并写入获取的数据
> * 第6步、从前一个文件中删除多余的数据
<br>

<img width = '200'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877298672.jpg"/>

<br><br><br>

### 二、流程搭建步骤

#### 第1步、打开云扩编辑器，新建项目

本项目命名为`切割过大Excel文件`,打开Excel文件，获取末行号、末列号。

> (1).使用_选择文件_组件，方便输入需要处理的 Excel 文件，并把文件路径存放在变量_原文件路径_中。
    
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877425656.jpg)


<br>

> (2).使用该路径文件，使用已有组件获取末行号和末列号。
>     
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877539527.jpg)


<br>

> (3).将获取的末列号数字转换为Excel中对应的列号（字母）。这边，我们使用一小段C#代码实现转换：
    
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877626718.jpg)


代码参见：
```
    StringBuilder letter = new StringBuilder();
    do {
        --num;
        int mod = num % 26; // 取余
        letter.Append((char) (mod + 'A')); // 组装字符串
        num = (num - mod) / 26; // 计算剩下值
    } while (num > 0);
    char[] arr = letter.ToString().ToCharArray();
    Array.Reverse(arr);
    line = new String(arr);
    Console.WriteLine(line);
```    

<br><br><br>

#### 第2步、更改原文件名

> (1).将分割得到的文件路径设置为_原文件名称+文件序号_的形式。
    
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877709851.jpg)


> 赋值内容是：
> `System.IO.Path.GetDirectoryName(原文件路径) + "\" + System.IO.Path.GetFileNameWithoutExtension(原文件路径) + 文件序号 +".xlsx"`

<br><br>

> (2).复制原文件，并将副本命名为文件序号为1的新文件。
    
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877821907.jpg)


<br><br><br>

#### 第3步、计算分割文件数

> 使用_循环操作（While）_组件，并输入循环条件。
> 
> 计算循环次数的思路如下：如果原文件数据有65行，且我们希望切割将其切割为含有不超过10行数据的小文件，那么需要需要切割为7个小文件（65 mod 10 + 1 = 7）。

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877921034.jpg)

<br><br><br>

#### 第4步、从前一个文件中读取需要分割的部分

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744877998346.jpg)


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744878055393.jpg)

<br><br><br>

#### 第5步、新建文件并写入获取的数据

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744878130818.jpg)


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744878253352.jpg)


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744878330290.jpg)


<br><br><br>

#### 第6步、从前一个文件中删除多余的数据

<br>

这个步骤我们可以使用云扩提供的`软件自动化->OfficeExcel->删除数据`实现。但鉴于宏的普遍应用需求，此处使用宏实现。

<br>

> (1).记得在使用_打开/新建_组件时，勾选_启用宏_属性。 

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744878405090.jpg)


<br><br>
   
> (2).录制宏并修改。在_执行宏_组件中，使用宏文件。
    
![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/23/16744878556330.png)


<br><br>

至此，整个流程已完成。

<br><br><br><br>


### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)