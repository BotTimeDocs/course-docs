# 第十七课(03)：知识点3-发送邮件(Outlook)

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

* 课程简介：知识点3-发送邮件(Outlook)（课程时长：3分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%83%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B93-%E5%8F%91%E9%80%81%E9%82%AE%E4%BB%B6%28Outlook%29.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

**（1）使用前提**

调用本地Outlook 客户端服务端口操作邮箱，需先在本地客户端进行登录。
发件人
- 邮箱地址 ：发件人邮箱地址。如，`“××@encootech.com”`。
- 共享邮箱地址 ：使用 Outlook 中共享邮箱地址作为发件人，执行发送邮件操作。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757661264934.jpg"/>


<br><br><br>


**（2）收件人**
- 收件人 ：邮件接收人邮箱地址（可填写多个收件人，用分号分割即可）；`例如：user1@encootech.com; user2@encootech.com`。
- 抄送人 ：发送邮件时的抄送人邮箱地址（可填写多个收件人，用分号分割即可）；` 例如：user1@encootech.com; user2@encootech.com`。
- 密件抄送 ：发送邮件时的密件抄送人邮箱地址（可填写多个收件人，用分号分割即可）；例如：`user1@encootech.com; user2@encootech.com`。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757661396173.jpg"/>


<br><br><br>

**（3）邮件**
- 邮件主题 ：发送邮件的主题。例，`"发送邮件（Outlook）"`。
- 邮件内容 ：发送邮件的正文内容。如，`“云扩科技：发送邮件（Outlook）”`。
- 附件 ：发送邮件的附件。支持相对和绝对路径。可写多个附件地址，具体写法参考：`new List`。 
- 保存为草稿 ：将编辑好的邮件保存到发件人草稿箱，不执行发送操作。
- HTML 格式 ：说明邮件内容是否为`HTML`格式，若勾选后，则按照`HTML`格式处理邮件内容。
- 重要性：选择邮件的重要等级，可选项：正常、高、低。
- 请求送达回执：勾选后，所发送的邮件在送达至指定邮箱后会自动发送回执。
- 请求已读回执：勾选后，发送的邮件被读后将自动发送回执。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757661528199.jpg"/>


<br><br><br>

**（4）转发**
- 邮件 ：输入需要转发的邮件；等同于在 outlook 中选择一封邮件点击“转发”;。
> **注意：** 仅支持 System.Net.Mail.MailMessage 类型。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757661596302.jpg"/>

<br><br><br>

**（5）操作小结**

<br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757661646132.jpg"/>


<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)