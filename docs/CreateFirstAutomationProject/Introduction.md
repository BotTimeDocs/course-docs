欢迎使用云扩RPA编辑器。在本模块中将会帮助你从头开始创建一个自动化项目。

在此单元中，你将学习到：
- 关于自动化项目相关的基本概念
- 如何基于智能录制器创建自动化项目

云扩RPA编辑器是一个图形化的流程编辑应用，可以让你根据业务需求生成自定义项目。使用云扩RPA编辑器提供的丰富的组件，无需编写代码，直接拖拖拽拽即可将业务流程转换成自动化流程。

在项目开始之前，你需要了解以下几个概念：
1. 自动化项目
2. 流程文件及类型
3. 组件
4. 变量
5. 智能录制器

**自动化项目**是用于管理所有和自动化任务相关的流程文件的集合，是你进行开发、发布以及部署给机器人运行的基本单元。通常，每一个独立的业务流程都应该为其创建一个新的自动化项目。

在每一个自动化项目中都会默认存在一个Main.xaml文件，此文件就是**流程文件**，是一个自动化项目运行的起点。同时，你也可以为自动化项目添加多个子流程文件，供主流程文件调用。

对于流程文件，分为**序列**和**流程图**两种类型。序列是一个线性过程，可以充当单个的组件块，而流程图则主要用于更加复杂的业务流程。

每一个自动化流程都是由许多个不同的**组件**组成，每一个组件都被赋予不同的功能，通过将每个组件连接起来，让其相互配合，就可以轻轻松松将复杂的业务流程转换成自动化流程，从而提升工作效率。有关组件的详细信息，请查看[云扩组件库](https://academy.encoo.com/zh-cn/wiki/Activities/ComponentsIntroduction.md)。

**变量**来源于数学，在初等数学中，变量是表示数字的字母字符，具有任意性和未知性。
通常，在数学公式中，变量存储的是数字。而在云扩RPA编辑器中，变量存储的是各种类型的值，其主要用于数据传递。有关变量的详细信息，请查看[变量](https://academy.encoo.com/zh-cn/wiki/Studio/Variables/Variables.md)。

**智能录制器**的存在，为你在自动化业务流程时节省了大量时间，它可以轻松地在屏幕上捕捉用户操作将其转换为一个序列存储下来。有关录制器的详细信息，请查看[智能录制](https://academy.encoo.com/zh-cn/wiki/Studio/Recording/Recording.md)。

若想创建自动化项目，将从编辑器主界面开始操作，通过项目面板的新建项目创建自动化项目，然后使用组件面板的各种组件编辑自动化流程，让其成为更有效的业务工具。有关编辑器主界面的详细信息，请查看[用户界面](https://academy.encoo.com/zh-cn/wiki/Studio/Introduction/TheUserInterface.md)。

![1](https://docimages.blob.core.chinacloudapi.cn/images/Studio/userInterface/1.PNG)  菜单栏 - 显示各种菜单，为编辑器提供一些功能入口。

![2](https://docimages.blob.core.chinacloudapi.cn/images/Studio/userInterface/2.PNG)  工具栏 - 显示各种工具按钮，使你可以开展广泛的活动。

![3](https://docimages.blob.core.chinacloudapi.cn/images/Studio/userInterface/3.PNG)  工具面板 - 显示各个面板的分层结构图，使你可以访问特定的任务。

![4](https://docimages.blob.core.chinacloudapi.cn/images/Studio/userInterface/4.PNG)  编辑区域 - 显示正在处理的自动化项目。

![编辑器主界面](https://docimages.blob.core.chinacloudapi.cn/images/Studio/userInterface/mainInterface.PNG)
