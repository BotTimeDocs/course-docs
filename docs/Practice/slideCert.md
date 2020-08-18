# 滑块验证
     
在实际项目中，大部分登录页面都会有各种形式的登录验证，比如滑块拖动验证，拼图验证或者是数字字母验证等。攻破这些验证码便成了使用 RPA 操作该系统的第一道关。

本文探讨如何使用 RPA 组件完成滑块验证并顺利登录。

## 课程概述

本文以 **企查查** 的登录验证为例，演示完成滑块验证并顺利登录。此页面的验证模块如下：

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/qcc)

## 流程详述
### 前置条件
在企查查网站上已经注册了账号。

### 创建项目
新建项目。

拖入 *流程图* 组件并重命名。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E6%B5%81%E7%A8%8B%E5%9B%BE)

### 打开企查查页面

使用 *打开浏览器* 组件，打开企查查网站：

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E6%89%93%E5%BC%80%E4%BC%81%E6%9F%A5%E6%9F%A5)

### 完成用户登录
打开企查查网站之后，**点击登录按钮 -> 输入用户名 -> 输入密码 -> 滑块验证 -> 点击登录**，即登录成功。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E7%99%BB%E5%BD%95%E6%AD%A5%E9%AA%A4)

#### 点击登录，进入密码登录页面
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E5%AF%86%E7%A0%81%E7%99%BB%E5%BD%95%E9%A1%B5%E9%9D%A2)

#### 输入账号密码
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E8%BE%93%E5%85%A5%E8%B4%A6%E5%8F%B7%E5%AF%86%E7%A0%81)

#### 完成滑块验证

使用组件完成滑块验证分为两步：
    1. 获取方块元素
    2. 拖动一定长度

1. 添加 *序列* 组件。
2. 使用 *获取元素* 组件获取方块元素，并输出。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E8%8E%B7%E5%8F%96%E5%85%83%E7%B4%A0)
3. 使用 *点击* 组件，按下方块。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E6%8C%89%E4%B8%8B)
4. 使用 *点击* 组件，右移后松开组件。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E6%9D%BE%E5%BC%80%E7%BB%84%E4%BB%B6)
    其中，移动的距离可以通过在页面上查看滑块轨道长度获得。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E8%BD%A8%E9%81%93%E9%95%BF%E5%BA%A6)
5. 点击登录。

#### 加强健壮性
有时因网络原因或其他原因没有登录成功，我们需要进行判断，如果页面显示验证通过，则点击登录，如果未出现该标识，则刷新页面，重新登录。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E5%88%B7%E6%96%B0)
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E9%AA%8C%E8%AF%81%E9%80%9A%E8%BF%87)

完整的流程编辑请参考以下视频：

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/slideCert/%E6%BB%91%E5%9D%97%E9%AA%8C%E8%AF%81%E7%A0%81.mp4" controls="controls" width="700px" />