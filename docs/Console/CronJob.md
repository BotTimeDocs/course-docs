# 如何使用机器人定时任务

在日常工作中总有些工作需要我们在某一特定的时刻去做某些任务，且具有周期性。云扩 RPA 机器人提供了**定时任务功**能完美解决了此类问题。

## 准备工作

1. 已在云扩 RPA 编写了一个 RPA 流程并发布到机器人。
2. 已安装最新版云扩机器人并激活。

## 创建定时任务

1. 打开云扩 RPA 机器人。
2. 进入定时任务页，点击**新建定时任务**。

    ![定时任务](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Robot/Cron-1.png)

3. 输入任务名称，如，“每日订单处理”。
4. 选择已发布到机器人的流程"每日订单汇总"，选择版本号。
5. （可选）点击**执行配置**，弹出如下图所示弹框，根据需求配置流程参数信息。

    ![定时任务](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Robot/Cron-2.png)

6. 选择定时模式**按天**
   下方示例配置为每天执凌晨一点行此流程，生效范围为 2020/12/17号0点开始至2020/12/31号0点结束。

    ![定时任务](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Robot/Cron-3.png)

7. 点击**确认**保存此定时任务。
  
    ![定时任务](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Robot/Cron-4.png)

8. 定时任务创建结束，即，当在生效时间范围内每天0点将会定时执行流程"每日订单处理"。