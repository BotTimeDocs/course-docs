# 获取天猫买家评价并存入Excel（下）

这节课我们继续[上节课](BestPractice/../GetInfoFromTianMao(1).md)未完成部分的流程开发。首先回顾下上节课内容：整个项目流程设计示意图、流程开发的创建项目、登录网页、获取Excel数据、判断品牌数据是否为空、进入品牌官方旗舰店部分，那么这节课我们将会学习到流程开发的**按服装编号搜索服装、判断搜索服装是否存在、获取服装当前的客户评价数量及具体的评价数据、写入评价数据、Excel中添加总结描述语**的具体数据链接部分。

接下来看看详细的开发步骤。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩 RPA 编辑器运行的硬件&软件要求（<https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?>）。

2. 打开云扩官网（<https://www.encoo.com/>）下载编辑器并安装。

3. 准备天猫账号及旗舰店服装数据Excel表格，如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-1.png)

## **流程设计图示：**
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-2.png)
（<font color=#0000FF> 本节课完成开发至搜索店铺模块，下节课接着开发剩下的模块并运行流程 </font>）
## **流程操作步骤：**
**按服装编号搜索服装**
1. 拖入**序列**组件用以模块化该功能块，拖入**输入文本**组件重命名为“输入服装编号”，指定输入框元素，输入服装编号数据arrayData[1].ToString()；拖入**点击**组件指定“搜本店”按钮元素：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-16.png)
注：指定元素后需打开“选择器”查看定位元素是否含有当前品牌店铺或者服装的固定信息，如果有，需要用通配符*替代(后续流程中不再重复讲解)，如下图所示

**判断当前服装是否存在**

1. 拖入**等待元素出现**组件查看是否有对应服装元素出现,注意：这里定位元素选择用**xpath**定位，具体方法如下：
<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getLinkInfo.mp4" controls="controls" width="700px" />

2. 设置**等待元素出现**组件的输出结果属性的变量exists（选中变量按Ctrl+B同步至变量区中），并将“失败后继续”改为“是”：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-17.png)

3. 拖入**流程决策**组件，输入判断条件（即上步操作中元素是否存在变量exists）:
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-18.png)
如果能搜索出对应服装（exists == true），则需要点击服装链接获取对应评价数据：

**获取评价数据**
1. 拖入**点击**组件，指定服装链接元素:
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-19.png)

2. 上步操作已打开服装信息页面，我们在拖入其他组件获取客户评价。拖入**序列**组件用以模块化该功能模块，重命名为“获取评价数据”，拖入**获取文本**组件获取“累计评价x”文本数据，设置输出变量：countPJ；并用**提取文本**组件从文本“累计评价x”中获取评价具体数据，输入获取数字文本的正则表达式\d+，设置输出变量resultCount：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-20.png)

3. 拖入**点击**组件，指定“累计评价x”元素；拖入**获取结构化数据”**组件用以获取客户具体评价数据，我们用该组件进行翻页获取，注意设置以下属性：

   a. 指定元素时选择自动点击下一页翻页；

   b. 打开“下一页”与整个组件的“选择器”窗口将当前服装的固定字符用通配符*代替；

   c. 设置两页之间间隔时间为2000~5000之间的随机数时间：创建变量time，数据变量为Random，初始化默认值为 new Random()，添加随机时间至右侧属性“获取下一页数据延迟”: Convert.ToInt32(time.Next(2000,5000));

   d. 设置最大提取条数：Convert.ToInt32(resultCount)；

   e. 添加输出数据表变量dt 并按Ctrl+b同步至变量区：
   ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-21.png)

4. 如果搜索不出对应服装（exists == false），则在该行Excel中写入备注：“无此商品”。拖入**写入单元格**组件，重命名为“写入备注”，设置工作表名、单元格及备注：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-22.png)

**评价数据写入Excel中**

根据Excel文件格式及获取的累计评价数据来看，我们不可能将所有评价数据写入Excel的工作表“Sheet1”中，那么这里我们设计为：同一编号的服装累计评价数据写入单独的工作表中，并在Sheet1对应的数据行中添加具体数据的链接，如果累计评价为0，则备注“累计评价0”，不需另加新工作表。

1. 拖入**流程决策**判断累计评价数据是否不为0（或为0，根据自己喜好添加）： Convert.ToInt32(resultCount) != 0，如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-23.png)

2. 如果累计评价不为0，则拖入**序列**组件用以模块化写入数据功能模块：

   a. 拖入**写入行/列数据**组件写入客户评价数据的标头：评价、尺寸颜色、买家，写入方式为 new List<String>{"评价","尺寸颜色","买家"}，工作表定义为：品牌名称_服装编号，写入方式为： arrayData[0]+"_"+arrayData[1]，起始单元格：A1

   b. 拖入**写入区域**组件写入客户累计评价数据，工作表定义为：arrayData[0]+"_"+arrayData[1]，写入数据：dt，起始单元格：A2
   ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-24.png)
 
   c. 将工作表 “arrayData[0]+"_"+arrayData[1]”中的数据链接到工作表“Sheet1”对应的数据行中。我们用“执行宏”组件来完成，首先录制添加链接的宏代码，如下面视频所示：
   <video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/recordVBACode.mp4" controls="controls" width="700px" />

   录制之后根据实际传入参数进行修改后存入txt文件中。修改后最终代码如下：
   ```
   Sub 添加链接(ByVal count As Integer, ByVal sheetName As String, ByVal countPJ As String)
    Sheets("Sheet1").Select
    Range("C" & CStr(count)).Select
    ActiveSheet.Hyperlinks.Add Anchor:=Selection, Address:="", SubAddress:= _
        sheetName & "!A1", TextToDisplay:= countPJ & "(点击查看详情)"
   End Sub
   ```
   d. 拖入**序列**组件用以模块化添加链接功能模块，拖入“赋值”组件，将工作表名赋给变量sheetName，如：sheetName = arrayData[0]+"_"+arrayData[1]

   e. 拖入**执行宏**组件，设置宏文件路径、实参（new List<String>{Convert.ToString(count),sheetName,countPJ}）及方法名，如下图所示：
   ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-25.png)

3. 如果累计评价为0，则拖入**写入单元格**组件，输入工作表“Sheet1”及单元格“"C" + count”，数据countPJ
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-26.png)

4. 以上操作步骤已完成一条数据处理的完整流程，接下来我们需要考虑循环条件，count <= lastRow中count的递增。拖入**赋值**组件，设置count递增：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-27.png)

5. 接下来我们设置tryCatch中的Catch部分，选择Exception为System.Exception，并添加错误日志。拖入**写入日志**组件，输入日志内容为：exception.Message
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-28.png)

6. 在Finally中，拖入**关闭标签页**组件用以处理完一条数据之后关闭当前服装标签页:
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-16.png)

至此，所有流程已开发完成，保存并运行流程，查看流程运行哪里会出现错误，如果有错，则需要根据实际情况调试并做流程相应修改。一般，因为数据有错需要进行环境初始化等操作我们可添加在Catches模块中。下面流程运行视频供参考：
   <video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/GetInfoFromTianMao/getInfoFromTianMao-final.mp4" controls="controls" width="700px" />
