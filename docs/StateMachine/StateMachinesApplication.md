# 状态机的应用 

大家好，今天以登录钉钉为例，与大家一起学习状态机的用法。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求
https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?

2. 打开云扩官网(https://www.encoo.com/)下载编辑器并安装（本节课使用编辑器版本为：1.1.2010.9）。

## **操作流程**

![image-20210118105303199](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/image-20210118105303199.png)

## 操作步骤

1. 拖入一个“**状态机**”组件至流程中。

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine1.png)

2. 打开状态机窗口，拖入“**状态**”组件，再打开状态窗口，在Entry中拖入“打开程序”与“等待元素出现“：

   > **说明：**
   >
   > 状态机内只能拖入“状态”与“最终状态”两个组件，不支持其他组件在内。

​      a. 在“**打开程序**”中输入钉钉程序路径;

​      b. “**等待元素出现**”定位钉钉正常登录后，界面上可识别已登录状态的元素（这里我们以左上角搜索输入框为可识别元素），定义输出结果变量：`isTrue`

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine2.png)

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine3.png)

3. 拖入“**最终状态**”组件，输入已登录判断条件 `isTrue == true`，然后打开最终状态对话框，拖入“**确认框**”填入已登录提示信息：

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine4.png)
![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine5.png)

4. 拖入“**状态**”组件，输入未登录判断条件：`isTrue == false`：

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine6.png)


5. 双击打开“状态”窗口，拖入“**获取文本**”组件，获取用户名输入框文本内容（这步主要考虑到钉钉登录界面一般情况下都会默认保留之前的登录用户名数据,我们可先获取文本检查下该文本是否为我们预期要登录的用户名），并定义输出变量:

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine7.png)

6. 拖入“**状态**”组件，判断上步操作中获取的用户名文本为预期用户名文本，填写判断条件：`usernameText == username`， 增加预期登录的用户名与密码变量：

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine8.png)

7. 打开“状态”窗口，拖入一个"**点击**"组件，点击密码输入框，再拖入“**输入文本**”组件，填入密码变量，并最后拖入"**点击**"组件点击登录：

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine9.png)

8. 拖入“**等待元素出现**”组件，指定登录界面元素，定义输出结果变量：`isTrue`

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine10.png)

9.  该“状态”组件连接至“最终状态”，至此，已完成已存在预期用户名的登录过程：

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine11.png)

10. 拖入“状态”组件，添加判断条件当前用户名文本不是预期用户名：`usernameText != username`

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine12.png)

11. 双击“状态”组件窗口，
   > 1. 拖入“**点击**”组件选中钉钉用户名输入框
   > 2. 拖入“**点击**”组件设置右键选中钉钉用户名输入框
   > 3. 拖入“**发送快捷键**”组件发送字母"A"全选输入框中原始文本
   > 4. 拖入“**输入文本**”组件发送预设账号内容
   > 5. 拖入“**输入文本**”组件发送预设账号内容
   > 6. 拖入“**点击**”组件选中钉钉密码输入框
   > 7. 拖入“**输入文本**”组件发送预设密码内容
   > 8. 拖入“**点击**”组件选中登录按钮
   > 9. 最后拖入“**等待元素出现**”组件，填入对应输出结果变量

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine13.png)

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine14.png)

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine15.png)

12. 该“状态”组件连接至“最终状态”，至此，已完成已存在非预期用户名的登录过程：

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/StateMachine/20210128StateMachine16.png)

13. 保存流程并尝试在以下四种情况下运行流程：

- 已登录状态
- 已有预期用户名数据状态
- 无用户名数据状态
- 用户名数据为非预期用户名状态