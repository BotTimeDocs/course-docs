# 第十七课(04)：知识点4-获取邮件(Outlook)

<br><br>

## 一、课程简介

<br>

**【课程目标】**

Hi，小伙伴们~ 邮件往来是企业日常业务中不可避免的工作内容之一，今天让我们一起通过对简单邮件组件的学习，一起完成两个邮件自动化小任务吧!

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

* 课程简介：知识点4-获取邮件(Outlook)（课程时长：3分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%83%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B94-%E8%8E%B7%E5%8F%96%E9%82%AE%E4%BB%B6%28Outlook%29.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

**（1）功能：** 获取本机`Outlook`账号中邮件。

<br>

**（2）输出**
- 邮箱地址 ：填写需要获取邮件的邮箱地址。
- 邮件文件夹 ：指定邮箱中的文件夹，若为中文版 Outlook 填写`“收件箱”`，英文版则填写 `"Inbox"`;   若获取`Inbox`下子级文件夹邮件，需使用 `"\"`分隔，例如:`"Inbox\客户邮件"`。
- 获取封数 ：获取邮件的封数。默认为 `1`。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662049779.jpg"/>


<br><br><br>

**（3）可选项**
- 标记为已读 ：默认获取到的邮件在 Outlook 中标记为未读，勾选后则将其标记为已读。
- 仅获取未读邮件 ：默认仅获取未读邮箱，若不勾选则获取所有状态邮件。
- 筛选 ：支持输入 JET / DASL query 语法检索过滤邮件。例如：仅获取未读邮件的 query 为 `"[UnRead] = True"`。
- 超时：指定此组件的执行时间。若超出此时间，组件还未执行，则会报错。
书写示例：
  - `"@SQL= ""urn:schemas:httpmail:sender"" = 'encoo'"`
  - `"@SQL= ""urn:schemas:httpmail:date"" > '2021/8/4'" + "And ""urn:schemas:httpmail:subject"" like '%测试%'"`

<br><br>


> **注意：** 如果当前输入的`query`与其他属性产生冲突，则优先使用其他属性选项值。具体写法[参考链接](https://docs.microsoft.com/zh-cn/office/vba/outlook/how-to/search-and-filter/filtering-items)


<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662150137.jpg"/>

<br><br><br>

**（4）输出**

邮件：返回一个邮件列表，内容为所获取的邮件，变量类型为`"List of Mails"`。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662238308.jpg"/>

<br><br>

**（5）操作小结**

<br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662300311.jpg"/>


<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)