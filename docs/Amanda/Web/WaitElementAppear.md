# 判断登录界面是否出现
此节课程以上次课程为基础，继续讲解**流程决策**为True时的运行流程

### 准备工作
1.  打开上节课程的流程文件


## 错误处理
2. 搜索**错误捕捉（Try Catch）**组件并拖拽至设计面板，重命名为**2.ConsolePanelPreviewr**
3. 将其和**流程决策**的True分支连接

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/2.png)

4. 搜索**写入日志**组件并拖拽至设计面板**Try**中。**日志内容**写入属性值 **"Welcome to Encoo RPA Console. Start to Login after click PhoneLogin"**

## 点击
此步骤将控制台的登陆方式由**邮箱登录**切换为**手机登录**

5. 搜索**点击**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到**手机登录**处，看到其高亮显示时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/phone.png)

## 等待元素出现
此步骤将用于判断上一步点击是否成功跳转到手机登录界面，并输出结果用于后续的流程决策

6. 手动点击**手机登录**
7. 搜索**等待元素出现**组件并拖拽至设计面板。点击**指定元素**，移动鼠标并看到其高亮显示时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/phone1.png)

8. 点击设计面板下的 **变量**标签，并新建一个**Boolean**类型的变量，命名为**waitElementAppearResult**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/v1.png)

## Catch 捕获到异常
9. 点击**添加新捕捉**。 选择**System.Exception**，完成后点击下拉框右侧空白处
10. 此时你可以看到下图界面。搜索**写入日志**组件并拖拽至设计面板

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/catch2.png)

11. **日志内容**写入属性值 **"2.Failed"**





## 流程决策：连接与条件分支设置

12. 退出当前**错误捕捉**，返回到带有开始节点的**流程图**界面
13. 搜索**流程决策**组件并拖拽至设计面板 
14. 将**2.ConsolePanelPreview**错误捕捉组件与**流程决策**连接
15. 点击**流程决策**，输入**条件**属性值为**waitElementAppearResult**
16. 将**流程决策**的右侧**False**分支和**结束流程_写入日志**连接

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/e.png)

## 运行
17. 点击工具栏的**运行**按钮，结束后查看运行日志即可

<table><td bgcolor=	#F0F8FF>请手动注册云扩控制台账号，以备后续课程使用</td></table>