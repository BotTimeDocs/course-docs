# 数字字母类验证码

关于网站登录验证，我们在之前的课程中讲解了**滑块验证**与**拼图滑块验证**两种方式，那么这这节课讲讲如何用云扩 RPA 破解网站的数字、字母类验证。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）。

2. 打开云扩官网（https://www.encoo.com/）下载编辑器并安装。

3. 准备超级鹰验证码平台用户名、密码及软件ID，具体请看最下端“验证码组件说明”。

## **案例介绍**

用云扩 RPA 实现含有数字、字母类验证码的登录，如下图所示：

![2021-01-15_133346](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133346.png)

流程设计示意图：

![2021-01-15_133347](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133347.png)

## **操作步骤**

1. 打开云扩编辑器，新建项目：

![2021-01-15_133348](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133348.png)

2. 打开组件市场，搜索“超级鹰”并下载：

![2021-01-15_133349](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133349.png)

3. 下载后对应组件可在“**组件 > 扩展**”中查看，如下图所示：

![2021-01-15_133350](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133350.png)

4. **打开网站及输入用户名密码部分**

​       a. 拖入“**打开浏览器**”组件，并设置“浏览器类型”与“网址”（此处以超级鹰登录页为例：https://www.chaojiying.com/user/login/?url=/user/pay/）：

![2021-01-15_133351](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133351.png)

​      b. 拖入两个“**输入文本**”组件，指定用户名及密码输入框元素并输入用户名密码：

![2021-01-15_133352](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133352.png)

5. **验证码识别及输入部分**

​      a. 拖入“**截屏**”组件，设置截图存放路径变量，并“指定元素”、填入路径变量、勾选同名覆盖（将验证码区域截图并保存）：

![2021-01-15_133353](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133353.png)

​      b. 拖入“**验证码识别**”组件，输入事先准备好的“密码”、“软件ID”、“图片地址”、“验证码类型”及“用户名”，如下图所示：

![2021-01-15_133354](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133354.png)

​      c. 拖入“**输入文本**”组件，指定验证码输入框元素，添加输入文本变量：

![2021-01-15_133355](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133355.png)

6. **登录部分**

​      a. 拖入“**点击**”组件并指定“登录”元素：

![2021-01-15_133356](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133356.png)

​       b. 验证码识别及输入验证码流程已开发完成，保存流程并运行。

## **验证码组件说明**

验证码组件是集成第三方超级鹰验证码识别平台的组件，因此，初次使用需要到超级鹰官网注册账号并购买题分，然后在""用户中心 > 软件ID > 生成一个软件 ID ""创建软件应用，会得到一个软件ID。验证码类型请在官网：http://www.chaojiying.com/price.html查询，根据自己需要选择合适的类型。

注册好超级鹰官网以后，我们先购买一个1元体验包来验证一下，再生成软件ID。

![2021-01-15_133357](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133357.png)

![2021-01-15_133358](https://docimages.blob.core.chinacloudapi.cn/images/Practice/verification/2021-01-15_133358.png)