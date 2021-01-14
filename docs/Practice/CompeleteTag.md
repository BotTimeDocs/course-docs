# 记录完成标识 

大家好，这节课我们讲讲流程开发时必须要考虑的记录完成标识部分。在一个需要重复多次处理数据的业务流程中，比如，银行处理反洗钱存量数据，数据量大到几万甚至几十万条，尤其在处理数据涉及到的系统无法提供24小时服务的情况下，我们必须要考虑分批次、分时间段来运行对应的业务流程，那么给处理完的数据要做个标记，否则每次运行都从第一条数据开始。我们把这个标记称之为**完成标识**。那么，在开发流程时该如何来记录完成标识、记录完成标识会有哪些实现方式呢？请看下面的详细讲解。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）

2. 打开云扩官网（https://www.encoo.com/）下载编辑器并安装。

## **典型流程处理场景**

1. 循环将 Excel 文件中的数据搬运到 Web 端

2. 根据 Excel 中的数据从 web 端获取对应字段，然后再回填到Excel文件中

## **完成标识记录方式**

- 记录至 txt 文件方式
- 记录至 Excel 单元格方式
- 读取已处理完数据行数方式（适用于Excel文件中写入数据）

## **流程开发步骤**

如下采用**记录至txt文件方式**，设计流程思路如下图所示：

![image-20210114142931415](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114142931415.png)

1. 拖入“**打开/新建**”组件，并设置需要处理的 Excel 数据文件路径：

![image-20210114143108005](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143108005.png)

2. 拖入“**获取末行号**”组件并设置对应变量（lastRow），可视末行号为需要处理的总数据量，如下图所示：

![image-20210114143247596](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143247596.png)

3. 拖入“**读取文件**”组件，读取当前完成标识，并设置文件路径及对应变量（completeIdentifier）：

![image-20210114143347847](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143347847.png)

4. 拖入“**条件（if）**”组件用来判断读取文件中数据是否为空（第一次运行时数据为空），如果为空则进行对应赋值（赋值组件），如果有数据，则说明不是第一次运行，不需要做额外操作，判断条件如下： 

```
String.**IsNullOrEmpty**(completeIdentifier)||completeIdentifier==**null**
```

![image-20210114143453820](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143453820.png)

5. 拖入“**循环操作（While）**”组件，输入循环条件`Convert.**ToInt32**(completeIdentifier) <= lastRow`，并拖入“**错误捕获（Try Catch）**”、“**流程图**”组件至循环内：

   > **说明：**
   >
   > - completeIdentifier为String类型，需要用Convert.ToInt32()方法转换为Int32类型才可以作为循环条件
   > - **错误捕获**组件为流程健壮性考虑

![image-20210114143556689](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143556689.png)

6. 拖入“**读取单元格**”，设置“工作表”，单元格（前面步骤中读取的完成标识作为单元格行数）及单元格内容变量（单元格内容为需要业务中处理的数据），如下图所示：

![image-20210114143718600](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143718600.png)

7. 进入业务处理部分，本节课不讲具体业务，用“流程图”来代表内容：

![image-20210114143800976](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143800976.png)

8. 完成主业务处理后，拖入“赋值”组件进行完成标识递增，因completeIdentifier本身为String类型，所以递增前需要进行类型转换，方法为：`completeIdentifier = (Convert.ToInt32(completeIdentifier) + 1).ToString()`

![image-20210114143906162](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114143906162.png)

9. 拖入“**写入文件**”组件，并将递增后的完成标识变量写入文件中：

![image-20210114144009021](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114144009021.png)



 以上即为在循环处理数据的业务流程中用txt文件记录完成标识的整个开发过程，如果想用Excel单元格记录完成标识，那么把流程开始时的“**读取文件**”组件与“**写入文件**”组件替换为office的“**读取单元格**”与“**写入单元格**”即可，两者之间的差异为：用txt文件记录完成标识性能会比excel单元格要好一些，具体要用那种方式可视具体情况而定。

第三种记录完成标识方式为“读取已处理完数据行数”，这种方式主要应用在需要将获取的数据写入Excel的场景中，如下图所示：

![image-20210114144106769](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DebugAndNote/image-20210114144106769.png)

从D~G列为从某查询征信的网站上获取并写入的数据，C列为需要查询信息的公司名称，当在规定时间段内流程运行后还有企业信息未查询，那么我们可以用“**获取末行号**”组件获取C列末行号(lastRowC)与D列末行号(lastRowD)，循环条件为lastRowD <=lastRowC即可，请大家自行尝试开发对应流程。
