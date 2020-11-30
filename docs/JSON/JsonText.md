# 从JSON文本中获取指定区域的数据

大家在项目中会遇到过不少需要处理 JSON 文本的工作，比如，在桌面应用中使用**获取区域结构**组件获取的数据、使用云扩 AI Hub 组件中的**发票识别**组件获取的发票数据，输出都是 JSON 文本，那么如何在**不使用代码**的情况下获取 JSON 文本中指定范围内的数据呢？接下来，我们一起来了解下这类数据的获取方法。

**准备工作：**

1. 准备开发流程的电脑，点击链接（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）查看云扩 RPA 编辑器运行的硬件&软件要求。

2. 打开云扩官网（https://www.encoo.com/）下载编辑器并安装（本节课使用编辑器版本为：1.1.2010.9）。

3. 准备好 JSON 文本文件 或 从业务流程中获取 JSON 文本。

   > **说明：**
   >
   > - 下图为“发票识别”组件获取的JSON数据，左侧为原文本，右侧为 JSON 在线解析后结构。
   > - 需要获取 details 区域中从 code 到 seller_bank_account 的数据。

   ![JSON文本](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/jsontext20201127.png)

**流程示意图：**

   ![流程示意图](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/flowchar20201127.png)



**流程操作步骤：**

1. 读取JSON文本

   拖入**读取文件**组件，并设置文件路径及定义输出文件内容变量：

   ![step1](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step1.png)

2. 截取指定区域文本

   如果使用**截取文本**组件来获取需要的数据区域，那么必须要明确数据的“开始位置”与“结束位置”，先仔细观察 JSON 文本中 details 区域：

   ![step2](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step2.png)

   > 说明：
   >
   > details关键字是固定的，也就是说“开始位置”是固定的，但是seller_bank_account之后的值为变量，结束位置不固定，但必须要通过某种方法获取当前这个文本中seller_bank_account这个变量值与其长度，（长度用来在截取文本时调整文本索引）。这里指的某种方法为：正则表达式+“提取文本”组件，文本“seller_bank_account：xxxx，”中固定的文本为“seller_bank_account”与逗号 “，”，那么获取整个动态文本的正则表达式可写为：`seller_bank_account.*?`。

     a. 拖入**流程图**组件，用于模块化截取指定区域流程片段，拖入**提取文本**组件并输入源文本变量、正则表达式，定义提取结果变量：
   ![step2-a](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step2-a.png)

   b. 拖入“获取文本长度”组件，获取上步操作中获取的动态数据长度：
   ![step2-b](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step2-b.png)

   c. 到此，已获取需要开始位置与结束位置文本，接下来拖入“截取文本”组件截取我们所需要的文本，开始位置索引为：text.**IndexOf**("""details""") + 10，结束位置索引为：text.**IndexOf**(resultText) + (length - 2)

   > **说明**：
   >
   > - 变量 text 为第一步中读取的文本变量;
   >
   > - 索引偏移量+10与-2可根据具体数据调整;
   > - 开始位置与结束位置索引也可通过组件“获取文本索引”获取 ：

   ![step2-c](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step2-c.png)




3. JSON转DataTable

   这里的 JSON 并不是源 JSON 文本，而是通过以上操作获取的含有我们所需数据的区域数据，但需要进行一些简单的拼接。可通过运行以上流程查看获取的最终数据结构（用**写入文本**组件来获取数据，并在 JSON 在线转换网页中测试：https://www.json.cn/#）：
   ![step3-1](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step3-1.png)

   提示数据最后缺大括号 “}”，根据提示添加大括号，并把整个 JSON 数据用中括号包起来，如下图所示，JSON 文本正常显示：

   ![step3-2](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step3-2.png)
   
   接下来我们正式转换JSON文本并获取所需要的数据：
   
   a. 从组件市场中下载**Json转换工具包**：

   ![step3-a](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step3-a.png)

    b. 拖入**Json转DataTable**组件，输入拼接 JSON 文本变量：`"[" + resultText + "}]"`，定义输出数据表变量dt：

    > **说明：**
    > 其中变量“resuleText”为以上操作“截取文本”步骤的输出文本。

   ![step3-b](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step3-b.png)

4. 保存DataTable数据

   a. 拖入Office**打开/新建**组件与**写入区域**组件，用于将上一步操作中获取的数据存入Excel。
   ![step4](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/step4.png)
   
   > **注意：**
   >
   > 写入区域勾选添加列头。

至此，从 JSON 中获取指定区域的流程已开发完毕，保存并运行流程。