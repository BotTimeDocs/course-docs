# 状态机的应用 

大家好，今天以登录钉钉为例，与大家一起学习状态机的用法。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）。

2. 打开云扩官网（https://www.encoo.com/）下载编辑器并安装（本节课使用编辑器版本为：1.1.2010.9）。

## **操作流程**

![image-20210118105303199](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118105303199.png)

## 操作步骤

1. 拖入一个“**状态机”**组件至流程中。

![image-20210118105350332](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118105350332.png)

2. 打开状态机窗口，拖入“**状态**”组件，再打开状态窗口，在Entry中拖入“打开程序”与“等待元素出现“：

   > **说明：**
   >
   > 状态机内只能拖入“状态”与“最终状态”两个组件，不支持其他组件在内。

​      a. 在“**打开程序**”中输入钉钉程序路径;

​      b. “**等待元素出现**”定位钉钉正常登录后，界面上可识别已登录状态的元素（这里我们以左上角搜索输入框为可识别元素），定义输出结果变量：`isTrue`

![image-20210118105517490](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118105517490.png)

3. 拖入“**最终状态**”组件，输入已登录判断条件 `isTrue == true`，然后打开最终状态对话框，拖入“**确认框**”填入已登录提示信息：

![image-20210118105615748](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118105615748.png)

![image-20210118114004170](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114004170.png)

4. 拖入“**状态**”组件，输入未登录判断条件：`isTrue == false`：

![image-20210118114056199](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114056199.png)

5. 双击打开“状态”窗口，拖入“**获取文本**”组件，获取用户名输入框文本内容（这步主要考虑到钉钉登录界面一般情况下都会默认保留之前的登录用户名数据,我们可先获取文本检查下该文本是否为我们预期要登录的用户名），并定义输出变量:

![image-20210118114152951](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114152951.png)

6. 拖入“**状态**”组件，判断上步操作中获取的用户名文本为预期用户名文本，填写判断条件：`usernameText == username`， 增加预期登录的用户名与密码变量：

![image-20210118114252729](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114252729.png)

7. 打开“状态”窗口，拖入通过项目组件开发并下载的新组件（输入密码并点击登录操作），填入密码变量：

![image-20210118114404139](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114404139.png)

8. 拖入“**等待元素出现**”组件，指定登录界面元素，定义输出结果变量：`isTrue`

![image-20210118114457037](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114457037.png)

9.  该“状态”组件连接至“最终状态”，至此，已完成已存在预期用户名的登录过程：

![image-20210118114550486](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114550486.png)

10. 拖入“状态”组件，添加判断条件当前用户名文本不是预期用户名：`usernameText != username`

![image-20210118114638193](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114638193.png)

11. 双击“状态”组件窗口，根据钉钉实际支持方式编辑删除当前已存在用户名文本流程部分，并拖入上步操作中发布并下载的个人组件，最后拖入“**等待元素出现**”组件，填入对应输出结果变量：

![image-20210118114723278](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114723278.png)

12. 该“状态”组件连接至“最终状态”，至此，已完成已存在非预期用户名的登录过程：

![image-20210118114806653](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118114806653.png)

13. 保存流程并尝试在以下四种情况下运行流程：

- 已登录状态
- 已有预期用户名数据状态
- 无用户名数据状态
- 用户名数据为非预期用户名状态