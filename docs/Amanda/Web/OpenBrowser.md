# 打开浏览器，并提供错误处理
本节课程将通过案列带领大家走进网站自动化，请保存好本节课程的流程，以备后面的课程使用

## 错误处理
此步骤用于捕捉运行中的错误以提高流程的成功率，同时提供错误解决方案以使流程继续运行。下述**Catch**内组件，仅当**Try**内组件运行失败时才会运行，它的作用是对**Try**内组件进行错误处理

1. 打开云扩**编辑器**，新建一个空白项目，搜索**错误捕捉(Try Catch)**组件并拖拽至设计面板，重命名为**1.OpenBroswer**，设为开始结点,双击打开

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/Rename.png)

2. 点击**添加新捕捉**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/catch.png)

3. 选择**System.Exception**，完成后点击下拉框右侧空白处

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/catch1.png)

4. 此时你可以看到下图界面。搜索**写入日志**组件并拖拽至设计面板

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/catch2.png)

5. **日志内容**写入属性值 **"1.Open Browser Failed"**

## 打开浏览器，点击按钮
6. 点击**添加组件**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/catch3.png)

7. 搜索**打开浏览器**组件并拖拽至设计面板
8. **网址**写入属性值 **"www.encoo.com/apply"**； **浏览器类型**选择**Chrome**
<table><td bgcolor=	#F0F8FF>仅当Chrome插件安装后，才可以使用Chrome浏览器运行流程 （IE运行流程不需要安装插件）。具体安装帮助请点击<a href=https://academy.bottime.com/zh-cn/wiki/Studio/Extensions/ChromeExtension.md>这里 </a>查看</td></table>

9. 搜索**点击**组件并拖拽至设计面板
10. 点击**指定元素**，将鼠标放到**立即注册**高亮显示时，点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/Register.png)

## 关闭标签页
为讲授**关闭标签页**的使用方法，特选定了在点击按钮后会生成新标签页的网站。关闭标签页有两种使用方法：①指定特定的标签页关闭 ②不指定特定标签页，关闭当前焦点标签页。大家可以点击[这里](https://academy.bottime.com/wiki/Activities/AppAutomation/Browser/CloseTab.md) 查看具体文档描述

下面将使用第一种**指定特定标签页**：

11. 搜索**关闭标签页**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到要关闭的标签页并高亮显示时，点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/highlight.png)


## 等待元素消失
此步骤用于检测上一步骤的操作是否生效 （通过指定按钮所在界面的某一元素，通过判断其是否消失来确定点击是否生效）

12. 搜索**等待元素消失**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到下图位置并高亮显示时，点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/waitVanish.png)


13. 点击设计面板下的 **变量**标签，并新建一个**Boolean**类型的变量，命名为**waitElementVanishResult**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/var1.png)

14. 点击**等待元素消失**组件，设置其输出**结果**属性值为**waitElementVanishResult** （若指定元素消失，则会返回 **True**; 否则返回 **False**)

## 流程决策，决定下一步流程走向
根据等待元素消失的结果，来确定流程下一步。当指定元素消失后（即按钮点击生效，返回值为True），进入云扩控制台页面；当指定元素未消失（即按钮点击未生效，返回值为False)，进入预设的结束流程分支

### 连接流程决策

15. 退出当前**错误捕捉**，返回到带有开始节点的**流程图**界面
16. 搜索**流程决策**组件并拖拽至设计面板 
<table><td bgcolor=	#F0F8FF>流程决策组件仅能在流程图种使用，无法使用在序列内</td></table>

17. 点击**1.OpenBrowser**错误捕捉组件，将鼠标放置到下图标红处，出现下图效果时，点击并拖动将其和**流程决策**连接

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/line.png)


### 设置决策条件
此步骤将前述**等待元素消失**的**结果**作为决策条件，当结果为False时，我们将写入日志并结束流程；当结果为True时，我们将继续执行流程，具体将在下节课程详细讲解，请保存好本节课程的流程以供后续使用

18. 点击**流程决策**，输入**条件**属性值为**waitElementVanishResult**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/decision.png)

### 流程决策为False时
此步骤将在流程决策的条件为False时执行。下述步骤在本模块的流程决策为False时，均执行，不再重复讲解

19. 搜索**写入日志**组件并拖拽至设计面板。更改其**显示名称**属性值为**结束流程_写入日志**；**日志内容**属性值写入 **"Error Encountered.End Process"**

20. 将**流程决策**的右侧**False**分支和**结束流程_写入日志**连接

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/decision1.png)

## 运行
21. 点击**运行**按钮，结束后查看运行日志即可