# 第十七课(05)：知识点5-获取邮件(IMAP)

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

* 课程简介：知识点5-获取邮件(IMAP)（课程时长：2分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%83%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B95-%E8%8E%B7%E5%8F%96%E9%82%AE%E4%BB%B6%28IMAP%29.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

**（1）功能** ：使用`IMAP`协议获取邮件，同时可使用代理。

<br><br><br>

**（2）服务器**
- 服务器 ：获取邮件的目标邮箱所属服务器地址。如，“×××.outlook.cn”。
- 端口号 ：获取目标邮箱邮件时所经端口号。如，993。
（常见邮箱的服务器地址和端口号都可以在邮箱网页或客户端的设置信息中找到，例如网易邮箱的配置）。
- 代理 ：获取邮件时若要使用代理，则填充此属性；格式为【服务器：端口号】。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662786879.jpg"/>

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662816159.jpg"/>


<br><br><br>

**（3）邮件**
- 邮箱地址 ：获取此邮箱地址中的邮件。如，`“××@encootech.com”`。
- 密码 ：获取邮件所属目标邮箱的密码。
- 邮件文件夹 ：指定获取邮件的文件夹。若为中文版 Outlook 填写`“收件箱”`，英文版则填写 `"Inbox"`; 若获取`inbox`下子级文件夹邮件，需使用`"/"`分隔，例如: `"inbox/客户邮件"`
- 获取封数 ：获取邮件的封数，默认为`1`。
- 邮件内容格式：默认为自动，可按需下拉选择邮件内容显示的格式，支持纯文本、HTML格式等。
- 忽略证书验证：默认不勾选；勾选则忽略证书验证，以确保正常连接服务器。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662891896.jpg"/>

<br><br><br>

**（4）输出**
- 邮件 ：将获取到的邮件存储在此变量。变量类型为 List<MailMessage> 。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757662992086.jpg"/>

<br><br><br>

**（5）可选项**
- 安全连接 ：指定检测加密方法，默认为自动。
- 仅获取未读邮件 ：默认获取所有类型邮件，若勾选则仅获取未读邮件。
- 标记为已读：默认获取的邮件在 IMAP 中标记为未读，勾选后则会将获取的邮件标记为已读。
- 超时：指定此组件的执行时间。若超出此时间，组件还未执行，则会抛出错误。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757663049378.jpg"/>

<br><br><br>

**（6）操作小结**

<img width = '400'  src =""/>


![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757663099058.jpg)


<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)