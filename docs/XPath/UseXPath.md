# 小白如何使用XPath

上节课已经介绍了关于 XPath 的基础知识。但作为一个初识 XPath 的用户，你可能还是会有疑问：我该怎么自己编写和查看 XPath 呢？ 那么今天，我将给大家介绍，如何在云扩编辑器中使用 XPath 来定位元素。当然，即使你是初识 XPath 用户 ，也不需要担心，你所要了解的，都在这里拉~

## 准备工作

1. 打开 IE 浏览器，并跳转到[百度一下](https://www.baidu.com/?tn=80035161_1_dg)的页面。
2. 打开云扩编辑器，新建项目。
3. 拖拽**点击**组件到设计面板，并设置为开始节点。

## 编辑器中自动生成XPath

下面将讲解，如何使用云扩编辑器，自动生成 XPath ，并使用生成的 XPath 来定位元素。

1. 选中**点击**组件，点击属性栏的**选择器**属性打开**选择器编辑器**。

   我们将在选择器编辑器中，设置自动生成 XPath 。

2. 点击下图图标后，勾选**生成 XPath（仅支持 WEB ）**。![image-20201202150659275](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/XPath/2-1.png)

3. 点击**指定元素**，指定**百度一下**按钮。

   此时，已经自动生成了可以匹配到指定元素的 XPath 路径，如下图所示。

   ![image-20201202172806657](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/XPath/2-2.png)

4. 点击确认。

   到这里，我们就完成了使用 XPath 来定位元素。运行，也可以看到点击效果。