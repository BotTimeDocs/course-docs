# 完整的 RPA 流程包括的模块

这节课我们来探讨一个完整可交付的 RPA 流程包含哪些模块，并介绍流程中 *创建日志* 和 *环境初始化* 模块。

实际做过 RPA 实施项目的同学都清楚一个能够运行的 RPA 项目和一个实际交付的 RPA 项目之间的巨大区别。简单来讲，一个实际交付的 RPA 项目需要考虑到 RPA 流程运行的稳定性，健壮性和可回溯性，而一个能够运行的 RPA 项目只能够保证在开发环境中能够完成 RPA 项目的需求。

## 完整流程
一般来讲，一个完整可交付的流程包含以下模块：
- 创建日志
- 环境初始化
- 业务数据处理
- 主业务稳定性处理
- 结束处理

如图：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E5%AE%8C%E6%95%B4%E6%B5%81%E7%A8%8B.jpg)

## 创建日志模块

在确定日志模块的创建方式，如决定我们的日志文件是按当天还是按当月、是按操作系统模块还是按照整个业务来创建，日志文件创建在哪个目录下等等问题时，我们必须考虑实际情况：流程是否需要每天运行、日志是否会展示给用户。

在本次课程中，我们以创建在项目路径下、创建当天日志为例。

### 创建步骤
1. 建立名为*创建日志*的子流程
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E5%88%9B%E5%BB%BA%E6%97%A5%E5%BF%97.jpg)

2. 依次检查日志文件夹/日志文件是否存在，如不存在则新建文件夹/文件。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E6%96%87%E4%BB%B6%E5%A4%B9%E6%98%AF%E5%90%A6%E5%AD%98%E5%9C%A8.png)
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E6%96%B0%E5%BB%BA%E6%96%87%E4%BB%B6%E5%A4%B9.png)
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E6%97%A5%E5%BF%97%E6%98%AF%E5%90%A6%E5%AD%98%E5%9C%A8.png)
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E6%B7%BB%E5%8A%A0%E6%97%A5%E5%BF%97%E8%B7%AF%E5%BE%84.png)

3. 编写在主流程中调用子流程并传参，实现创建日志的逻辑。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E8%B0%83%E7%94%A8%E5%AD%90%E6%B5%81%E7%A8%8B.png)
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E6%97%A5%E5%BF%97%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%84.png)

    此处演示的日志文件路径是：
    > 日志文件夹路径 + "\" + System.DateTime.Now.ToString("yyyyMMdd") + ".txt"

4. 运行流程，日志文件成功创建。

    <video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E5%88%9B%E5%BB%BA%E6%97%A5%E5%BF%97.mp4" controls="controls" width="700px" />

## 实现环境初始化
环境初始化模块主要为流程运行前，给流程提供一个干净的运行环境做准备，比如关闭流程所要执行的 Excel 文件，浏览器等等。根据项目的不同，需要进行不同的环境准备。

本文演示常见的环境准备项：杀进程和执行垃圾回收。其他常见的环境准备项还有：登录网页系统等。

### 使用*执行命令行*组件杀进程

关闭 Chrome 的命令是： 

    >taskkill /f /im Chrome.exe

关闭 Excel 的命令是：

    >taskkill /f /im EXCEL.exe

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E6%9D%80%E8%BF%9B%E7%A8%8B.png)

## 执行垃圾回收

执行 C# 命令实现垃圾回收：

    >GC.Collect()

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/logAndInit/%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6.png)