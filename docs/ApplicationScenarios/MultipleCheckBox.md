# 勾选多个指定复选框的小技巧  

在网页自动化操作过程中，有时会遇到勾选多个复选框的场景，当我们需要勾选的复选框不固定时，如果流程中直接通过点击组件的【指定元素】勾选复选框不利于复用流程，在这种情况下，我们需要自定义勾选复选框参数，那么，具体怎么操作呢？

接下来，我们介绍流程开发的详细步骤及思路。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩 RPA 编辑器运行的硬件&软件要求（<https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?>）。

2. 打开云扩官网（<https://www.encoo.com/>）下载编辑器并安装。


## **流程设计图示：**

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-1.png)

## **结果预期：**
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-2.png)

## **流程操作步骤：**
1. 创建项目，命名为“勾选复选框”：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-3.png)

2. 拖入**打开浏览器**组件，并配置需要选择复选框的网页：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-4.png)

3. 拖入**赋值**组件，来接收自定义参数的列表内容：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-5.png)

4. 拖入**循环操作（For Each）** 组件，来遍历每一个需要勾选的参数值：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-6.png)

5. 观察网页中每个复选框的xpath路径：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-7.png)

6. 拖入**赋值**组件，来接收每次拼接的xpath内容：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-8.png)

7. 拖入**勾选**组件，并设定元素xpath，xpath为上步操作的拼接值，其中包含变量：
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/multipleCheckbox-9.png)

至此勾选多个用户指定复选框的流程已开发完成，保存并运行查看结果：
<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/MultiCheckbox/checkbox.mp4" controls="controls" width="700px" />