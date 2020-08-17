# 花式使用点击组件
     
你可以使用云扩编辑器提供的大量实用的组件以实现丰富的功能。但相信你使用的最多的还是那些最基础的组件，如*点击*，*指定元素*等等。

在实际业务中，遇上五花八门的系统时，你会发现：这些基础的操作也有相当的使用技巧，以确保在特定环境下，流程不会被简单的操作阻塞或者不至于遇到性能方面的问题。

本节课中，我们介绍*点击*组件的花式用法。

## 组件属性回顾

先回顾一下*点击*组件的属性：

- 点击类型：单击、双击、按下、松开；
- 光标位置：中心、左上、左下、右上、右下、
- 横坐标百分比、横坐标偏移、纵坐标百分比、纵坐标偏移
- 鼠标键：左键、中键、右键
- 点击方式：默认、模拟鼠标、设置控件
- 辅助键：Alt、Ctrl、Shift、Win

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/ClickAdvanced/%E5%B1%9E%E6%80%A7)

## 常见的项目场景

借助*点击*组件的丰富属性，我们可以完成一些常见的项目场景。

### 滑块验证

在很多网页中，需要进行登录或转账等高验证等级操作时，时常会见到滑块验证的场景。
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/ClickAdvanced/%E6%BB%91%E5%9D%97.jpg)

在流程中，你需要首先实现滑动认证，然后才能进行其他业务处理。

这样的滑动认证其实可以通过*点击*组件的以下属性实现：
- 点击；
- 按下；
- 松开。

### 元素已验证，但流程中无法点击

通常在制作流程时，我们都会使用元素选择器验证元素是否被选中。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/ClickAdvanced/%E9%80%89%E6%8B%A9%E5%99%A8%E9%AA%8C%E8%AF%81.jpg)

但因为各种系统的不同，我们还是会碰到开发时已验证通过，但流程运行时无法点中所选元素的情况。

此时，将点击方式从*默认* 修改为 *模拟鼠标* 或者 *设置控件* 属性，点击就会正确运行。

### 选中多个项目
你还可以使用*点击*组件，一次选中多个项目。使用 *Shift* 辅助键即可实现。

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/ClickAdvanced/%E7%82%B9%E5%87%BB.mp4" controls="controls" width="700px" />