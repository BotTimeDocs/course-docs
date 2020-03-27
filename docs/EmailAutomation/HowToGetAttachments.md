# 自动获取邮件和附件

在此单元中，将创建一个自动获取邮件的机器人，并可将附件保存到指定目录。


在此单元你将学习到：
- 使用[获取邮件POP3](https://academy.encoo.com/zh-cn/wiki/Activities/AppAutomation/Mail/GetMailPOP3.md)组件
- 使用[保存附件](https://academy.encoo.com/zh-cn/wiki/Activities/AppAutomation/Mail/GetMailPOP3.md)组件

准备工作：
- 一个可用的邮箱，并获取其POP3配置信息

## 创建项目

1. 在编辑器创建一个新的项目**GetEmailandAttachmentsDemo**
2. 从【组件】面板将组件【获取邮件POP3】、【循环操作（For Each）】拖入进设计面板中

   ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/EmailAutomation/GetAttachments-1.png)


## 配置目标邮箱信息

1. 在项目中点击【获取邮件POP3】组件并在右侧【属性】面板配置所需字段
2. 配置服务器信息

    > **服务器地址：** 输入服务器地址，例如："smtp.outlook.cn"

    > **端口号：** 输入服务器端口号，若使用公司邮箱，可向公司IT管理员获取

    > **代理：** 非必填项，根据实际业务需要选择是否填写。格式为{服务器地址}:{端口号}
3. 填写目标邮箱信息

    > **邮件地址：** 输入要获取的目标邮箱地址

    > **邮件内容格式：** 选择"自动"
    
    > **密码：** 输入目标邮箱密码

    > **获取封数：** 输入10
4. 设置输出

    > **邮件：** 此属性的作用是接收获取到的邮件，为了接下来从输出结果中获取附件，我们先将其保存到变量mailResult中。具体操作如下：
    1. 在变量面板新建一个变量mailResult，类型为List<MailMessage>
   ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/EmailAutomation/GetAttachments-3.png)
    2. 回到属性栏，在【输出】-【邮件】输入框中填入mailResult，即所获取到的邮件就都会保存在mailResult中
       ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/EmailAutomation/GetAttachments-4.png)


## 循环获取的邮件并将附件保存至指定目录

1. 双击【循环操作（For Each）】打开
2. 将【写入日志】组件和【保存附件】相继拖拽进来
3. 在【写入日志】组件的【日志内容】文本框输入 **"邮件标题: "+item.Subject**，用于执行后在日志查看获取到了哪些邮件
4. 在【保存附件】组件的【邮件】文本框输入 **item** 
5. 并【文件夹路径】中输入 **"./Attachments"** 

## 执行项目查看结果
1. 点击【运行】即可成功获取配置的目标邮箱中的邮件
2. 在【工作目录】面板，选中项目**GetEmailandAttachmentsDemo**右键单击，选择**打开文件夹** 进入**Attachments**文件夹即可查看到下载的附件

## 如何在编辑器中下载并使用本课程示例
1. 打开编辑器，在工具栏点击【流程市场】
2. 搜索此课程名称即可找到此流程
3. 选中流程并点击【下载】图标，在【新建项目】弹窗中输入【项目名称】
4. 点击【创建】此时将会在本地创建一个新的项目
5. 在【工作目录】面板即可打开创建的项目


