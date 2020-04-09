# 属性值的多种写法

### 准备工作
1.  打开上节课程的流程文件
2. 手动打开浏览器，输入网址 https://www.encoo.com/ 并等待页面加载完成

## 支持变量
3. 点击设计面板下的 **变量**标签，并新建一个**String**类型的变量，命名为**Val**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/Val.png)

4. 点击**获取元素**，点击属性栏**选择器**属性旁的按钮，打开选择器编辑器
5. 点击最后一个节点层级，查看右侧的属性区域，剪切XPath的属性值，填入 **{Val}**

<table><td bgcolor=	#F0F8FF>变量要写在花括号里</td></table>

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/Val3.png)

6. 点击确定，返回**变量**面板，粘贴上一步的属性值到变量**Val**的默认值处


![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/Val2.png)

7. 点击工具栏的**运行**按钮，结束后查看运行日志，应含有下图两行日志信息

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/result2.png)

## 支持通配符
8. 点击**获取元素**，点击属性栏**选择器**属性旁的按钮，打开选择器编辑器
9. 点击最后一个节点层级，查看右侧的属性区域，将XPath属性前的复选框设置为不勾选
<table><td bgcolor=	#F0F8FF>当复选框设置为不勾选时，可实现删除此项效果，并在点击确定再次打开选择器编辑器时消失</td></table>

###  *代表匹配零个或多个

10. 将**SInfo**属性值删除，填入**新闻** *

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/Wildcard.png)

11. 点击左下角的**验证**，可看到**新闻中心**被高亮显示，验证成功

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/highlight.png)

###  ？代表匹配一个
12. 将**SInfo**属性值删除，填入**新闻** **?**
13. 点击左下角的**验证**，可看到验证失败

原因：问号仅代表一个字符，网页内的文本为**新闻中心**而非三字，所以找不到指定元素

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/validate1.png)

14. **SInfo**属性值填入**新闻** **??**
15. 点击左下角的**验证**，可看到**新闻中心**被高亮显示，验证成功

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/Selector/highlight.png)