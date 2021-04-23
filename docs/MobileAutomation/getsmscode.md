# 获取手机验证码并登录网页

本节课，带大家了解下，如何获取安卓手机短信验证码并登录网页。

## 前提操作

1. 准备开发流程的电脑，查看云扩 RPA 编辑器运行的 [硬件&软件要求](https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?)。
2. 打开 [云扩官网](https://www.encoo.com/) ，下载并安装云扩 RPA 编辑器。

    > **说明：**
    >
    > 本课程使用的云扩 RPA 编辑器版本为：企业版 1.1.2103.14

3. 在控制台的“首页 > 安装包下载”中，下载 Android 服务包(Encoo.Android.Automation)。

    > **说明：**
    >
    > 拥有企业控制台的用户可以直接从控制台下载，如果不是，请联系我们官网客服提供企业版手机自动化相关服务。

## 配置手机连接

1. 当手机连接上 PC 之后，USB 的连接方式选择“传输文件” ，然后将安卓服务包中的 SmsObserver.apk 拖入手机文件目录下的某个位置，从手机端点击此 apk 安装程序。

    ![sms 路径](https://docimages.blob.core.chinacloudapi.cn/images/Course/smspath.png)

2. 运行安卓服务包中的 Encoo.Android.Automation.exe 安卓自动化程序。如果是第一次连接手机请参考 [安卓手机配置文档](https://academy.encoo.com/zh-cn/wiki/Studio/process/developProject/MobileDevicesManage/Download.md?uuid=1ba0256c-ad6d-4f13-aff7-8572dd274f18)。

    ![可执行程序](https://docimages.blob.core.chinacloudapi.cn/images/Course/executeapp.png)

3. 点击“连接服务”。

    ![连接服务](https://docimages.blob.core.chinacloudapi.cn/images/Course/connectionservice.png)

   服务已连接成功如下图所示。

    ![服务连接成功](https://docimages.blob.core.chinacloudapi.cn/images/Course/automateconnect.png)

4. 使用管理员角色打开命令行，输入 `adb devices`，查看当前已经连接的移动端设备，保证手机与 PC 已经连接上。
  
    ![adb](https://docimages.blob.core.chinacloudapi.cn/images/Course/adbdevices.png)

5. 打开云扩编辑器，点击菜单栏的“工具 > 移动设备管理器”。

    ![打开移动设备管理器](https://docimages.blob.core.chinacloudapi.cn/images/Course/openmobilemanage.png)

6. 选择小米手机，并连接设备。

   ![连接设备](https://docimages.blob.core.chinacloudapi.cn/images/Course/connectdevice.png)

## 设计与开发流程

下面的流程我们以某网站手机号免密登录为例。

具体思路：

（1）打开网址，进入到对应页面
（2）点击获取验证码
（3）连接手机设备并使用获取验证码组件，将获取到的验证码填回网页验证码输入框
（4）点击“登录”按钮，进行登录

流程操作步骤如下：

1. 打开编辑器，新建流程，流程名可自定义。

    ![创建流程](https://docimages.blob.core.chinacloudapi.cn/images/Course/createflow.png)

2. 拖入“打开浏览器”组件，浏览器类型选择 `chrome`，网址：_某网站登录地址_
3. 点击 “手机免密登录”。
4. 输入手机号码，点击“获取验证码”。

    ![获取验证码](https://docimages.blob.core.chinacloudapi.cn/images/Course/getsmscodeflow.png)

5. 拖入“连接设备”组件，内部拖入“获取短信验证码”组件。

    ![获取短信验证码组件](https://docimages.blob.core.chinacloudapi.cn/images/Course/activity.png)

6. “获取短信验证码”组件需要配置输入和输出选项，此处我设置的开始时间为 5 分钟以内，超时为 60 秒，输出的验证码复制给`verification_code` 变量

    ![设置属性](https://docimages.blob.core.chinacloudapi.cn/images/Course/settingattu.png)

7. 最后拖入"输入文本"组件，指定验证码元素输入框，输入的文本为上一步获取到的验证码 `verification_code`，点击“登录”

    ![登录](https://docimages.blob.core.chinacloudapi.cn/images/Course/login.png)

8. 运行流程。

    - 自动获取验证码并登录的流程图示：

    ![流程图示](https://docimages.blob.core.chinacloudapi.cn/images/Course/flowchart.png)

    - 手机端获取验证码截图：

    ![手机端获取验证码](https://docimages.blob.core.chinacloudapi.cn/images/Course/autogetsmscode.jpg)

    - 云扩编辑器端，运行日志输出了正确的验证码：

    ![运行结果](https://docimages.blob.core.chinacloudapi.cn/images/Course/runresult.png)

## 常见问题

1. **Q：获取到了 StartTime，但是验证码获取失败。**

    ![异常现象](https://docimages.blob.core.chinacloudapi.cn/images/Course/unnormal.jpg)

   **A：** 从以下四个步骤进行排查：

    a. 进入小米设置页面，点击授权管理。

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Course/mobile1.jpg)

    b. 点击“应用权限管理”。

    ![2](https://docimages.blob.core.chinacloudapi.cn/images/Course/mobile2.jpg)

    c. 找到我们最开始安装的 Sms 应用，打开应用设置。

    ![3](https://docimages.blob.core.chinacloudapi.cn/images/Course/mobile3.jpg)

    d. “通知类短信“选项需要设置为“允许”，完成设置后再重新运行下流程。

    ![4](https://docimages.blob.core.chinacloudapi.cn/images/Course/mobile4.jpg)
