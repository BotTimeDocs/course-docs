# Chrome浏览器下载的文件保存至指定路径下

大家好，当我们遇到在Chrome浏览器上下载文件后保存到指定文件路径的场景时，通常采取的方案相对较多的是手动设置Chrome下载文件路径，但也有些特定的场景中不合适让用户去修改浏览器设置。那么，如何通过RPA从默认的下载路径获取到文件并保存到指定的路径下呢？尤其是在每位用户的默认下载文件路径不相同的情况下（即默认路径为动态的）。

接下来我们以下载云扩编辑器安装包为例，一起看看具体的开发过程。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩RPA编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?）。

2. 打开云扩官网（https://www.encoo.com/） 下载编辑器并安装。
3. 注册云扩社区版控制台账号。

## **流程设计图示**

![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-1.png)

## **流程操作步骤**

### **登录云扩控制台网站**

1. （创建项目步骤略过）拖入**打开浏览器**组件，并指定网址，选择浏览器类型为**Chrome**:
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-2.png)

2. 拖入**序列**组件，命名为“登录”；拖入**输入文本**组件，指定用户名输入框元素、创建变量 <font color=#0000FF>  username </font> 并按快捷键**Ctrl+B**同步至变量区，变量默认值为实际用户名：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-3.png)

3. 再次拖入**输入文本**组件，指定密码输入框元素、创建变量<font color=#0000FF>  password </font>并按快捷键**Ctrl+B**同步至变量区，变量默认值为实际密码：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-4.png)

4. 拖入**点击**组件，指定登录元素：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-5.png)

### **下载Studio并保存至指定文件路径下**

1. 拖入**流程图**组件用来模块化流程下载并将文件移至目标文件夹部分；拖入**点击**组件，指定“下载”元素：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-6.png)

2. 点击下载后我们模拟手动操作点击网页下端下载进度栏中的“全部显示”，但因为网络延迟等因素导致有时目标元素并不能马上显示出来，所以我们在设计流程时可用**等待元素出现**组件来检查元素显示，并拖入**流程决策**组件判断是否出现，如果出现则点击，如果在超时时间端内没有出现该元素，那么继续等待，流程设计如下图：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-7.png)

3. 点击上步操作中的“全部显示”后需要点击“保留”，但因为文件大小不确定，还未下载完成的页面上没有“保留”这个按钮，那么我们用上步同样的操作来处理：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-8.png)

4. 点击“保留”之后下载的文件已保存在默认路径下，我们需要获取当前下载的文件名及默认下载路径。首先拖入**获取文本**组件获取文件名，需要注意的是在指定元素后从**选择器**中**取消最下层的Hyperlink**，否则获取到的数据为文件名下端的链接字串而非文件名，如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-9.png)
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-10.png)

5. 拖入**点击**组件，指定“在文件夹中显示”元素，注意：用**UIA3**技术录制的元素因为定位时会相对比较慢，所以需要添加**匹配超时时间**，如下图所示：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-11.png)

6. 拖入**获取文本**组件，指定“文件地址栏”元素，注意：因为默认下载文件路径每台电脑都不相同，所以指定元素后需要在选择器中对当前路径Name用通配符替换：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-12.png)

7. 拖入**复制/移动文件**组件，输入源文件路径（将以上操作步骤中获取的文件名称与默认下载路径名称进行拼接：<font color=#0000FF>  filePath(' ')[1] + "\" + fileName </font>）与目标路径(<font color=#0000FF>  destFolderPath + "\" + fileName </font>)并选择“移动”方式：
![](https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/getDownloadFile-13.png)
至此，整个流程开发完成。以下视频供参考：
<video src="https://docimages.blob.core.chinacloudapi.cn/images/Course/getDownloadFilesFromChrome/SavesDownloadedFilesToDestinationPath-edited.mp4" controls="controls" width="700x" />
