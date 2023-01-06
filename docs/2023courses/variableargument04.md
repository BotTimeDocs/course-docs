<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

通过对变量、参数及RPA数据类型的学习，完成用RPA组件模拟搭建一个模拟实现计算器功能流程。冲吧~

<br><br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727351319863.jpg"/>



<br>

**课时内容：**

> * RPA第三课 (2023年)
> * 课程时长：  20分钟 ,7节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)







<br><br>

**目录：**

> RPA小任务：模拟计算器功能 (课程时长:5分钟)

> 知识点1：变量的定义及其创建办法 (课程时长:3分钟) 

> 知识点2：变量的范围及包含关系 (课程时长:2分钟)

> 知识点3：常用的RPA数据类型 (课程时长:3分钟) 

> 知识点4：参数——流程间传递数据 (课程时长:3分钟)

> 知识点5：参数 VS 变量 (课程时长:2分钟)

> 知识点6：表达式编译器 (课程时长:2分钟)

<br><br><br>



## 二、学习内容：

* 课程简介：常用的RPA数据类型 (课程时长:3分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”


<br><br>


### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E5%B8%B8%E7%94%A8%E7%9A%84RPA%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B.mp4"> </video>




<br><br>

### 2.2 文档教程：

变量需要设置变量类型，默认创建的变量类型为String，String类型的官方解释是一个字符串，相当于一个文本。变量类型是一个选择框，打开即可看到一些常用的数据类型：
![](media/16727291938145/16727413425788.jpg)

以下即为日常使用中较为常见的变量类型，如果发现实际流程需要用到更复杂的变量类型，也可以在浏览类型中选择或者进行搜索。

<table style="undefined;table-layout: fixed; width: 714px">
<colgroup>
<col style="width: 56px">
<col style="width: 139px">
<col style="width: 519px">
</colgroup>
<thead>
  <tr>
    <th></th>
    <th>变量类型 </th>
    <th>定义 </th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>（1）</td>
    <td>Boolean（布尔） </td>
    <td>用来做判断，只有true和false两个值。 </td>
  </tr>
  <tr>
    <td>（2）</td>
    <td> Int32（整型） </td>
    <td>是一个整数，范围是：-2,147,483,648 到 2,147,483,647。 </td>
  </tr>
  <tr>
    <td>（3）</td>
    <td> String（文本类型） </td>
    <td>是一个字符串， 例如：“我是Tina”, "RPA学习"这类文本，需要用双引号括起来。 </td>
  </tr>
  <tr>
    <td>（4）</td>
    <td>Object </td>
    <td>可以使用所有类型,相对的，我们就不知道这个变量到底是什么类型了，所以用的比较少。 </td>
  </tr>
  <tr>
    <td>（5）</td>
    <td>Double&nbsp;&nbsp;</td>
    <td>是双精度浮点数，和Int32的区别就是他范围更大，且可以有小数点。 </td>
  </tr>
  <tr>
    <td>（6）</td>
    <td>System.DateTime </td>
    <td>是一个日期，想要获取当前日期可以在默认值里面填System.DateTime.Now. </td>
  </tr>
  <tr>
    <td>（7）</td>
    <td>DataTable </td>
    <td>是一个数据表，多用在数据表，数据库等相关的组件中;<br><br>也可以通过Excel组件把Excel里面的区域记录在数据表类型的变量中。 </td>
  </tr>
  <tr>
    <td>（8）</td>
    <td>FolderPath </td>
    <td>用来存储文件夹路径，本质上是String的一个变种。 </td>
  </tr>
  <tr>
    <td>（9）</td>
    <td>FilePath </td>
    <td>用来存储文件路径，本质上是String的一个变种。 </td>
  </tr>
  <tr>
    <td>（10）</td>
    <td>Password </td>
    <td>用来存储密码，本质上是String的一个变种。 </td>
  </tr>
  <tr>
    <td>（11）</td>
    <td> List of T&nbsp;&nbsp;</td>
    <td>是一个集合，其中T是一个泛型类型，代表可以选择任意一个类型。 <br><br>举例：先选择List of T, 再选择一个Int32作为T, 就有了一个代表Int32的集合，可以使用集合组件往里面添加int32类型的数据。 </td>
  </tr>
  <tr>
    <td>（12）</td>
    <td>Dictionary of T </td>
    <td>是一个字典，代表了一个键值对，这里的T和集合的T一样，是个泛型，这里的2个T, 前一个是键（key）,后一个是值（Value）。 <br><br>举例：选择字典，第一个T选择Int32, 第二个T选择String, 然后可以通过字典组件来添加获取里面的值。如果添加了一个 1, "test", 那么获取值的时候键填写1，然后就可以拿到他的值"test"了。 </td>
  </tr>
  <tr>
    <td>（13）</td>
    <td>Array of T </td>
    <td>是数组，和集合类似，在编辑器中有专门的数组组件对数组做操作。 </td>
  </tr>
</tbody>
</table>

<br><br>


### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>
