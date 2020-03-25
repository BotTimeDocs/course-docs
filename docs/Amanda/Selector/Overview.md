# 选择器编辑器
**选择器**是一个属性，用来定位目标元素。例如您要点击页面内的一个按钮，**选择器**的作用就是定位到目标按钮。
点击属性栏**选择器**旁的按钮，会弹出选择器编辑器。**选择器编辑器**为用户提供了编辑属性值，预览和验证的功能，扩大了特殊场景的定位支持力度，降低运行失败率

## 适用范围
带有**选择器**属性的组件，均支持选择器编辑器


## 对比与控件元素的异同
**选择器**属性和**控件元素**属性作用相同，均为定位目标元素。两者互斥。
不同的地方在于是否可编辑。**控件元素**不可编辑，它适用于组件间的传递，即适用A组件得到一个输出**控件元素**后，传入B组件的输入**控件元素**。下面将通过一个案例来详述其使用方法

### 准备工作：
1. 打开云扩**编辑器**，新建一个空白项目，搜索**序列**组件并拖拽至设计面板，设为开始结点,双击打开序列
2. 手动打开浏览器，输入网址 https://www.encoo.com/ 并等待页面加载完成

### 获取控件元素输出
3. 搜索**获取元素**组件并拖拽至设计面板
4. 点击**指定元素**，将鼠标放到导航栏**云扩RPA**处，看到下图高亮效果后点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/EncooRPA.png)

5. 点击设计面板下的 **变量**标签，并新建一个**IUiObject**类型的变量，命名为**outElement**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/Variable.png)

6. 点击**获取元素**组件，设置其输出**控件元素**属性值为**outElement** 

### 传入控件元素
7. 搜索**悬停**组件并拖拽至设计面板
8. 设置其目标**控件元素**属性值为**outElement** 
9. 点击工具栏的**运行**按钮，查看效果

### 运行结果
运行后大家可以看到如下效果

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/Result.png)

在了解如何使用**控件元素**来定位目标元素后，接下来我们将学习如何使用**选择器编辑器**来动态的定位目标元素。
请点击[这里](https://academy.bottime.com/zh-cn/wiki/Activities/Appendix/Selector.md)查看文档版详解，以完成后续课程和测试题