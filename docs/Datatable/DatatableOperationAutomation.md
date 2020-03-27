
# 操作数据表

在此单元中，将创建一个自动操作数据表的机器人，它可以获取CSV文件数据，并进行添加列、添加行、移除列、排序、筛选并将结果再保存至新的CSV文件


在此单元你将学习到：
- 使用[读取CSV文件](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/ReadCSV.md?_v=v2020.1)组件
- 使用[添加数据列](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/AddColumn.md?_v=v2020.1)组件
- 使用[添加数据行](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/AddRow.md?_v=v2020.1)组件
- 使用[移除列](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/RemoveColumn.md?_v=v2020.1)组件
- 使用[排序](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/SortDataTable.md?_v=v2020.1)组件
- 使用[筛选](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/FilterDataTable.md?_v=v2020.1)组件
- 使用[保存为CSV文件](https://academy.encoo.com/zh-cn/wiki/Activities/DataTable/SaveToCSV.md?_v=v2020.1)组件

准备工作：
- 一个名称为StudentsInfo的CSV文件(已包含在课程示例中, 下载即可得)，内容格式如下：

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-20.png)


## 创建项目

1. 在编辑器创建一个新的项目 DatatableOperationAutomationDemo
2. 右键项目名称并点击“打开所在文件夹”菜单，打开项目目录，创建文件夹“Files”,并将准备好的CSV文件放入此文件夹
3. 在【变量】面板分别创建2个数据类型为system.Data.Datatable且范围为MainFlow的变量：dtStudentsInfo 和 dtStudentsByFilter, 分别用于接下来存储获取CSV和操作后的结果，下方课程有详细介绍

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-21.png)



## 配置组件属性

1. 在【组件】面板【数据表】目录下找到【读取CSV文件】组件，并将其拖拽进新建项目Main设计面板中，用于读取CSV文件内容
    > **文件路径：** 输入将要读取的文件路径 ".\Files\StudentsInfo.csv"

    > **数据表：** 输入变量 dtStudentsInfo

2. 将【添加数据列】组件拖拽进设计面板，用于在数据表中添加新列，并与【读取CSV文件】组件建立连接。属性配置如下：
    > **数据表：** 输入变量 dtStudentsInfo

    > **列名：** 输入想要添加的列

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-22.png)


3. 将【添加数据行】组件拖拽进设计面板，用于在数据表中添加新行，并与【添加数据列】组件建立连接。属性配置如下：
    > **数据表：** 输入变量 dtStudentsInfo

    > **数组：** 输入想要添加的行内容 new Object[]{"7","Christina","16","100","Shenzhen","Girl"};

4. 将【移除列】组件拖拽进设计面板，用于移除数据表中的列，并与【添加数据行】组件建立连接。属性配置如下：
    > **数据表：** 输入变量 dtStudentsInfo

    > **列名：** 输入想要移除的列 "ID"

5. 将【排序】组件拖拽进设计面板，用于对整个数据表排序，并与【移除列】组件建立连接。属性配置如下：
    > **数据表：** 输入变量 dtStudentsInfo

    > **列名：** 输入想要排序的列名 "UserName"

    > **排序方式：** 选择排序方式 升序

6. 将【筛选】组件拖拽进设计面板,用于过滤数据表数据，并与【排序】组件建立连接。双击进入后点击【点击打开"筛选向导"】后在【筛选器向导】窗口配置如下图所示信息：

     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-23.png)

7. 将【保存为CSV文件】组件拖拽进设计面板中，并与组件【筛选】建立连接，用于将筛选后的数据表保存至CSV文件中。配置属性如下：

    > **文件路径：** 输入将要保存的文件路径 ".\Files\StudentsByFilter.csv"

    > **数据表：** 输入变量 dtStudentsByFilter

8. 流程创建完成，如下图所示：
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-24.png)

## 执行项目查看结果
1. 点击【运行】，在【日志】面板可以查看整个运行过程记录
2. 右键项目名称并点击“打开所在文件夹”菜单，进入文件夹“Files”，你将会看到一个StudentsByFilter.csv文件，双击打开，数据结果如下图，已成功删除列"ID"和过滤"City"是"Beijing"的数据，如下图：
     ![DataTable](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Datatable/DT-25.png)

## 如何在编辑器中下载并使用本课程示例
1. 打开编辑器，在工具栏点击【流程市场】
2. 搜索此课程名称即可找到此流程
3. 选中流程并点击【下载】图标，在【新建项目】弹窗中输入【项目名称】
4. 点击【创建】此时将会在本地创建一个新的项目
5. 在【工作目录】面板即可打开创建的项目
