​第十一课 - Excel文件合并 {#activity-name .rich_media_title}
-------------------------

By 安妮 [文逸课堂](javascript:void(0);)

**文逸课堂** ![](https://mp.weixin.qq.com/s/vIZ5bWEu6z7u-7JIFbxqDg)

微信号 gh\_44753f1ea223

功能介绍 RPA流程开发课堂

** **

*8月26日*

收录于话题

    大家好，这节课我们讲下Excel文件的合并，在讲之前先回顾一下第二课Excel文件的拆分，Excel文件拆分一是为了提高流程运行速度，二是为了匹配其他涉及到的系统的需求。那么在分批次处理完各种数据后我们需要进行Excel文件的合并，以还原数据文件。那么，接下来就讲讲如何用云扩RPA编辑器开发合并Excel文件的流程。\

**准备工作**：

    1）准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求（https://academy.encoo.com/zh-cn/wiki/Studio/HarewareAndSoftwareRequirements.md?uuid=1bb922bd-c25d-4921-9241-f13ee45d295f）

    2）打开云扩官网（https://www.encoo.com/）下载编辑器并安装。

    3)  文件夹中有多个数据结构一致的Excel数据文件。如下图所示：

       

![](./_第十一课%20-%20Excel文件合并_files/640)

**本次课程介绍：**

   
1）流程名称：Excel文件合并机器人，该机器人可以将多个Excel文件正确合并为一个文件。

    2）流程开发设计如下：

![](./_第十一课%20-%20Excel文件合并_files/640(1))

   3）流程开发步骤：

打开云扩编辑器，选择“项目”，并点击“新建项目”进行创建项目。

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

a）**“获取指定文件夹中的文件列表”部分**\

拖入“获取文件/文件夹列表”，添加对应的变量fileList（变量类型：String[]）与参数directoryPath（参数类型：String），将fileList作为输出变量，directoryPath作为输入参数（当然，也可以将directoryPath作为变量处理），如下图所示：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**b）“从所有文件中找到指定文件”部分**\

拖入“循环操作（For Each）”组件，并将fileList作为循环体变量输入：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

拖入“流程图”组件，将该组件放置到“循环操作（For Each）”组件内：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

拖入“流程决策”组件，添加fileIdentifier参数（也可以设置为变量），该参数用来指定文件夹内哪一个文件作为基本文件，后续会把其他文件的数据复制到该文件内，并输入判断条件：item.Contains(fileIdentifier)

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

判断为真，即如果当前文件名包含指定的文件标识，那么把该文件名赋给可以传递到for
each循环之外的变量中。拖入“赋值”组件，如下图所示：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

如果找到对应的文件，即终止循环。拖入“终止循环”组件：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**c）“循环合并Excel文件”部分**

拖入“循环操作（For Each）”组件，并把fileList作为循环体变量：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

“循环操作（For Each）”组件内部拖入“流程图”组件以此作为下面流程的容器：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

拖入“流程决策”组件，并添加判断条件item.Contains(fileIdentifier)：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

如果判断条件为假，即当前文件不包含文件标识（也就是说当前文件不是指定的基础文件），那么**打开当前文件并复制对应数据**。

-   拖入“新建/打开”组件：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

-   拖入“获取末行号”组件与“获取末列号”组件获取当前文件最大行号与列号，作为后续读取区域的区域数值，如下图所示：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

-   拖入“执行C\#代码”组件，将获取的末列号数值转换为字母列号：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

*=============================================*

*附上代码段： *

*StringBuilder letter = new StringBuilder();\
    do {\
        --lastColumn;\
        int mod = lastColumn % 26; // 取余\
        letter.Append((char) (mod + 'A')); // 组装字符串\
        lastColumn = (lastColumn - mod) / 26; // 计算剩下值\
    } while (lastColumn \> 0);\
char[] arr = letter.ToString().ToCharArray();\
Array.Reverse(arr);\
toLetter = new String(arr);\
Console.WriteLine(toLetter);*

*（*我们将会开发“*转为字母列号”功能对应的组件，之后可直接用组件实现，无需代码）\
*

**=============================================**

-   拖入“读取区域”组件，并添加数据区域，在上步操作中我们已获取末行号与末列号，此处就将获取的数据作为读取区域的输入，如下图所示：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**打开指定基础文件并写入上步操作中读取的数据**\

-   拖入“打开/新建”组件，输入文件路径（basicFile）：

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

-   拖入“获取末行号”以此来获取基础文件最大行号，并在下一行中用“写入数据”组件进行写入数据：\

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**写入数据后删除原有文件**\

-   拖入“删除文件/文件夹”组件并添加当前文件路径item以此删除该文件：**\
    **

![](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

至此，整个流程已开发完毕，请保存并运行，祝顺利！以下为流程运行视频：

\

    好啦，伙伴们，今天的课程就到此结束。除了经常说的那句有不同开发思路请留言以外，还想知道大家对课程内容是否有更多建议，这里都非常欢迎听取不同的建议与意见\~

预览时标签不可点

收录于话题 \#

个**

上一篇 下一篇

阅读

分享

收藏

赞

在看

****已同步到看一看[写下你的想法](javascript:;)

前往“发现”-“看一看”浏览“朋友在看”

![](./_第十一课%20-%20Excel文件合并_files/pic_like_comment492329.png)

前往看一看

**看一看入口已关闭**

在“设置”-“通用”-“发现页管理”打开“看一看”入口

[我知道了](javascript:;)

**

已发送

取消 **

#### 发送到看一看 {.like_comment_primary_title}

发送

​第十一课 - Excel文件合并

最多200字，当前共字

**

发送中

喜欢此内容的人还喜欢

[](javascript:void(0);)

第二十五课 - 填写海关减免税货物结转申请单（Word写入操作）

第二十五课 - 填写海关减免税货物结转申请单（Word写入操作）

...

文逸课堂

不喜欢

不看的原因

确定

-   内容质量低
-   不看此公众号

[](javascript:void(0);)

重大突破！

重大突破！

...

中国经济网

不喜欢

不看的原因

确定

-   内容质量低
-   不看此公众号

[](javascript:void(0);)

梅拉尼娅也劝特朗普，认输吧

梅拉尼娅也劝特朗普，认输吧

...

长安街知事

不喜欢

不看的原因

确定

-   内容质量低
-   不看此公众号

[留言](javascript:;)

![](./_第十一课%20-%20Excel文件合并_files/qrcode)

微信扫一扫\
关注该公众号

微信扫一扫\
使用小程序

****

[取消](javascript:void(0);) [允许](javascript:void(0);)

****

[取消](javascript:void(0);) [允许](javascript:void(0);)

**微信版本过低**

当前微信版本不支持该功能，请升级至最新版本。

[我知道了](javascript:void(0);) [前往更新](javascript:void(0);)

确定删除回复吗？

[取消](javascript:;) [删除](javascript:;)

[知道了](javascript:;)

**长按识别前往小程序**

![](https://mp.weixin.qq.com/s/vIZ5bWEu6z7u-7JIFbxqDg)

**


