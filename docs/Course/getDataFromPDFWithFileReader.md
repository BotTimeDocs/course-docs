# 如何用文档理解解析 PDF 文件？  

我们在项目开发过程中经常会遇到从 PDF 文件中获取指定数据的场景，那么这节课我们就来讲讲如何使用企业版文档理解的功能获取 PDF 文档中指定的数据：以获取滴滴电子发票中的发票号码、发票总金额数据并存入数据库为例。接下来我们进行详细讲解。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩 RPA 编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）。

2. 打开云扩官网（https://www.encoo.com/）下载编辑器并安装。

3. 购买企业版控制台，并开通/购买文档理解功能。

4. 编辑器激活方式为：登录控制台激活。
5. 准备滴滴发票 PDF 文件, 如下图所示：

    ![pdf文件](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-1.png)

6. 准备 MySql 数据库并创建表，代码如下所示:

```mysql
      CREATE TABLE `tb1_bill` (
        `id` int(11) NOT NULL AUTO_INCREMENT,
        `billNumber` varchar(50) DEFAULT NULL,
        `billMoney` varchar(50) DEFAULT NULL,
        PRIMARY KEY (`id`)
        ) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSETT=gb2312; 
```

## **流程设计图示**

![](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-2.png)

在上述例子中，假设我们需要获取网页中这个表格的最后一列，如果我们使用【**获取结构化数据**】组件来处理，则无法实现整个 table 数据的正常获取，此时我们就可以使用如下思路来解决问题。

## **流程操作步骤**

### **控制台创建文档理解模板**

1. 登录企业版控制台（已激活）。
2. 点击左侧菜单 **文档理解** -> 点击 **新建**，此时会出现 **新增模型** 对话框， 如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-3.png)

3. 输入模板名称、备注（非必填项），选择内置模型、上传模板文件。如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-4.png)

4. 点击 **确定**，进入数据抽取界面，在该界面框选需要获取的数据并定义标签名称与字段类型：
![](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-5.png)

5. 点击 **保存模板**，**发布模板**，并返回至模板列表页面。至此，控制台文档理解模板已创建完成：
![](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-6.png)
模板创建成功，在列表中可以看到新建的模板。

### **编辑器端流程开发**

1. 创建一个“文档理解 PDF”的项目（看过前面流程开发课程的同学们应该知道怎么创建项目了，这里就不做过多讲解）。
拖入 **错误捕获（Try Catch）** 组件，在 Catch 中添加异常 Exception，并添加打印错误信息日志的操作（可用 **写入日志** 组件），再在 Try 里面拖入 **流程图** 组件：

    ![拖入组件](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-7.png)

2. 拖入 **文档理解** 组件，并设置参数点击 **确认**：

   ![文档理解](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-8.png)

    运行以上流程查看输出内容，即变量 result 的内容，以 JSON 字符串形式显示，如下所示：

    ![json字符串](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-10.png)

3. 拖入 **执行 C#代码** 组件，编写解析 JSON 字串的 C#代码并从中获取指定字段的数据, 即：发票号码和总金额，将获取的数据赋值给变量“发票号”与“金额”：

    ![csharp组件](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-9.png)

    *附上代码如下：*

    ```c
       //代码执行入口，请勿修改或删除
        public void Run()
          { 
          //在这里编写您的代码
            try
            {
              Console.WriteLine("PDF理解处理的Json数据："+result);
              //获取到
              JObject jo=(JObject)JsonConvert.DeserializeObject(result);
              发票号=jo["pages"][0]["labelResults"][0]["textValue"].ToString().Split(':')[1];
              金额=jo["pages"][0]["labelResults"][1]["textValue"].ToString().Split('￥')[1];

              Console.WriteLine(jo["pages"][0]["labelResults"][0]["textValue"].ToString().Split(':')[0]+":"+发票号);
              Console.WriteLine(jo["pages"][0]["labelResults"][1]["textValue"].ToString().Split(':')[0]+":"+金额);
            }
              catch(Exception ex)
            {
              Console.WriteLine(ex.Message);
            }
          }
        //在这里编写您的函数或者类  
    ```

4. 拖入 **连接数据库** 组件并输入连接字串、选择数据库类型并点击测试，连接通过：

    ![连接数据库](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-11.png)

    其中 Server = 服务器地址，Database = 数据库名，Uid = 用户名，Pwd = 密码，可自行填入自己对应的 Server、Database、Uid 和 Pwd 值。

    *附上连接字串：*

    ```sql
   Server=10.10.xx.xxx;Port=3306;Database=bill;Uid=webxxr;Pwd=Uxxx123;pooling=true; 
    ```

5. 拖入 **执行语句** 组件，并输入插入数据库的 SQL 语句：
![](https://docimages.blob.core.chinacloudapi.cn/images/文字课程/getDataFromPDF-12.png)

   *附上 SQL 语句如下：*

   ```sql
      insert into tbl_bill(billNumber,billMoney)values('"+发票号+"','"+金额+"');
   ```

至此，整个流程已开发完成，点击保存并运行，即可读取 PDF 文件中的发票号和金额并插入到 Mysql 数据库中。以下视频供参考：

![视频](https://docimages.blob.core.chinacloudapi.cn/images/视频课/文字课程视频/fileReader-Final.mp4)
