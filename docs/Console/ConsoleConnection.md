# 通过控制台激活编辑器和机器人

大家好，这节课我们主要来介绍一下通过控制台来激活对应的编辑器及机器人。最终，我们可以将编辑器编辑好的流程包直接发布到控制台，同时也可利用控制台调度各类机器人执行流程任务。

通过本章节，你可以了解到：

1. 通过控制台激活机器人。

2. 通过控制台激活编辑器。

3. 查看许可证使用情况。


## 通过控制台激活机器人

机器人激活包括本地激活以及控制台激活两种方式，其中通过控制台激活是指机器人连接到控制台并且消耗控制台上的许可证进行激活。通过控制台激活的机器人可以被控制台远程调度进行执行任务。

### 1、在控制台创建机器人

步骤1：首先我们进入“RPA管理 > 机器人管理”页面，在这里我们可以查看当前资源组下所有的机器人信息，同时可在当前资源组下新建机器人，我们也可在右上角切换至不同的资源组。

步骤2：点击“新建”按钮，在弹窗中填写机器人基本信息并选择对应的机器人类型后，点击“确定”即可完成机器人新建。新建成功后，系统将会自动复制该“机器人连接字符串”以用于激活。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection1.png)

​         若此次没有激活，后续也可点击机器人名称查看“机器人详情”找到并复制该字符串。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection2.png)


### 2、在机器人客户端激活

#### 社区版机器人激活

步骤1：打开已经安装好的机器人客户端，在激活方式选择页面中点击“社区版”中的“控制台激活”。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection3.png)

步骤2：在激活页面中“连接字符串”输入框中粘贴已复制的“机器人连接字符串”，点击“激活”按钮，即可完成对应机器人的激活。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection4.png)

#### 企业版机器人激活

步骤1：打开已经安装好的机器人客户端，在激活方式选择页面中点击“企业版”中的“控制台激活”。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection5.png)

步骤2：在激活页面中“连接字符串”输入框中粘贴已复制的机器人“连接字符串”，点击“激活”按钮，即可完成对应机器人的激活。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection6.png)

## 通过控制台激活编辑器 

编辑器激活包括本地激活以及控制台激活两种方式，其中通过控制台激活是指编辑器连接到控制台并且消耗控制台上的许可证进行激活。通过控制台激活的编辑器可以直接将编辑好的流程包分享到控制台上进行使用。

#### 社区版编辑器激活

步骤1：打开已经安装好的编辑器客户端，在激活方式选择页面中点击“社区版”中的“控制台激活”。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection7.png)


步骤2：在激活页面中输入对应的“账号”及“密码”后，点击“下一步”按钮，即可进入租户选择页面。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection8.png)

步骤3：在租户选择页面中选择对应的租户后，即可完成激活。

> **说明：**
>
> 对于社区版每人仅拥有一个社区版租户。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection9.png)

#### 企业版编辑器激活

步骤1：打开已经安装好的编辑器客户端，在激活方式选择页面中点击“企业版”中的“登录控制台激活”。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection10.png)

步骤2：在激活页面中输入对应的“控制台服务地址”、“账号”及“密码”等信息后，点击“下一步“按钮，即可进入租户选择页面。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection11.png)


步骤3：编辑器会自动填写云扩 SaaS 版企业控制台的服务地址，对于私有化版企业控制台可以在首页（HomePage）导航页中复制对应的“控制台服务地址”进行填写。

![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection12.png)

步骤4：在租户选择页面中选择对应的租户后，即可完成激活。

> **说明：**
>
> 一个用户可以被加入多个企业版租户中。

 ![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection13.png)

## 查看许可证使用情况

控制台中的“许可证页面”主要用于展示并管理控制台中导入的许可证使用情况，控制台许可证主要决定了控制台可以激活的编辑器、机器人的数量。


完成编辑器、机器人等客户端激活操作后， 若需要查看并管理许可证的使用情况，可在“全局管理 > 许可证”中，点击对应的”查看使用情况”按钮即可查看使用详情。

 ![Consoleintroduction](https://docimages.blob.core.chinacloudapi.cn/images/Console/ConsoleConnection14.png)

以上便是通过控制台激活编辑器及机器人的方式，我们将会在后续的课程中介绍控制台是如何使用编辑器上传的流程包去调度机器人执行任务。
