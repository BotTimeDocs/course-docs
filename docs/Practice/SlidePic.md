# 滑块拼图验证

在实际项目中，大部分登录页面都会有各种形式的登录验证，比如滑块拖动验证，拼图验证或者是数字字母验证等。攻破这些验证码便成了使用 RPA 操作该系统的第一道关。

本文探讨如何使用 RPA 组件完成滑块拼图验证并顺利登录。

## 课程概述

本文以 **Boss 直聘** 的登录验证为例，演示完成滑块拼图验证并顺利登录。此页面的验证模块如下：

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E9%AA%8C%E8%AF%81%E9%A1%B5%E9%9D%A2)

操作流程如下：

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)

操作演示参考视频：

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E6%89%8B%E5%8A%A8%E6%93%8D%E4%BD%9C.mp4" controls="controls" width="700px" />

进行滑块拼图验证时，大部分操作和[滑块验证](https://academy.encoo.com/learn/unit-detail/35)一致，只是滑块移动距离的测量需要使用额外的工具。

## 流程详述
### 前置条件
滑块移动距离的测量需要使用云扩组件市场提供的*尖叫数据 OCR*组件。

该组件调用了[尖叫数据](http://www.jianjiaoshuju.com/)网站的服务，使用该组件前，需要注册并获取账号对应的 AppCode、AppKey、AppSecret 等信息。你必须在网站上购买 *坐标图片验证码识别* 服务。网站提供了0元10次试用版，开发时可以使用该套餐。

### 创建项目
新建项目。

拖入 *流程图* 组件并重命名。

### 下载尖叫数据 OCR 组件
在组件市场中，下载*尖叫数据 OCR*组件。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E5%B0%96%E5%8F%AB%E6%95%B0%E6%8D%AEOCR.webp)

### 点击获取滑动页面

使用*模拟鼠标*的方式，点击*圆点*元素。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E5%9C%86%E7%82%B9.png)

### 获取验证图片，测量偏移量

1. 获取图片

使用 *截屏* 组件拾取需要测定的图片元素。
    
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E6%88%AA%E5%B1%8F.webp)

2. 测量偏移量

使用*尖叫数据 OCR - 滑块验证码识别*组件，获取偏移横坐标数据。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E8%8E%B7%E5%8F%96%E6%A8%AA%E7%A7%BB%E6%95%B0%E6%8D%AE.webp)

获取的数据格式如下：

```
 {
     "msg":"查询成功!",
     "v_code":"185,78",
     "errCode":0,
     "v_type":"sld"}
```

对于返回的数据，我们还需要进一步加工。使用*执行 C# 代码*组件，执行以下代码，获取 *v_code* 字段中的第一个数据。这个数据就是我们想要的偏移量数据。

```
try{
       JObject jo = (JObject)JsonConvert.DeserializeObject(picad);
       string   plance= jo["v_code"].ToString();
       string[] strArray = plance.Split(',');
       xmove=Convert.ToInt32(strArray[0]);
}
catch (Exception ex)
{
       Console.WriteLine(ex.Message);
}
```

实际测量发现，多了8个像素。使用赋值组件减去8个像素。

### 滑动滑块

滑动滑块的具体操作在[滑块验证](https://academy.encoo.com/learn/unit-detail/35)中有详细描述。请自行参考步骤指引。

以下是流程执行过程的视频：

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/SlidePic/%E6%BB%91%E5%8A%A8%E9%AA%8C%E8%AF%81.mp4" controls="controls" width="700px" />