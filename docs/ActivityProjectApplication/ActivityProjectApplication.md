# 组件项目的应用

## 概述

**组件**是项目中可重复使用的模块，而通过**创建组件项目**，开发者可以将自动化项目中某些可重用的部分，封装成一个组件，在其他项目中使用。这样就可以减少重复的操作，提高流程开发效率。

比如，在一些需要用户登录才能继续进行使用的应用或网站中，就可以将用户登录模块封装成一个组件。在今后的自动化项目中，只要安装组件，就可以直接使用“用户登录”的功能，省时省力。

## 创建组件项目

这里用一个简单的例子来说明如何创建并应用组件项目：我们设计一个 Excel 文本替换的组件，帮助替换 Excel 中指定单元格的文本。我们希望把这个功能封装在一个组件里，以便今后使用。

1. 在编辑器开始主页，新建下选中“组件项目”，输入项目名称“Excel 文本替换”，点击“创建”

    创建完成后更改 xaml 文件名称，由“NewActivity”更改为“替换文本”

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/new%20Library.png)

2. 打开参数列表，创建 5 个字符串型（String）的输入参数，其将作为发布后组件的输入属性：
    - Excel 文件 -- 要替换文本的 Excel 文件所在路径
    - 工作表 -- 要替换文本的的 Excel 文件工作表
    - 单元格地址 -- 要替换文本的 Excel 文件单元格
    - 原文本 -- 要进行替换的原文本
    - 新文本 -- 要替换成的文本

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/arguments.png)

3. 从组件面板搜索“打开 / 新建”组件，并将其拖入到编辑区域连接至开始节点
4. 在该组件的属性面板，输入以下内容：
    - 文件路径：Excel 文件

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/openNew.png)

5. 从组件面板搜索“读取单元格”组件，并将其拖入到“打开 / 新建”组件内部
6. 在该组件的属性面板，输入以下内容：
    - 工作表：工作表
    - 单元格：单元格地址
    - 单元格内容： 单元格内容 --- 单击该字段后的输入框，输入**单元格内容**作为变量名称，全选**单元格内容**并使用快捷键 **Ctrl+B** 创建该变量

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/readCell.png)

7. 从组件面板搜索“替换文本”组件，拖到“读取单元格”组件下方
8. 在该组件的属性面板，输入以下内容：
    - 查找内容：原文本
    - 新内容：新文本
    - 源文本：单元格内容
    - 替换结果：结果 -- 单击该字段后的输入框，输入**结果**为变量名称，全选**结果**并使用快捷键 **Ctrl+B** 创建该变量

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/replaceText.png)

9.  从组件面板搜索“写入单元格”组件，拖到“替换文本组件下方
10. 在该组件的属性面板，输入以下内容：
     - 数据：结果
     - 单元格：单元格地址
     - 工作表：工作表

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/writeCell.png)

## 发布组件项目

组件项目创建完毕，但为了方便重复使用，我们可以使用“发布”功能，把这个组件项目发布成一个组件。

1. 首先，我们需要创建一个组件市场，来存放我们的组件。打开开始主页，来到设置下的管理市场
2. 点击加号（+），开始创建市场
    - 输入市场名称，如“Test”
    - 输入市场地址，可以使用本地文件夹路径，如“E:\ActivityMarket”
    - 勾选“启用”按钮，启用该组件市场

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/manageMarkets.png)

3. 返回编辑主页，点击菜单栏的“发布到组件市场”，打开发布窗口
    - 选择刚刚创建的目标市场
    - （可选）填写最新版本号，标识发布的版本。此处使用默认值
    - 填入此组件的描述信息，如“Excel 文本替换组件支持将 Excel 中符合条件的指定单元格文本内容替换为期望值。”
    - （可选）将项目中使用的所有依赖项打包到流程包中

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/publish.png)

## 安装并使用组件

如果你要在另外一个自动化项目中使用该组件包，需要先安装，将其添加为自动化项目的依赖项

首先准备好需要替换文本的 Excel 文件，此处以 demo.xlsx 为例，我们将指定单元格 B1 的“云扩”替换为“Encoo”

![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/demoFile.png)

1. 创建一个流程项目：替换 Excel 文本

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/newWorkflow.png)

2. 在组件面板或市场面板，点击“组件市场”，打开组件市场窗口
3. 选择之前创建的市场，搜索发布的组件包并选择。在我们的示例中，该组件包名为“Excel 文本替换”

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/install.png)

4. 单击“安装”，然后根据提示重新加载项目。此时，该组件包已添加到当前流程项目中，并在组件面板中可见

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/replaceTextActivity.png)

5. 从组件面板中，将“替换文本”组件拖入到编辑区域并连接到开始节点
6. 在该组件的属性面板，输入以下内容：
    - Excel 文件：“E:\demo.xlsx” -- 要替换文本的 Excel 文件所在路径
    - 工作表：“Sheet1” -- 要替换文本的的 Excel 文件工作表
    - 单元格地址：“B1” -- 要替换文本的 Excel 文件单元格
    - 原文本：“云扩” -- 要进行替换的原文本
    - 新文本：“Encoo” -- 要替换成的文本

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/useReplaceText.png)

7. 点击“运行”，可以看到 Excel 里的“云扩”已被替换为“Encoo”

    ![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Library/result.png)
