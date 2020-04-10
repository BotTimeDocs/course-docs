# 使用方法

下面将详述如何通过图像识别的方法来实现：

在有两个记事本打开的情况下，使用图像识别的元素定位方法，**点击**打开指定文件的页面设置，**输入文本**到页眉，通过**发送快捷键**的方式关闭页面设置界面，通过**等待元素消失**判断是否关闭成功并将结果**写入日志**


## 准备工作
1. 打开两个**记事本**文件，一个命名为**Target.txt**,另一个使用默认名称**Untitled.txt**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/TwoNotepad.png)

2. 打开云扩**编辑器**，新建一个空白项目，搜索**序列**组件并拖拽至设计面板，设为开始结点,双击打开序列


## 点击文件
3. 搜索**点击**组件并拖拽至设计面板
4. 点击**指定元素**，将鼠标放到**Target.txt**标题栏左上角处，此时可看到整个记事本窗口为高亮显示

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/HighlightTitle.png)

5. 按住CTRL，对工具栏的**文件**画矩形框


## 打开页面设置
6. 搜索**点击**组件并拖拽至设计面板。点击**指定元素**
7. 按下**F2**，可看到延迟5秒录制倒计时。在倒计时时间内，点击**文件** 

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/Delay.png)

8. 倒计时结束后，将鼠标放到弹出菜单的左上角，此时可看到弹出菜单为高亮显示

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/HighlightPageSetup.png) 

9. 对弹出菜单的**页面设置**画矩形框


## 填写页面
10. 搜索**输入文本**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到页面设置界面左上角标题处，此时可看到页面设置界面为高亮显示

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/Header.png)

11.  按住CTRL，对页面标签文本和输入框画矩形框

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/DrewLabelAndInput.png)

12. **输入文本**属性栏中，**文本**属性填入**Header**。注意！因为此处的输入为英文，所以在运行时请将输入法改成相应的英文输入法

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/InputHeaderProperty.png)



## 关闭页面设置
13. 搜索**发送快捷键**组件并拖拽至设计面板。打开下拉菜单，找到**Enter**并点击。此时可看到**发送快捷键**属性栏中，**键值**属性值为 **"{Enter}"**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/SendHotkey.png)



## 判断是否关闭成功
14. 搜索**等待元素消失**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到页面设置界面左上角标题处，此时可看到页面设置界面为高亮显示

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/Header.png)

15. 按住CTRL，对下图画矩形框

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/DrawPreview.png)

16. 点击设计面板下的 **变量**标签，并新建一个**Boolean**类型的变量，命名为**waitElementVanish**
17. 点击**等待元素消失**组件，设置其输出**结果**属性值为**waitElementVanish** （若指定元素消失，则会返回 **True**; 否则返回 **False**)

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/waitElementVanishVariable.png)



## 将结果写入日志
18. 搜索**写入日志**组件并拖拽至设计面板。**日志内容**写入属性值 **"PageSetupPage Vanished? : " + waitElementVanish.ToString()** (此步骤将会看到**等待元素消失**组件的执行结果，即指定元素是否消失)

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/OCR/Log.png)

## 运行
19. 点击工**运行**按钮，结束后查看运行日志即可
