## 如何部署一个流程并使用机器人执行

大家好，这节课我们主要来介绍一下如何在云扩控制台上对流程进行部署，并使用已连接的机器人执行一次流程任务。

### 创建流程部署

首先我们需要在“流程部署”页面中新建一个流程部署，部署过程主要对流程失败的重试次数、视频录制、任务优先级、执行目标等进行配置，同时也可对流程包中的参数进行再次赋值。在流程部署页面中点击“新建”按钮后即可开始新建流程部署。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob1.png)

**1. 对流程部署进行基本配置**

- 基本信息：填写流程部署名称，通过下拉选择需要部署的流程包及对应的版本号。

- 失败最大尝试次数：流程执行失败后将按照该次数自动进行重试，默认为3次。

- 任务优先级：优先级越高该任务将被越先执行，默认优先级为2000。
- 是否开启视频录制：开启后机器人将会进行视频录制，并且根据回传条件控制台视频将视频回传至控制台。


![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob2.png)

- 流程包参数赋值：可选择对流程包中的参数进行重新赋值，主要有2种赋值方式：
  - 手动赋值：直接在对应参数的"参数默认值"输入框中进行修；
  - 导入资产：点击“导入资产”可选择在资产管理页面中预先存储的资产进行赋值。（本次暂不讲述，后续会重点展开）

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob3.png)

**2. 配置流程执行目标**
点击“下一步”开始配置流程执行目标，可选择指定队列执行/指定机器人执行：

- 指定机器人执行：流程任务生成后将由指定的机器人执行，目前绑定几个机器人将会执行几次流程任务。

- 指定队列执行：流程任务将会被生成到队列中，由队列中空闲机器去动态分配任务。

此次我们将选择指定机器人执行，勾选“指定机器人执行”后选择一个空闲的机器人，点击“保存”按钮即可完成一个流程部署的创建。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob4.png)



### 手动执行流程

完成流程部署之后我们便可以开始执行流程，目前执行流程有两种方式：
- 手动执行：系统将会立即生成一条流程任务进行执行。
- 任务计划：系统将通过定时的方式生成流程任务进行执行。

> **说明：**
>
> 无论是通过何种方式执行流程，均为当前时刻或定时时刻创建任务。如果无可用机器人或者前方有更多任务在排队则无法保证立刻执行任务。

1. 此次让我们将通过手动执行的方式执行一条流程，点击对应流程部署的“操作”-“执行”按钮。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob5.png)

2. 点击“执行”按钮后系统将会弹窗让我们对之前流程部署的配置进行确认，此处可以对流程部署配置进行修改，修改后仅会影响本次执行结果，不会对原流程部署造成影响，二次确认后点击“执行”按钮即可生成对应的任务。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob6.png)


### 查看任务执行情况

若我们想查看当前任务的执行情况，则我们可以在"流程部署"的"任务列表"页面中查对应任务的任务（Job）及任务下执行实例(Runinstance)情况。
- 任务（Job）：代表需要完成的流程任务，一个Job可能包括多个具体的执行实例。

- 执行实例（Runinstance）: 任务的具体执行信息，任务每一次执行均会生成一条。如果任务最大失败重试次数为3，则理论上最多会生成4条执行实例。

在此处可以查看任务来源、创建时间、开始时间、结束时间、状态、任务优先级等信息。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob7.png)


现在我们可以看到刚刚创建的任务已经处于成功执行的状态，若我们需要查看机器人执行该条任务的具体信息，可以点击某一执行实例（Runinstance）“日志”按钮来查看详细日志。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob8.png)

在页面中我们可查看详细的机器人执行日志、截图、视频记录等，便于对执行情况进行追溯。

![process](https://docimages.blob.core.chinacloudapi.cn/images/Console/jobcourse/runjob9.png)

本次的课程到此结束。以上便是如何部署一个流程并调度一个机器人执行的基本介绍，后续的课程中我们将会继续介绍更复杂的调度方式。