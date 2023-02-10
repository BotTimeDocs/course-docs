第十七课(02)：知识点2-发送邮件(SMTP)

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

* 课程简介：知识点2-发送邮件(SMTP)（课程时长：5分钟）
* 学习目标：掌握 ★★★
* 难易程度：较难 ★★★★
* 讲义下载：文末进群-获取“讲义PPT”

<br><br><br>


### 2.1 视频教程

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/%E7%AC%AC%E5%8D%81%E4%B8%83%E8%AF%BE/%E7%9F%A5%E8%AF%86%E7%82%B92-%E5%8F%91%E9%80%81%E9%82%AE%E4%BB%B6%28SMTP%29.mp4"> </video>

<br><br><br>

### 2.2 文档教程 

<br>

**（1）功能：** 使用 SMTP 协议发送邮件。

<br>

**（2）服务器**
- 服务器 ：发件人邮箱的服务器地址。例如，“smtp.×××.outlook.cn”。
- 端口号 ：邮箱服务器的SMTP端口，可在设置--POP3/SMTP/IMAP中进行查看。



<br>

- 代理 ：发送邮件时若要使用代理，则填写此属性值；格式为【服务器：端口号】。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757660674197.jpg"/>


<br>

如图，以163邮箱为例，此处端口号为：25。
> （常见邮箱的服务器地址和端口号都可以在邮箱网页或客户端的设置信息中找到，例如网易邮箱的配置）。
> 


<br><br>

**（3）发件人**

- 邮箱地址 ：使用此邮箱地址作为发件人，执行发送邮件操作。
- 密码 ：以163为例，需输入授权码，同样可在设置--POP3/SMTP/IMAP中进行查看（需先开启stmp）。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757660585801.jpg"/>



<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757660616616.jpg"/>


<br>

> **注意：** 不同邮箱的密码填写会有所不同。部分邮箱的密码栏所需填写的是邮箱密码。

<br><br>

**（4）邮件**
- 收件人 ：邮件接收人邮箱地址（可填写多个收件人，用分号分割即可）；例如：`user1@encootech.com; user2@encootech.com`。
- 抄送人 ：发送邮件时的抄送人邮箱地址（可填写多个收件人，用分号分割即可）；例如：`user1@encootech.com; user2@encootech.com`。
- 密件抄送 ：发送邮件时的密件抄送人邮箱地址（可填写多个收件人，用分号分割即可）； 例如：`user1@encootech.com; user2@encootech.com`。
- 邮件主题 ：发送邮件的主题。例如，`"发送邮件（SMTP）"`。
- 邮件内容 ：发送邮件的正文内容。例如，`“云扩科技：发送邮件（SMTP）”`。
- 附件 ：发送邮件的附件。支持相对和绝对路径。可写多个附件地址，具体写法参考：`new List`。
- HTML 格式 ：说明邮件内容是否是`HTML`格式，若勾选后，则按照`HTML`格式处理邮件内容。
- 重要性：选择邮件的重要等级，可选项：正常、高、低。

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757660279407.jpg"/>


<br><br><br>

**（5）可选项**
- 安全连接 ：指定检测加密方法，默认为自动，同样支持其他选择。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757660211154.jpg"/>


- 超时：指定此组件的执行时间。若超出此时间，组件还未执行，则会抛出错误。

<br><br><br>

**（6）操作小结**

<br>

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/02/08/16757660149162.jpg"/>


<br><br><br>

> **补充：什么是POP3、SMTP及IMAP？**
> 
> （1）POP3
> * POP3是Post Office Protocol 3的简称，即邮局协议的第3个版本,它规定怎样将个人计算机连接到Internet的邮件服务器和下载电子邮件的电子协议。它是因特网电子邮件的第一个离线协议标准,POP3允许用户从服务器上把邮件存储到本地主机（即自己的计算机）上,同时删除保存在邮件服务器上的邮件，而POP3服务器则是遵循POP3协议的接收邮件服务器，用来接收电子邮件的。（与IMAP有什么不同？）
> 
> （2）SMTP
>  * SMTP 的全称是“Simple Mail Transfer Protocol”，即简单邮件传输协议。它是一组用于从源地址到目的地址传输邮件的规范，通过它来控制邮件的中转方式。SMTP 协议属于 TCP/IP 协议簇，它帮助每台计算机在发送或中转信件时找到下一个目的地。SMTP 服务器就是遵循 SMTP 协议的发送邮件服务器。
 SMTP 认证，简单地说就是要求必须在提供了账户名和密码之后才可以登录 SMTP 服务器，这就使得那些垃圾邮件的散播者无可乘之机。
 增加 SMTP 认证的目的是为了使用户避免受到垃圾邮件的侵扰。
> 
> （3）IMAP
> * IMAP全称是Internet Mail Access Protocol，即交互式邮件存取协议，它是跟POP3类似邮件访问标准协议之一。不同的是，开启了IMAP后，您在电子邮件客户端收取的邮件仍然保留 在服务器上，同时在客户端上的操作都会反馈到服务器上，如：删除邮件，标记已读等，服务器上的邮件也会做相应的动作。所以无论从浏览器登录邮箱或者客户端 软件登录邮箱，看到的邮件以及状态都是一致的。

<br><br><br>

### END：

![](https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg)