# 获取整表数据
此节课程将讲述如何使用**获取结构化数据**组件获取到整表数据

## 准备工作
1. 打开云扩**编辑器**，新建一个空白项目，搜索**序列**组件并拖拽至设计面板，设为开始结点,双击打开序列
2. 打开Chrome浏览器，输入 **"http://www.chinaports.com/chuanqibiao/2/null/null/null/query"** 并点击跳转

## 打开要提取数据的网页
此步骤用于打开数据源所在的网页，并在流程运行结束后关闭浏览器

2. 搜索**打开浏览器**组件并拖拽放置于**序列**内
3. **网址**属性写入 **"http://www.chinaports.com/chuanqibiao/2/null/null/null/query"**; **浏览器类型**选择 **Chrome**;勾选**结束后关闭**

## 获取整表数据
4. 搜索**获取结构化数据**组件并拖拽放置于**打开浏览器**内
5. 点击**指定数据源**，将鼠标放到表内任一数据上，高亮显示时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/1.png)

6. 弹出下图窗口后，点击**是**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/getWhole.png)

## 预览整表数据
此步骤将获取到的数据展现给用户，可用于预览数据

7. 被获取到的数据被展示在下图。点击**完成**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/WholeTable.png)

## 翻页获取更多数据
此步骤可用于指定下一页按钮，并在运行时实现自动翻页功能

8. 点击下图的**是**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/next.png)

9. 将鼠标移动到**下一页**，高亮显示时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/next2.png)

## 设置最大提取条数
此步骤可用于限制运行时获取数据的最大条数。例如当整表有大量数据时，若全部获取会消耗时间和抓取不必要的数据；此时可通过设置**最大提取条数**来实现：当获取到的数据达到规定的最大条数时，运行结束

10. 点击**获取结构化数据**组件，**最大提取条数**属性写入**30**

## 将获取到的数据存入数据表

11. 点击设计面板下的 **变量**标签，并新建一个**DataTable**类型的变量，命名为**dt**
12. 点击**获取结构化数据**组件，输出**数据表**属性写入**dt**

## 验证获取到的数据行数
13. 搜索**写入日志**组件并拖拽放置于**序列**内
14. **日志内容**属性写入**dt.Rows.Count.ToString()**

## 运行查看结果数据表信息条数
15. 点击**运行**按钮，结束后查看运行日志，可看到输入数据表内信息条数为**30**

## 如何在编辑器中下载并使用本课程示例
1. 打开编辑器，在工具栏点击【流程市场】
2. 搜索此课程名称即可找到此流程
3. 选中流程并点击【下载】图标，在【新建项目】弹窗中输入【项目名称】
4. 点击【创建】此时将会在本地创建一个新的项目
5. 在【工作目录】面板即可打开创建的项目