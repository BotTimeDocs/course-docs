# 完整的 RPA 流程包括的模块（下）

## 流程概述

如上节课所说：一个完整的流程一般包括“日志创建”、“环境初始化”、“主业务数据处理”及“结束处理”等模块。其中上节课我们探讨了如何进行日志创建与初始化环境。这节课我们来探讨“主业务数据处理”与“结束处理”及主数据处理的稳定性问题。在实际项目中，流程的稳定性/健壮性是最需要关注的部分，因为这是一个流程价值体现的最最重要的一个环节。一般情况下，我们会使用大量的错误捕获组件提升流程的健壮性。

我们以在企查查网站查询企业信息并保存到 Excel 文档作为演示内容。流程示意图如下：

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E5%AE%8C%E6%95%B4%E6%B5%81%E7%A8%8B.jpg)


首先，将需要查询信息的企业名称及所要查询的企业信息title保存在Excel文件中，如下图（可根据自己的真实需求来保存企业信息）：

## 流程开发步骤

### 添加流程图
打开云扩编辑器，选择“流程模板”项目（接上节课项目）并打开，拖入“流程图”组件并重命名。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E6%B5%81%E7%A8%8B%E5%9B%BE.png)

### 读取 Excel 文件中的企业信息
打开 Excel 文件。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E6%89%93%E5%BC%80Excel%E6%96%87%E4%BB%B6.png)

获取末行号作为循环次数。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E8%8E%B7%E5%8F%96%E5%BE%AA%E7%8E%AF%E6%AC%A1%E6%95%B0.png)

### 打开企查查

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E6%89%93%E5%BC%80%E4%BC%81%E6%9F%A5%E6%9F%A5.png)

### 循环查询

建立循环：以单元格索引为递增变量，从第2行开始递增，循环至单元格索引和Excel最大行数相等。
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E5%BE%AA%E7%8E%AF.jpg)

### 添加错误捕获组件
在企查查网站上查询信息时，我们经常会遇到一些问题，导致组件会抛出异常，循环停止，流程无法继续查询下一个企业信息。这些问题可能是：
 - 网页不稳定；
 - 需要查询的企业不存在；
 - 其中某一个字段不存在。
 
在项目中，我们需要捕获异常信息并做相应的处理，然后进行处理下一条数据的正常查询。这时**错误捕获（Try Catch）**组件就可以发挥它的作用。

在本例中，我们将获取企业信息部分作为 Try 的内容，在 Catch 中处理异常，在 Finally 中添加一个循环完成后必须要做的部分。
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/tryCatch.png)

### 在 Try 中写入正常业务流程

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/FlowChart.png)

使用 *读取单元格* 组件，以读取企业信息。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/readCell.png)

使用拼接查询结果 url 的方式，访问查询结果页面。
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/search.png)

点击访问企业信息。
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/click.png)

编辑*点击*组件。这个组件应用在循环中。因此，我们需要对该组件的选择器进行编辑，使用通配符替代企业名称，使在不同关键词的搜索结果页上都能够完成点击操作。

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E4%BF%AE%E6%94%B9%E9%80%89%E6%8B%A9%E5%99%A8%E4%BF%A1%E6%81%AF.mp4" controls="controls" width="700px" />

在上面的视频中，我们除了将 *Window8 的 *Name* 中企业名称改为通配符，还将 *WebElement* 中的*Sinfo* 改为 XPath。实际达成的效果是一致的。实际项目中使用何种修改方式只为实际的稳定性进行选择。实际交付时，我们也经常需要在获取的 XPath 内容上进行修改。

检查页面中的企业信息是否为 *table* 元素。如果是，我们可以拖入*获取结构化数据*组件一次性获取所有需要的企业信息；如果不是，那么可以用*获取文本*组件来逐个获取。此处，我们发现是 *table* 元素。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/table.png)

使用*获取结构化数据*组件，获取信息。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E8%8E%B7%E5%8F%96%E7%BB%93%E6%9E%84%E5%8C%96%E4%BF%A1%E6%81%AF.png)

将数据写入到 Excel 文件中。写入时，确认字段正确。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E5%AD%97%E6%AE%B5.png)
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E5%86%99%E5%85%A5.png)

获取的有些数据因为含有脏数据，还需进行额外处理。我们使用 *确认框* 或 *写入日志* 提供额外检查。脏数据处理时，用到两个字符串处理函数，请自行查阅资料了解使用细节：

    - `Split()`
    - `Trim()`

关闭当前企业信息页面。
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E5%85%B3%E9%97%AD%E9%A1%B5%E9%9D%A2.png)

### 在 Catch 中写入异常处理逻辑

常用的异常处理手段有：
1. 用*写入文件*组件来记录异常，方便后续查询异常原因。
2. 如果因为网络问题导致网页上数据没有正确显示，可以用*刷新浏览器*组件进行刷新，甚至可以重新进行环境初始化.
3. 如果需要获取的某一个字段有可能会出现异常（字段不存在等），也可以对该字段用*Try Catch*方法进行针对性处理。

以下以*写入文件*为例：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E5%86%99%E5%85%A5%E6%96%87%E4%BB%B6.png)

### 在 finally 中进行单元格索引递增
通过单元格索引递增，获取下一条数据。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E9%80%92%E5%A2%9E.png)

编制流程时，参考以下视频：

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/tryCatch/%E4%BC%81%E6%9F%A5%E6%9F%A5%E5%BE%AA%E7%8E%AF%E6%9F%A5%E8%AF%A2.mp4" controls="controls" width="700px" />