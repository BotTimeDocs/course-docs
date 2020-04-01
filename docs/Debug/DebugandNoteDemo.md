# 使用调试和日志快速定位问题

在日常编写流程时难免会遇到一些“奇怪的问题”，有时无从下手，我们都明白只有能够快速的定位问题才能够快速解决。很幸运，云扩编辑器内置了强大的调试工具和日志组件可以帮助我们快速定位问题，大大地提高了我们的工作效率。

在此单元中，我们将一起使用调试工具和日志组件一步一步执行整个运行过程并将关键信息记录在日志。



在此单元你将学习到：
- 使用[调试](https://academy.encoo.com/zh-cn/wiki/Studio/Debugging.md)追踪和定位问题
- 使用[错误捕获(Try Catch)](https://academy.encoo.com/zh-cn/wiki/Activities/WorkflowControl/TryCatch.md)组件
- 使用[写入日志](https://academy.encoo.com/wiki/Activities/System/WriteLog.md)组件


准备工作：
- 安装 Microsoft Office

## 创建项目

1. 在编辑器创建一个新的项目**DebugandNoteDemo**
2. 在【组件】面板搜索【打开/新建】或在【软件自动化】-【Office Excel】目录下找到【打开/新建】组件，并将其拖拽进新建项目Main设计面板中
    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DebugDemo-1.png)

3. 选中【打开/新建】组件并在属性面板配置文件路径：
   > 新建文件: 勾选 
   > 文件路径: "Files\Demo.xlsx" 

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-1.png)



## 配置流程信息

1. 在设计面板中双击打开【打开/新建】组件，找到【错误捕获(Try Catch)】组件并拖入
2. 在【Try】区域相继拖入【插入工作表】、【写入单元格】和【写入日志】组件
    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-2.png)
3. 在【插入工作表】组件的属性面板填写如下信息：
   > 新工作表名称："Demo"
   > 插入位置: 2

4. 在【写入单元格】组件的属性面板填写如下信息：
   > 单元格："A0"
   > 工作表："Demo"
   > 数据： "Just for demo"


5. 在【写入单元格】组件的属性面板填写如下信息：
   > 日志级别："info"
   > 日志内容：DateTime.Now+"：成功写入单元格"


5. 在【Catches】区域拖入【写入日志】组件:
   > 日志级别："Error"
   > 日志内容：DateTime.Now+"遇到异常："+exception.Message


## 插入断点
1. 选中组件【插入工作表】按【F9】或右键单击选择【断点】【插入断点】，接下来分别对【写入单元格】和【写入日志】做此操作

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-7.png)

## 调试
1. 在编辑器工具栏点击【调试】，此时编辑器左侧面板自动切换到【变量】，流程中的焦点在【插入工作表】组件并高亮
2. 点击编辑器顶部工具栏【单步执行】，此时焦点移动至【写入单元格】，左侧面板显示在【插入工作表】组件执行后的参数信息

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-8.png)

3. 继续点击【单步执行】或按【F11】，此时焦点移动至【Catches】模板，这是指在执行【写入单元格】组件时遇到了异常

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-12.png)

4. 继续点击【单步执行】或按【F11】，此时在编辑器左侧【日志】面板显示了详细的错误信息

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-11.png)

4. 根据错误信息我们才明白原来是在写入单元格时没有找到 A0 此单元格，那么我们回到【写入单元格】组件属性面板做如下更改：

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-13.png)

5. 再次在编辑器工具栏点击【调试】，并按照之前的操作点【F1】继续单步调试，最后流程成功执行完成

    ![Demo](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/DD-14.png)

## 查看结果
1. 在【工作目录】面板，选中项目**DebugandNoteDemo**右键单击，选择**打开文件夹** 
2. 在打开的窗口中，你会发现自动创建了**Files**文件夹，双击进入
3. 在此目录下自动创建了一个**Demo.xlsx**文件
4. 双击打开，你会发现有个工作表名为**Demo**，A1单元格的内容为**Just for demo**


## 小结
在此单元中我们使用调试和日志完整运行了整个流程，并解决了一个异常错误。但是调试和日志在实际业务中的作用远高于此，你可以查看有关[调试](https://academy.bottime.com/wiki/Studio/Debugging.md?)的具体文档说明，后续课程中也会有相关课程讲解，让我们一起继续学习吧。