# 制作云扩ViCode - 流程配置

大家好，上一节课，我们简单介绍了一下ViCode的基本操作及ViCode编辑器的构造。今天这节课我们来实践通过ViCode编辑器创建第一个ViCode。

通过这节课你将了解到：

- 初始化流程组件
- 界面配置
- 设置参数组件
- 全局配置

## 前提条件

1. 已创建一个含参数的流程（编辑器教程）

2. 已将流程上传至控制台，并创建关联的流程部署（控制台教程）

3. 创建ViCode（上一节课程）

## 初始化流程组件

通过前序课程，新建一个ViCode，进入ViCode编辑器。

1. 选中页面，拖拽“流程”组件至页面内。

2. 在配置窗口内选择你想要的流程部署，点击**创建**，流程组件即可添加至当前页面。

![devmode](https://docimages.blob.core.chinacloudapi.cn/images/Kris/academy/secoundworkflow/addworkflow.png)


初始化流程组件时，系统将根据参数列表及参数类型，在模拟界面加载出参数对应的默认组件。 以下为参数类型及其对应的默认组件类型：

- Boolean：是/否
- Double：数字
- Int32：数字
- Int64：数字
- System.String：文本
- System.DateTime：日期
- System.String[]： 批量文件上传
- 其他类型：文本

## 界面配置

接下来，我们开始调整界面显示，使ViCode的界面展示达到预期的样子：

- **控件排序**：当你希望交换控件顺序时，你需要单击控件选中，使用拖拽的方式将控件移动至你想要的位置。
- **控件删除**：当你想要删除界面上的组件时，你可以单击选中想要删除的组件，单击 Delete 键删除组件。
- **控件是否显示**：选中整个流程组件，在右侧列表调整参数是否需要显示在ViCode页面上。 当你取消勾选参数时，参数不会出现在页面上。 当你勾选参数时，参数会出现在页面上。

![devmode](https://docimages.blob.core.chinacloudapi.cn/images/Kris/academy/secoundworkflow/workflow2.png) 

## 设置参数组件

1. 单击模拟界面的组件，选中单个组件后，即可在右侧编辑组件信息。

![devmode](https://docimages.blob.core.chinacloudapi.cn/images/Kris/academy/secoundworkflow/workflow3.png)

当前支持对组件的设置如下：

- 参数名：展示流程中当前参数的名称。
- 展示名称：组件对应标签的名称。
- 是否可更改：不可更改的参数，系统将作为标签展示参数默认值，若没有设置默认值，则仅展示标签。
- 是否必填: 打开此选项意味着我们会在前端校验当前参数必填。
- 参数类型：展示流程中当前参数的数据类型。
- 组件类型：允许用户调整交互组件类型，不同参数对应的组件选择列表，如下图所示。

![devmode](https://docimages.blob.core.chinacloudapi.cn/images/Kris/Apps/setcomponent1.png)

2. 你对组件的所有内容的编辑，都可即时在模拟界面上查看。

## 全局配置

1. 点击左侧第二个菜单，即可进入全局配置界面。

2. 你可以在这里对ViCode的名称，图标，布局，说明进行编辑和调整。


   > **说明：**
   >
   > 目前我们只支持流水响应式页面布局，未来我们将开放更多元的布局方式供用户定义界面。


   ![全局配置](https://docimages.blob.core.chinacloudapi.cn/images/Kris/academy/secoundworkflow/workflow4.png)

完成以上步骤后，点击右上角保存，第一个ViCode就完成啦。