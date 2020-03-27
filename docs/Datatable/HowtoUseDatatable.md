
# 实现一个自动处理数据表的机器人

在此单元中，将创建一个自动操作数据表并输出CSV文件的机器人，它可以搭建一个数据表并可与CSV文件中的数据合并，删除多余列后再保存至CSV文件


在此单元你将学习到：
- 使用[读取CSV文件](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/ReadCSV.md?_v=v2020.1)组件
- 使用[搭建数据表](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/BuildDataTable.md?_v=v2020.1)组件
- 使用[联结数据表](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/JoinDataTable.md?_v=v2020.1)组件
- 使用[预览数据表](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/PreviewDataTable.md?_v=v2020.1)组件
- 使用[移除列](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/RemoveColumn.md?_v=v2020.1)组件
- 使用[保存为CSV文件](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/SaveToCSV.md?_v=v2020.1)组件

准备工作：
- 一个名称为StudentsBasicInfo的CSV文件(已包含在课程示例中, 下载即可得)，内容格式如下：
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-1.png)

## 创建项目

1. 在编辑器创建一个新的项目 DatatableAutomationDemo 
2. 右键项目名称并点击“打开所在文件夹”菜单，打开项目目录，创建文件夹“Files”,并将准备好的CSV文件放入此文件夹
3. 在【变量】面板分别创建3个数据类型为system.Data.Datatable且范围为MainFlow的变量：dtStudentsBasicInfo、dtStudentsAddress 和 dtStudentsFullInfo
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-2.png)


## 配置组件属性

1. 在【组件】面板【数据表】目录下找到【读取CSV文件】组件，并将其拖拽进新建项目Main设计面板中，用于读取CSV文件内容
    > **文件路径：** 输入将要读取的文件路径 ".\Files\StudentsBasicInfo.csv"

    > **数据表：** 输入变量 dtStudentsBasicInfo

2. 将【搭建数据表】组件拖拽进设计面板,用于搭建一个将于其他表合并的数据表，并与【读取CSV文件】组件建立连接。双击【搭建数据表】后再点击【点击打开“数据表搭建器”】，配置数据信息，如下两图所示：

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-3.png)

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-4.png)


3. 将【联结数据表】组件拖拽进设计面板,用于将读取的CSV数据与刚搭建的数据表执行内连接操作，并与【搭建数据表】组件建立连接。在属性面板【数据表】字段中输入变量dtStudentsAddress，用于接收输出的数据结果。双击【联结数据表】后再点击【点击打开“连接配置”】，在【联结配置】窗口配置如下图所示信息：

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-5.png)

 4. 将【预览数据表】组件拖拽进设计面板,用于在运行时预览确认两个数据集联结后的结果。

 5. 将【移除列】组件拖拽进设计面板, 用于移除联结后数据结果中的多余列 S_ID，配置属性如下：

    > **显示名称：** 输入 移除列(S_ID)，用于将组件名称更改为更易理解的信息

    > **数据表：** 输入变量 dtStudentsFullInfo，用于接收将要被处理的数据表

    > **列名：** 输入 "S_ID", 指将移除数据表dtStudentsFullInfo中的列 S_ID 。 注意："列名，列索引和数据表列"这3个属性互斥，只能且必需填入一项

 5. 再将一个【移除列】组件拖拽进设计面板中并与组件【移除列(S_ID)】建立连接, 用于移除联结后数据结果中的多余列 S_UserName，配置属性如下：

    > **显示名称：** 输入 移除列(S_UserName)，用于将组件名称更改为更易理解的信息

    > **数据表：** 输入变量 dtStudentsFullInfo，用于接收将要被处理的数据表

    > **列名：** 输入 "S_UserName", 指将移除数据表dtStudentsFullInfo中的列 S_UserName 

 5. 将【读取CSV文件】组件拖拽进设计面板中，并与组件【移除列(S_UserName)】建立连接，用于将处理后的数据表保存至CSV文件中。配置属性如下：

    > **文件路径：** 输入将要保存的文件路径 ".\Files\StudentsFullInfo.csv"

    > **数据表：** 输入变量 dtStudentsFullInfo

6. 流程创建完成，如下图所示：
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-9.png)

## 执行项目查看结果
1. 点击【运行】
2. 出现【预览数据表】，已成功将两个数据表合并，但还未移除列S_ID和S_UserName前的数据表，如下图：
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-6.png)
3. 点击【确认】，项目执行完毕
4. 右键项目名称并点击“打开所在文件夹”菜单，进入文件夹“Files”，你将会看到一个StudentsFullInfo.csv文件，双击打开，数据结果如下图，已成功移除列S_ID和S_UserName：
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-7.png)


## 如何在编辑器中下载并使用本课程示例
1. 打开编辑器，在工具栏点击【流程市场】
2. 搜索此课程名称即可找到此流程
3. 选中流程并点击【下载】图标，在【新建项目】弹窗中输入【项目名称】
4. 点击【创建】此时将会在本地创建一个新的项目
5. 在【工作目录】面板即可打开创建的项目
