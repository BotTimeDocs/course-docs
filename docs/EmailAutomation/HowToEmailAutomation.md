
# Email自动化

在此单元中，将创建一个自动发送邮件的机器人，它可以同时分别向两个收件人发送邮件，每封邮件都包含两个附件。


在此单元你将学习到：
- 使用[发送邮件(SMTP)](https://academy.encoo.com/zh-cn/wiki/Activities/AppAutomation/Mail/SendMailSMTP.md)组件


准备工作：
- 一个可用的邮箱，并获取其SMTP配置信息
- 两个附件文件：一个txt文件和一张图片

## 创建项目

1. 在编辑器创建一个新的项目**EmailAutomationDemo**
2. 在【组件】面板搜索【邮件】或在【软件自动化】-【邮件】目录下找到【发送邮件(SMTP)】组件，并将其拖拽进新建项目Main设计面板中

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/EmailAutomation/EmailAutomation-Search.png)


## 配置邮件信息

1. 在设计面板中点击【发送邮件(SMTP)】组件并在右侧【属性】面板配置所需字段：
2. 配置发件人信息

    > **邮箱地址：** 输入发件人邮箱地址，例如："username@encootech.com"

    > **密码：** 输入发件人邮箱密码

3. 配置服务器信息

    > **服务器地址：** 输入服务器地址，例如："smtp.outlook.cn"

    > **端口号：** 输入服务器端口号，若使用公司邮箱，可向公司IT管理员获取

    > **代理：** 非必填项，根据实际业务需要选择是否填写。格式为{服务器地址}:{端口号}

    注意：服务器和端口号可以根据邮箱后缀不同，在网上或[云扩社区](https://forum.encoo.com/)查找相关信息。例如：发件人使用QQ邮箱，您可在网上搜索“QQ邮箱 SMTP服务器地址 端口号”；

 4. 填写收件人信息

    > **收件人：** 邮件接收人邮箱地址。可写多个收件人，用分隔符";"分开即可；例如："user1@encootech.com; user2@encootech.com"

    > **抄送人：** 发送邮件时的邮件抄送人（CC）邮箱地址，非必填项；可写多个收件人，用分开分割即可；例如："user1@encootech.com; user2@encootech.com"
    
    > **密件抄送：** 发送邮件时的秘密抄送人（BCC）邮箱地址，非必填项；可写多个收件人，用分开分割即可；例如："user1@encootech.com; user2@encootech.com"

 5. 填写具体邮件内容

    > **邮件主题：** 填写邮件标题"Demo for Email Automation"

    > **HTML格式：** 勾选

    > **邮件内容：** 填写邮件内容 "Just for demo, please ignore..."

    > **附件：**  本课程中我们将会添加两个附件，添加方法：
    
    1. 先在【变量】面板创建变量listAttachments
    2. 设置此变量数据类型为List<string>，此时需导入命名空间**System.Collections.Generic.List<System.String>**

    3. 为此变量初始化 **new List<string>(){"Files\Demo.txt","Files\HelloWorld.png"}** 
        ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/EmailAutomation/EmailAutomation-var.png)


所有字段配置信息如下：

![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/EmailAutomation/EmailAutomation-Perp.png)


## 执行项目查看结果
点击【运行】即可完成邮件发送，此时你就可以在【发件人】邮箱中的【已发送】目录和【收件人】邮箱中的【收件箱】看到此邮件了


## 如何在编辑器中下载并使用本课程示例
1. 打开编辑器，在工具栏点击【流程市场】
2. 搜索此课程名称即可找到此流程
3. 选中流程并点击【下载】图标，在【新建项目】弹窗中输入【项目名称】
4. 点击【创建】此时将会在本地创建一个新的项目
5. 在【工作目录】面板即可打开创建的项目
