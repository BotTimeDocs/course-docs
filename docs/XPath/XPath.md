# 什么是XPath

## XPath定义

XPath，即为XML路径语言（XML Path Language），它是一门在XML文档中查找信息的语言。XPath 使用路径表达式来选取 XML 文档中的节点或者节点集。这些路径表达式和我们在常规的电脑文件系统中看到的表达式非常相似。

XPath 最初设计是用来搜寻XML文档的，但是它同样适用于 HTML 文档的搜索。

那，XML又是什么呢？它是用来存储和传输数据的。与 HTML 不同有以下两点：

1. HTML 用来显示数据，XML是用来传输数据。
2. HTML 标签是固定的，XML标签是自定义的。

## XPath作用

- 定位数据位置，定位数据位置，定位数据位置。重要的事情说三遍
- 我们在定位到数据位置后，才能进行比如点击、输入文本等操作

## XPath在Chrome中的实践

Google Chrome 浏览器自带了叫做 "[Chrome DevTools](https://developers.google.com/chrome-developer-tools/)" 前端调试工具。 它包含一系列方便的调试工具，其中包括了在不添加额外插件的前提下，直接审查和验证 XPath/CSS 选择器的功能，具体步骤如下：

1. 打开 Chrome 浏览器，并输入网址跳转到[百度](https://www.baidu.com/)页面。

2. 键入 `F12` 来开启 Chrome DevTools。默认设置下`Element`面板将会自动打开。

3. 按照下图步骤，找到`百度一下`按钮的XPath并复制。它的值为：//*[@id="su"]

   ![image-20201123095855154](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/XPath/xpath1.png)

4. 在当前面板按下`Ctrl`+`F`来启用搜索模式。

5. 输入步骤三得到的XPath值：//*[@id="su"]。如果有任何元素被成功匹配，它们将会在 DOM 中以黄色高亮。

![image-20201123100511663](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/XPath/xpath2.png)

   







