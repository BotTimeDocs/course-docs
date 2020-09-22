# 操作日期选择框（datepicker）

有些页面上的日期选择框可以直接用*输入文本*组件进行操作。

本文主要针对那些不支持直接输入，必须通过点击才能操作的日期选择框。本文以 AntDesign 基础日期选择框为例，选择指定日期。

## 操作思路
指定日期后，在页面中依次选择年，月和日。

## 前提条件
已打开 [AntDesign 基础日期选择框](https://ant.design/components/date-picker-cn/)。

## 根据系统时间和增量，确定指定时间
把我们需要指定的时间分别保存在 *年*，*月*，*日* 三个变量中。

1. 拖入 *流程图* 组件，重命名为*获取年月日*：
2. 在流程图中，设置字符串型变量 *年* 与参数 *年份增量*。
3. 拖入*赋值*组件，赋值左侧为变量 *年*，右侧为 `System.DateTime.Now.AddYears(年份增量).ToString(*yyyy*)`
![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E5%B9%B4)
4. 以同样方法指定月份及日期。添加以下变量：
    - *月*；
    - *日*；
    - *月份增量*；
    - *日期增量*。

赋值代码为：
- *月*：`System.DateTime.Now.AddMonths(月份增量).ToString(*MM*).TrimStart('0')`
- *日*：`System.DateTime.Now.AddDays(日期增量).ToString(*dd*)`

## 在日期选择框中选择时间
### 点击日期选择框
拖入*点击*组件，指定日期输入框元素。

![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E7%82%B9%E5%87%BB%E6%97%A5%E6%9C%9F%E9%80%89%E6%8B%A9%E6%A1%86)

### 选择年份

1. 拖入*点击*组件，点击年份,打开年份选项框。

    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E7%82%B9%E5%87%BB%E5%B9%B4%E4%BB%BD)

2. 拖入*获取结构化数据*组件，获取该面板所有年份。查看指定年份是否包含在内。如果不包含，则点击上一页或者下一页按钮翻页）：

    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E7%BB%93%E6%9E%84%E5%8C%96%E8%8E%B7%E5%8F%96%E5%B9%B4%E4%BB%BD)

3. 拖入*C\#*组件，从上步获取的数据表中循环查找指定年份。如果包含，则赋值isTrue为true，为下一步做准备：

    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E6%9F%A5%E6%89%BE%E6%8C%87%E5%AE%9A%E5%B9%B4%E4%BB%BD)

附上查找年份代码：

```
isTrue=false;
for(int i=0;i\<dt.Rows.Count;i++){
    for(int j=0;j\<dt.Columns.Count;j++){
        if(dt.Rows[i][j].Equals(年)){
        i=i+1;
        j=j+1;
        isTrue=true;
        break;
    }else{
        continue;
        }
    }
}
```

4. 使用*流程决策*组件，根据 isTrue 判断下一步操作：
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E5%88%A4%E6%96%AD%E7%BF%BB%E9%A1%B5)

如果isTrue为真（上步中查询到预期年份），则直接点击选中年份;
如果未查到年份，则点击翻页。
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E7%82%B9%E5%87%BB%E5%B9%B4%E4%BB%BD%E7%BF%BB%E9%A1%B5)

### 选择月份
1. 使用*赋值*组件，拼接月份：
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E6%8B%BC%E6%8E%A5%E6%9C%88%E4%BB%BD)

2. 打开月份选择框：
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E6%89%93%E5%BC%80%E6%9C%88%E4%BB%BD%E9%80%89%E6%8B%A9%E6%A1%86)

3. 点击指定月份:
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E7%82%B9%E5%87%BB%E6%8C%87%E5%AE%9A%E6%9C%88%E4%BB%BD)

### 选择日期

点击指定日期：
    ![](https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/%E9%80%89%E6%8B%A9%E6%97%A5%E6%9C%9F)

完整的流程编辑请参考以下视频：

<video src="https://docimages.blob.core.chinacloudapi.cn/images/Practice/datepicker/datepicker-%E5%8A%A0%E5%AD%97%E5%B9%95_1.mp4" controls="controls" width="700px" />