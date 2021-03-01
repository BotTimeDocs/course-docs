# 获取天猫买家评价并存入Excel（上） 

这节课我们来看看一个真实案例 - 获取天猫买家评价并存入Excel文件的流程是如何开发的。题外话，相信所有的商家对买家的评价都极其关注，就像我们也很在乎所有小伙伴在使用云扩RPA编辑器开发流程后对我们云扩RPA产品的评价一样，好评、差评对我们都很重要，所以，很期待你使用后的真实感受反馈。言归正传，我们继续讨论本节课流程开发的步骤及思路。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩 RPA 编辑器运行的硬件&软件要求（<https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?>）。

2. 打开云扩官网（<https://www.encoo.com/>）下载编辑器并安装。

3. 准备天猫账号及旗舰店服装数据Excel表格，如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-1.png)

## **流程设计图示：**

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-2.png)
（<font color=#0000FF> 本节课完成开发至搜索店铺模块，下节课接着开发剩下的模块并运行流程 </font>）
## **流程操作步骤：**
**创建项目**
1. 点击开始 ->新建，选择“从模板新建”中的“通用网页流程”，输入项目名称：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-3.png)

2. 按照默认模板，修改**打开浏览器**组件的URL，获取等待网页加载完成的元素：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-4.png)
(URL： https://login.tmall.com/?redirectURL=https%3A%2F%2Fwww.tmall.com%2F)

**登录网页**
1. 拖入**序列**或**流程图**组件并命名为：登录，拖入两个**输入文本**组件，分别命名为“输入用户名”和“输入密码”，指定用户名与密码输入框元素，再将用户名与密码设置为参数并作为输入文本组件的输入内容：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-5.png)

2. 拖入**点击**组件，指定登录按钮元素： 
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-6.png)
以上实现登录天猫网站，接下来我们从Excel中获取数据，然后循环输入至网页中并获取对应数据：

**获取Excel中行数据**
1. 拖入**打开/新建**组件，并指定Excel文件：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-7.png)

2. 此时我们需要考虑，Excel中有很多数据，必须要循环操作，那么循环多少次呢？这里，我们用**获取末行号**来获取总数据数量，以此作为后续的循环最大次数(lastRow):
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-8.png)

3. 拖入**循环操作（While）**，创建变量count，变量类型为int32，设置默认值为2（根据Excel表中第一条数据的行数做决定，在本例中第一条数据位于Excel第2行），值输入循环条件 count <= lastRow：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-9.png)

4. 拖入**错误捕获（Try Catch）**组件，（循环操作中我们一般都加入tryCatch组件来保证即便其中一条数据运行失败，都会继续循环下去），拖入**流程图**组件来模块化接下来的操作： 
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-10.png)

5. 拖入“读取行/列数据”组件以此来读取Excel中品牌与服装编号数据，设置起始单元格数据（"A" + count）、定义输出变量（arrayData）：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-11.png)

**判断品牌数据是否为空**

1. 上步操作中获取行数据（品牌及服装编号）后，我们需要判断“品牌”数据是否存在（因为从Excel文件中可见品牌在合并单元格中，合并单元格数据默认在第一行，合并单元格后面行中数据为空）：判断条件为： Convert.ToString(arrayData[0]) == ""
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-12.png)

**进入品牌官方旗舰店**

1. 如果品牌数据不为空，则需要输入并查找对应官方旗舰店。拖入**序列**组件用以模块化进入官方旗舰店功能，拖入**当前页跳转**组件（该组件为循环考虑，在原有的标签页做跳转可减少操作步骤），输入目标跳转URL：https://www.tmall.com/：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-13.png)
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-14.png)

2. 拖入**输入文本**组件重命名为输入品牌名称并设置输入数据 arrayData[0] + "官方旗舰店"；拖入**点击**组件，指定“搜索”按钮元素；拖入**点击**组件，指定“进入店铺”按钮元素：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-15.png)

3. 以上操作完成搜索品牌官方旗舰店并进入店铺，那么这里我们需要注意，进入官方旗舰店会自动新起一个标签页，为了后续操作不混乱，我们关闭旧标签页：拖入**关闭标签页**组件，指定标签页元素并打开选择器查看定位元素节点数据，如果有固定某品牌名称，我们用通配符*来代替用以适用于更多品牌元素标签页，具体请见如下视频：
<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/closeBrowserTab.mp4" controls="controls" width="700px" />

   以上操作完成搜索店铺功能。

   各位，本节课内容就到此结束，下节课我们继续开发至流程完整并试运行。
