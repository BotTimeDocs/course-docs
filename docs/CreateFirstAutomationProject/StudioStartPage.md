# 编辑器界面操作说明

大家好，编辑器作为流程开发者必不可少的装备，本节课将带领帮助大家了解一下编辑器整体界面操作。

编辑器在界面上主要分为两大模块：**开始主页**和**编辑主页**。

## 开始主页

首次打开编辑器，我们会进入编辑器的开始主页。开始主页中主要可以进行以下一些操作：

1. **新建项目**

    在开始页面或新建页面，你可以新建自动化项目。除此之外，在新建页面还提供了项目模板和流程市场，帮助你快速熟悉如何新建并编辑一个自动化项目。

    在流程市场中，你可以搜索任何你感兴趣的流程，并在编辑器中打开运行，查看效果。或进行更改，将其完善成为你自己想要的效果。

    ![新建](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/newProject.png)

2. **打开项目**

    在开始页面或打开页面，你可以在最近使用列表中，查看并打开最近使用过的流程。除此之外，在打开页面还可以打开本地的项目进行编辑，甚至还可以查看控制台上所有的流程，进行下载编辑。

    > **说明：**
    >
    > 针对控制台流程，需要使用控制台账号登录编辑器才可以看到。

    ![打开](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/openProject.png)

3. **辅助工具**

    在工具页面，你可以看到在项目编辑过程中需要安装或使用的各种应用或扩展。通过这些工具，你可以方便、快速地完成某些特定场景的流程编辑。

    比如，安装 Chrome 扩展后，你可以对 Chrome 浏览器进行各种自动化操作：鼠标点击、获取数据等等。

    ![辅助工具](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/tools.png)

4. **全局设置**

    在设置页面，可以帮助你完成一些编辑器的全局设置，一键修改，应用所有。

    ![全局设置](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/settings.png)

5. **提供帮助**

    在帮助页面，你可以看到很多帮助链接，它们可以将你指引到各个神奇的网站，有些可以帮助你熟悉产品的使用，有些可以帮助你答疑解惑，还有些能够让你体验不一样的自动化。

    除此之外，你还能够了解到产品的相关信息，比如版本号信息，你还可以通过此页面更改激活方式。

    ![帮助](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/help.png)

## 编辑主页

在编辑器中，每一个流程都是由许多组件串联起来的，组件之间则使用箭头连接起来。

现在，我们新建一个项目，看一下如何在编辑主页编辑流程。

1. **新建项目**

    在开始页面中，新建一个流程项目，创建完成，将会进入编辑主页。

    ![新建项目](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/newFlowProject.png)

2. **编辑主页布局**

   进入编辑主页，可以看到编辑主页主要分为以下几个部分：

   ![编辑主页](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/editorPage.png)

   | 区域            | 说明                                                         |
   | --------------- | ------------------------------------------------------------ |
   | 菜单栏          | 位于界面最上方，是一种树形结构，为编辑器提供一些功能入口，例如，文件操作、运行调试。 |
   | 工具栏/工具面板 | 位于界面最左侧，通过点击工具栏的图标按钮可以打开对应的工具面板，使你能够针对项目进行不同的处理操作。 |
   | 编辑区域        | 是编辑器的主要区域，用于编辑项目中具体的功能。<br/>在编辑区域底部，可以看到变量、参数和导入按钮，可以帮助你对这些信息进行管理。 |
   | 属性面板        | 位于界面右侧，用于设置组件的属性，当我们选择任一组件后，在属性面板能够查看这个组件的属性信息，并进行编辑。 |
   | 状态栏          | 位于界面最下方，展示打开的项目和编辑器通知等相关信息。       |

3. **添加组件**

   介绍完界面布局，我们来讲一下如何添加组件到编辑区域。

   打开编辑主页的组件面板，通过以下方式可以添加组件：

     - 方式一：鼠标按住要添加的组件，拖动组件到编辑区域，即可将组件添加到编辑区域；然后拖动 Start 节点连接到拖入的组件。

        ![添加组件](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/addActivity1.gif)

     - 方式二：鼠标按住要添加的组件，拖动组件到 Start 节点上 。  

        ![添加组件](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/addActivity2.gif)

4. **选择组件**

    - 单选组件

        通过鼠标点击，就能够选择组件，选择一个组件后，我们可以从属性面板查看或者修改这个组件的属性信息。

        此外，选择组件并右击组件，我们还可以对这个组件进行各种设置，比如：复制粘贴、启用/禁用组件等操作。

        ![单选组件](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/chooseActivity.png)

    - 批量选择组件

      - 方式一：选择一个组件，然后按住 Ctrl 键，并使用鼠标左键，可以自由选择多个组件。    

        ![批量选择组件](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/chooseActivity1.gif)

      - 方式二：按住鼠标左键进行框选，即可完成批量选择 。     

        ![批量选择组件](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/chooseActivity2.gif)

5. **修改属性**

    我们添加组件主要是为了流程编辑，而设置组件属性就是中间必不可少的一个环节。比如：打开浏览器组件，有许多属性。在“网址”这个属性中填入 *"https://www.encoo.com"*，然后点击运行，就会打开云扩官网。  

    修改属性的时候，除了下拉的属性，其他的属性都可以使用各种各样的数据类型，比如字符串、整数以及一些表达式。

    > **说明：**
    >
    > 填写属性值时，如果属性值是字符串，需要以英文双引号括起来 。

    ![修改属性](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/openBrowser.gif)

6. **变量管理**

    大多数情况下，部分组件执行后，会产生一个执行结果，而这个执行结果往往需要进一步处理，此时则需要介质来暂存获取到的数据，这个介质就是**变量**。只要是需要返回数据的组件，输出类属性就是将数据存储到变量里，然后进行任意操作。

    ![执行结果](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/result.png)

    所有的变量都需要定义后才能使用，在变量列表处，可以手动创建一个变量。针对需要删除和修改的变量，直接在变量列表处进行操作即可。

    ![变量管理](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/mangeVariables.png)

7. **其他常用操作**

   - 项目执行

      通过运行面板可以运行/调试项目，使用停止按钮则可以快速停止流程执行。    
       ![执行](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/Run.png)

   - 项目发布

     编辑成功的项目可以一键发布到控制台、本地机器人或市场中。    
       ![发布](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/TheUserInterface/publish.png)

通过上述介绍，我们已经初步了解编辑器的界面组成及简单操作，接下来，你可以初步尝试一下如何编辑一个简单的项目了。
