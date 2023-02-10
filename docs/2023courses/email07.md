# 第十七课(07)：RPA小任务2--监听保存Outlook邮件附件

<br><br>

## 一、课程简介

<br>

**【课程目标】**

HI，小伙伴们~ 邮件往来是企业日常业务中不可避免的工作内容之一，今天让我们一起通过对简单邮件组件的学习，一起完成两个邮件自动化小任务吧!

<br><br>

**课时内容：**

> * RPA第十七课 (2023年)
> * 课程时长：20分钟 ,7节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)

<br><br>


**目录：**

> * 知识点1-邮件组件基本类型介绍（课程时长：1分钟）
> * 知识点2-发送邮件(SMTP)（课程时长：5分钟）
> * 知识点3-发送邮件(Outlook)（课程时长：3分钟）
> * 知识点4-获取邮件(Outlook)（课程时长：3分钟）
> * 知识点5-获取邮件(IMAP)（课程时长：2分钟）
> * RPA小任务1--发送生日祝贺邮件（课程时长：3分钟）
> * RPA小任务2--监听保存Outlook邮件附件（课程时长：3分钟）


<br><br><br>



##  二、学习内容：

<br>

* 课程简介：RPA小任务2--监听保存Outlook邮件附件（课程时长：3分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%83%E8%AF%BE/RPA%E5%B0%8F%E4%BB%BB%E5%8A%A12--%E7%9B%91%E5%90%AC%E4%BF%9D%E5%AD%98Outlook%E9%82%AE%E4%BB%B6%E9%99%84%E4%BB%B6.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

### **一、保存附件-组件功能介绍**

<br>

**（1）功能：** 将邮件中的附件保存到指定位置。

<br><br> 

**（2）邮件**

- 文件夹路径 ：附件保存的具体位置，支持相对和绝对路径。
- 邮件 ：取此邮件变量中的附件，执行保存操作。

<br>

> 注意：若出现同名文件则会报错；路径不存在则自动新建。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757666257032.jpg"/>


<br><br><br>

### 二、操作步骤

<br><br>

**第1步：**

> * 该步骤会将提取的邮件放入名为mails的变量中。添加获取邮件（Outlook）组件并填写属性。
> 
> * 需填写邮箱地址、获取封数、输出的变量（点击右侧 fx ，按提示的变量名，即可可快捷创建变量mails）。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757664946932.jpg"/>

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757664992543.jpg"/>


<br><br><br>

**第2步：**

> 打印获取邮件的数量。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757665057974.jpg"/>


<br><br><br>

**第3步：**

> 添加循环操作（For each）组件，对所提取的邮件进行判断。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757665106392.jpg"/>

<br><br><br>

**第4步：**

> 添加写入日志组件，打印邮件主题。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757665144520.jpg"/>

<br><br><br>


**第5步：**

> 添加条件（if）组件判断所提取邮件中是否存在主题为Test的邮件）。
> 
> 若条件成立，则执行保存附件组件，需填写附件的保存路径。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757665206472.jpg"/>


<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757665245626.jpg"/>


<br><br><br>

**第6步：**

> 点击运行，即可获取到邮件和对应的附件文件。

<br><br><br>

**参考Demo** ：点击下载[参考流程包](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%83%E8%AF%BE/%E8%8E%B7%E5%8F%96%E9%82%AE%E4%BB%B6Demo.dgs)


<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)