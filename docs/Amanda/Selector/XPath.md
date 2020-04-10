# 增加XPath属性
当某些元素难以定位或者定位不稳定时，可以通过增加XPath属性来解决这一问题。当使用XPath时，XPath所在的节点层级将通过XPath属性值来定位，此节点层级的其他属性值将不会发生效力（即使其复选框为选中状态）

例如下图标红处在定位此节点层级时将不发生效力

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/xpath.png)

## 准备工作
1. 已学习上节课最后的选择器文档版详解，若需回顾，请点击[这里](https://academy.bottime.com/zh-cn/wiki/Activities/Appendix/Selector.md)
2. 打开云扩**编辑器**，新建一个空白项目，搜索**序列**组件并拖拽至设计面板，设为开始结点,双击打开序列
3. 手动打开浏览器，输入网址 https://www.encoo.com/ 并等待页面加载完成

## 获取元素
此步骤获取一个控件元素输出值，后续将对此元素的选择器进行更改，使其通过XPath来定位元素

4. 搜索**获取元素**组件并拖拽至设计面板
5. 点击**指定元素**，将鼠标放到导航栏**云扩RPA**处，看到下图高亮效果后点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/EncooRPA.png)

6.  点击设计面板下的 **变量**标签，并新建一个**IUiObject**类型的变量，命名为**outElement**；新建一个**Boolean**类型的变量，命名为**result**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/xpathVar.png)

7. 点击**获取元素**组件，设置其输出**结果**属性值为**outElement** 

## 属性校验
此步骤将通过属性名来获取目标元素的属性值，并和指定值进行对比后返回True或False的结果

8. 搜索**属性校验**组件并拖拽至设计面板。设置其目标**控件元素**属性值为**outElement** ；设置其输入**属性名**属性值为 **"innerText"**;设置其目标**值**属性值为 **"云扩RPA "**  (注意，此处RPA有在结尾后有空格)

## 将目标元素的属性值写入日志
此步骤用于查看目标元素的innerText属性值

9. 搜索**写入日志**组件并拖拽至设计面板
10. **日志内容**写入属性值 **"InnerText is : "+outElement.GetProperty("innertext").ToString()** 

## 将属性校验的结果写入日志
9. 搜索**写入日志**组件并拖拽至设计面板
10. **日志内容**写入属性值 **"AttributeChec result is :"+result.ToString()** 

## 运行查看结果
11. 点击工具栏的**运行**按钮，结束后查看运行日志，应含有下图两行日志信息

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/RunningResult.png)

## 获取XPath属性值
12. 回到 https://www.encoo.com/ 网站，按住**F12**打开如下图面板后，点击标红处

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/F12.png)

13. 将鼠标放置到导航栏的**新闻中心**处，看到下图效果后，点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/News.png)

14. 对应的代码段被定位到。右键单击对应的代码段->复制->复制XPath

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/copyXPath.png)

## 新增XPath属性值
15. 点击**获取元素**组件，点击属性栏**选择器**属性旁的按钮，打开选择器编辑器
16. 点击最后一个节点层级，查看右侧的属性区域，并在空白处右键单击->新增

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/addXPath.png)

17. 点击下拉菜单，选择**XPath**属性。点击右侧的属性值文本框，**Ctrl+V**粘贴XPath

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/AddedXPath.png)

18. 点击确认

## 更改属性检验的值
19. 点击**属性检验**组件，设置其目标**值**属性值为 **"新闻中心"**

## 运行查看结果
20. 点击**运行**按钮，结束后查看运行日志，应含有下图两行日志信息

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/result2.png)

<table><td bgcolor=	#F0F8FF>流程完成后不要忘了保存哟，下节课程的练习将依附本课流程</td></table>