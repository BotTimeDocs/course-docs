# Excel之执行宏
关于Excel的基本操作已经有了详细的了解。现在，我们学习一下如何使用Excel中的宏。

在此单元中，你将学习到：
- Excel执行宏

现在，我们需要在Excel文件中执行宏命令，以让单元格的大小适应单元格内容，那么如何实现呢？

你可以按照以下操作进行：
## 新建一个Excel启用宏的工作簿
首先，需要新建一个Excel文件，将其转换为“Excel 启用宏的工作簿”。
1. 打开编辑器进入主界面，在项目面板中，点击“新建项目”
2. 输入项目名称，例如“Excel执行宏”。
3. 在项目面板，选中该项目，打开右击菜单，选择“打开本地文件夹”
4. 在该项目所在目录下，右击新建一个Excel文件，并输入文件名，例如“宏命令”
5. 打开该文件，将其另存为“Excel 启用宏的工作簿”

    ![转换文件](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/OfficeExcel/xlsxToXlsm.PNG)

    >注意：
    >在开始处理宏之前，应启用“开发工具”。
    >1. 转到 "文件>"选项> "自定义功能区"。
    >2. 然后, 在 "自定义功能区" 部分的 "主选项卡" 下, 选中 "开发工具" 复选框, 然后按"确定"。

## 在“宏命令.xlsm”文件中，输入内容，并编辑宏
1. 按照以下格式，在文件中填入“感谢选择云扩RPA编辑器”

    ![写入内容](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/OfficeExcel/execute1.PNG)

2. 选择“开发工具”，双击打开“Visual Basic”，在Sheet1中写入以下内容，并保存
    Sub SetColumnsAutoFit()
        Range("A:A").Columns.AutoFit
    End Sub

    ![编辑宏](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/OfficeExcel/openVisualBasic.PNG)

## 打开“宏命令.xlsm”文件并执行宏

现在，我们已经在Excel文件中写入了内容，并编辑好了宏命令，那么便开始自动化执行宏吧

1. 从组件面板拖入一个“打开/新建”组件到编辑区域
2. 点击组件的浏览按钮选择文件路径，选择“宏命令.xlsm”文件
3. 从组件面板拖入一个“执行宏”组件到“打开/新建”组件内部
4. 在“执行宏”组件的属性面板，填入以下内容：
    - **Sub/Function名**："Sheet1.SetColumnsAutoFit"</br>要执行的宏的函数名称

    >注意：
    >通过“宏文件路径”，还可以对外部宏文件进行自动化。当该属性值为空时，默认执行工作表内部宏。宏文件仅支持.txt和.text。
  
最终，项目如下所示：

![Excel执行宏示例](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/OfficeExcel/Excel-executeMacro.PNG)

## 运行自动化项目

在运行面板中，点击“运行”，将会自动打开“宏命令.xlsm”文件，并且第一列的单元格大小适应为A1单元格内容。

>**说明：**
>
> 运行带有“执行宏”组件的项目，需在“打开/新建”组件的可选项属性中勾选“启用宏”属性。

![Excel执行宏](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/OfficeExcel/execute2.PNG)

## 如何在编辑器中使用示例

对于上述示例，你可以在编辑器的“流程市场”进行下载和使用。

1. 打开编辑器进入主界面，在“市场面板”中，点击“流程市场”
2. 在搜索栏中输入以下名称-Office Excel 之执行宏，搜索到对应流程
3. 选中该流程，点击“下载”，打开“新建项目”窗口
4. 输入自定义项目名称或使用默认名称，点击“创建”，即可下载成功
5. 在项目面板中，找到对应的项目，双击打开就可使用

除此之外，你还可以从云扩市场网站查找到该示例流程，点击[此处](https://marketplace.encoo.com/#/workflow/detail?packageId=Excel%E6%89%A7%E8%A1%8C%E5%AE%8F)前往查看。
