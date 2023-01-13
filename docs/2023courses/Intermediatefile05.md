


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

* 课程简介：RPA小任务1--批量重命名文件并另存 (课程时长:6分钟)
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>

### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%20%E7%AC%AC%E5%85%AB%E8%AF%BE/%E7%AC%AC%E4%B9%9D%E8%AF%BE/%E7%AC%AC%E4%B9%9D%E8%AF%BE%2805%29%EF%BC%9ARPA%E5%B0%8F%E4%BB%BB%E5%8A%A11--%E6%89%B9%E9%87%8F%E9%87%8D%E5%91%BD%E5%90%8D%E6%96%87%E4%BB%B6%E5%B9%B6%E5%8F%A6%E5%AD%98.mp4"> </video>

<br><br><br>

### 2.2 文档教程

<br>

#### 一、任务结婚扫

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736109515867.jpg)

#### 二、具体搭建步骤：

<br>


* **第1步：** 拖入遍历文件夹组件，遍历所选文件夹下的全部文件。

<br>

在文件夹中输入所需遍历的文件夹路径，例如“F:\Folder1”。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736110295879.jpg"/>

<br><br>


*  **第2步：** 拖入重命名文件/文件夹组件，对遍历出的文件进行重命名。

- 原路径：输入"filePath"。
    （在遍历文件夹组件中对文件进行重命名，原路径即为每一个循环中的filePath）。
- 新名称：输入要修改的新名称，例如：在每个文件名前加一个前缀"new_"+"原文件名"。

<br><br>

> **提问：如何获取到原文件名呢？** 
> 
> 可以通过导入一个名为System.IO的命名空间，通过C#代码：Path.GetFileName，获取filePath的文件名。

<br><br>

- 新路径：需新建一个String类型的变量，存储修改后的文件路径，例如："newFilePath"。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736110677158.jpg"/>

<br><br>


**第3步：** 拖入写入日志组件，打印出重命名后的文件路径。
- 日志内容：输入上一步新建的变量"newFilePath"。

<br>


**第4步：** 拖入复制/移动文件组件，将重命名后的文件复制到另一文件夹。

- 复制/移动：下拉选择复制或移动。当选择移动时，原路径下的文件则会被删除。
- 源路径：输入第二步新建的变量newFilePath。
- 目标路径：输入想要复制到的文件夹，例如“C:\Folder2”

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736110782883.jpg"/>

<br><br>


第5步：运行该流程。
流程运行结束后，即可看到Folder1文件夹下的文件被重命名为"new_"+"原文件名".txt 格式，并被复制到Folder2文件夹中。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/13/16736110846335.jpg"/>

<br><br><br><br>


### END :

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)





