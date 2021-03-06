# 花式使用选择器编辑器
     
你可以使用云扩编辑器提供的大量实用的组件以实现丰富的功能。但相信你使用的最多的还是那些最基础的组件，如*点击*，*指定元素*等等。

在实际业务中，遇上五花八门的系统时，你会发现：这些基础的操作也有相当的使用技巧，以确保在特定环境下，流程不会被简单的操作阻塞或者不至于遇到性能方面的问题。

本节课中，我们介绍*选择器编辑器*的花式用法。

## 前置课程

在此前的课程中，您已经了解了选择器编辑器的基础用法：
 - 选择器编辑器的作用：[选择器编辑器](https://academy.encoo.com/learn/unit-detail/16);
 - 选择器编辑器中 XPath 的用法：[增加XPath属性](https://academy.encoo.com/learn/unit-detail/15);
 - 在选择器编辑器中添加变量和通配符：[属性值的多种写法](https://academy.encoo.com/learn/unit-detail/26)。

## 选择/点击位置不固定的元素

在实际项目中，你经常会碰到 **需要选择或者点击的元素在页面上的位置并不固定** 的情况。

你可以通过拼接 XPath 来定位，并将 XPath 变量传给选择器。你也可以获取该元素的 *index* 属性，将其传给选择器。

在以下示例中，我们演示选择 *通用型超级计算集群 sccg5*。该行位置会根据实际情况发生变化，并不会固定在第3行。那么这种情况下，我们可以通过查找文本 *通用型超级计算集群 sccg5* 来获取该行行号，然后将行号作为单选按钮元素选择器中的 *index*。

参看视频中演示的流程开发过程：

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/ClickAdvanced/index.mp4" controls="controls" width="700px" />