# 第九课(06)：RPA小任务2--Chrome下载文件至指定路径
<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

* 通过对文件自动化组件的进一步学习，结合之前学过的知识点：最终完成“批量重命名文件并另存”以及“在Chrome下载文件至指定路径”两个RPA流程搭建，过程中请熟悉与掌握流程构建的设计思路。


<br><br>

**课时内容：**

> * RPA第九课 (2023年)
> * 课程时长：30分钟 ,6节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1--文件/文件夹是否存在 (课程时长:2分钟)
> * 知识点2--选择文件/文件夹 (课程时长:3分钟)
> * 知识点3--遍历文件夹 (课程时长:2分钟)
> * 知识点4--获取文件/文件夹列表 (课程时长:3分钟)
> * RPA小任务1--批量重命名文件并另存 (课程时长:6分钟)
> * RPA小任务2--Chrome下载文件至指定路径 (课程时长:14分钟)


<br><br><br>



##  二、学习内容：
<br>

* 课程简介：RPA小任务2--Chrome下载文件至指定路径 (课程时长:14分钟)
* 学习目标：掌握 ★★★
* 难易程度：简单 ★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<br>

> 暂无

<br><br><br>

### 2.1 文档教程


当我们遇到在Chrome浏览器上下载文件后保存到指定文件路径的场景时，通常采取的方案相对较多的是手动设置Chrome下载文件路径，但也有些特定的场景中不合适让用户去修改浏览器设置。那么，如何通过RPA从默认的下载路径获取到文件并保存到指定的路径下呢？尤其是在每位用户的默认下载文件路径不相同的情况下（即默认路径为动态的）。

接下来我们以下载云扩编辑器安装包为例，一起看看具体的开发过程。

### 一、准备工作
● 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）。
● 打开云扩官网（https://www.encoo.com/） 下载编辑器并安装。
● 注册云扩社区版控制台账号。

### 二、流程设计图示

<br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735921324575.jpg"/>

<br><br>



### 三、流程操作步骤

<br>


#### （1）登录云扩控制台网站

<br>

第1步：

* （创建项目步骤略过）拖入打开浏览器组件，并指定网址，选择浏览器类型为Chrome: 


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735923191340.jpg"/>

<br><br>



第2步：

* 拖入序列组件，命名为“登录”；拖入输入文本组件，指定用户名输入框元素、创建变量 username 并按快捷键Ctrl+B同步至变量区，变量默认值为实际用户名： 

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735923275744.jpg"/>

<br><br>




第3步：
* 再次拖入输入文本组件，指定密码输入框元素、创建变量 password 并按快捷键Ctrl+B同步至变量区，变量默认值为实际密码： 

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735923346874.jpg"/>

<br><br>


第4步：
* 拖入点击组件，指定登录元素： 


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735923439427.jpg"/>

<br><br><br><br>


#### （2）下载Studio并保存至指定文件路径下

<br>

* 第5步：拖入流程图组件用来模块化流程下载并将文件移至目标文件夹部分；拖入点击组件，指定“下载”元素： 

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735926781618.jpg"/>

<br><br><br><br>

第6步：

* 点击下载后我们模拟手动操作点击网页下端下载进度栏中的“全部显示”，但因为网络延迟等因素导致有时目标元素并不能马上显示出来；

* 所以我们在设计流程时可用等待元素出现组件来检查元素显示，并拖入流程决策组件判断是否出现，如果出现则点击；

* 如果在超时时间端内没有出现该元素，那么继续等待，流程设计如下图： 

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735926781618.jpg"/>

<br><br><br><br>

第7步：

* 点击上步操作中的“全部显示”后需要点击“保留”，但因为文件大小不确定，还未下载完成的页面上没有“保留”这个按钮，那么我们用上步同样的操作来处理： 

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735926781618.jpg"/>

<br><br><br><br>

第8步：
* 点击“保留”之后下载的文件已保存在默认路径下，我们需要获取当前下载的文件名及默认下载路径。

* 首先拖入获取文本组件获取文件名，需要注意的是在指定元素后从选择器中取消最下层的`Hyperlink`，否则获取到的数据为文件名下端的链接字串而非文件名，

* 如下图所示：  
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735926781618.jpg"/>

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735926781618.jpg"/>

<br><br><br>

第9步：

* 拖入点击组件，指定“在文件夹中显示”元素，注意：用UIA3技术录制的元素因为定位时会相对比较慢，所以需要添加匹配超时时间，如下图所示： 
<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735925699657.jpg"/>

<br><br><br>

第10步：
* 拖入获取文本组件，指定“文件地址栏”元素，注意：因为默认下载文件路径每台电脑都不相同，所以指定元素后需要在选择器中对当前路径Name用通配符替换： 

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735925699657.jpg"/>

<br><br><br>

第11步：
* 拖入复制/移动文件组件，输入源文件路径（将以上操作步骤中获取的文件名称与默认下载路径名称进行拼接： `filePath(' ')[1] + "\" + fileName `与目标路径`destFolderPath + "\" + fileName `并选择“移动”方式`：  

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16735925699657.jpg"/>

<br> <br>
至此，整个流程开发完成。

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)
