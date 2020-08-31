# 使用系统功能设定定时任务

云扩控制台支持连接大量机器人并设定流程的定时执行。

但是，当企业因为使用的机器人较少，未部署云扩控制台时，其实也可以借助 Windows 系统自带功能实现简单的定时任务功能。

本文介绍通过 Windows 系统 *任务计划程序* 定时触发机器人执行流程。

## 操作思路
使用 Windows 自带的 *任务计划程序* 定时调用 .bat 文件。对应的 .bat 文件启动已安装的云扩机器人程序，调用指定的 RPA 流程。

### 前提条件
确保机器人未运行。

### 指定 RPA 流程
新建 .json 文件，按规则写入流程文件相关信息。

1. 此处将 .json 文件命名为 *robot.exe.json*。
2. 根据流程文件所在位置，按不同规格写入 .json 文件：
    - 假如你希望调用在云扩编辑器中创建的 RPA 流程项目，请按照以下格式（其中的文件夹路径是在编辑器中创建项目时所在的项目目录）：

        > {"ProjectPath":"C:\Users\{UserAccount}\Documents\Encoo\\{ProjectFolder}"}
    
    - 假如你希望调用已导入本地机器人的 RPA 流程项目，请按照以下格式：
    
        ```
        {
            "LocalPackageName":"{ProjectName}",//在机器人中显示的本地流程包名
            "LocalPackageVersion":"{ProjectVersion}",//在机器人中显示的流程包版本号
            "Arguments": null
        }
        ```

### 编写调用指定 RPA 流程的 .bat 文件
.bat 文件内容如下：

```
@echo off
tasklist /nh|find /i "Encoo.Executor.exe"
  if ERRORLEVEL 1 (
    cd /d "C:\Program Files (x86)\Encoo\Encoo Robot\Monitor"
    start /wait robot.exe -d "{jsonPath}"
  ) 
  else (exit)
```

此时，你即可使用此 .bat 文件调用机器人执行指定流程了。

### 设定定时任务
设定定时任务，定时执行 .bat 文件即可。

1. 打开 Windows 任务计划程序。
2. 创建任务。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/timing/%E5%88%9B%E5%BB%BA%E4%BB%BB%E5%8A%A1)
3. 设定名称，使用最高权限。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/timing/%E8%AE%BE%E5%AE%9A%E5%90%8D%E7%A7%B0)
4. 设定触发时间。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/timing/%E8%AE%BE%E5%AE%9A%E8%A7%A6%E5%8F%91%E6%97%B6%E9%97%B4)
5. 指定执行的 .bat 文件。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/timing/%E6%8C%87%E5%AE%9Abat%E6%96%87%E4%BB%B6)

创建完成后，在*任务计划程序库*中可查看到刚设定的任务，选中任务右边可点击直接运行，也可等到设定的时间触发运行。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/timing/%E4%BB%BB%E5%8A%A1%E5%88%97%E8%A1%A8)

Note：任务触发前，请确保机器人处于可执行状态。