# 获取分隔列数据
此节课程将讲述如何使用**获取结构化数据**组件获取到分隔列数据

## 准备工作
1. 打开云扩**编辑器**，新建一个空白项目，搜索**序列**组件并拖拽至设计面板，设为开始结点,双击打开序列
2. 打开Chrome浏览器，输入 **"http://www.chinaports.com/chuanqibiao/2/null/null/null/query"** 并点击跳转

## 绑定浏览器
此步骤将演示如何获取已打开的浏览器内数据

注意：在运行时，请保持绑定的浏览器处于打开状态；否则**绑定浏览器**会失败，流程报错并退出

3. 搜索**绑定浏览器**组件并拖拽放置于**序列**内
4. 点击**指定浏览器**，将鼠标移动到准备工作中打开的网页上，看到下图高亮效果时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/attach.png)

## 获取分隔列数据
5. 搜索**获取结构化数据**组件并拖拽放置于**绑定浏览器**内
6. 点击**指定数据源**，将鼠标放到表内第一个单元格上，高亮显示时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/1.png)

7. 弹出下图窗口后，点击**否**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/getWhole.png)

8. 点击**下一步**，执行指定第二个元素的操作

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/2.png)

9. 将鼠标放到表内第一列的任意单元格上，高亮显示时点击


![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/3.png)

## 两次指定元素匹配到规则后，配置列名
10. 当两次指定的元素匹配到规律时，会显示对话框提示配置列名，此处填入**承运人**后点击**下一步**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/4.png)


## 继续提取数据
11. 获取到的第一列数据被展示了出来，点击**继续提取数据**执行获取第二列数据的操作

12. 将鼠标放到表内第三列起运港的第二个单元格上，高亮显示时点击。出现下图点击**下一步**来继续指定第三列的任意单元格

13. 当两次指定的元素匹配到规律时，会显示对话框提示配置列名，此处填入**启运港**后点击**下一步**

14. 获取到的第一列和第三列的数据被展示了出来，点击**完成**
15. 弹出的对话框询问是否翻页获取更多数据，此处选择**否**

## 将获取到的数据存入数据表

16. 点击设计面板下的 **变量**标签，并新建一个**DataTable**类型的变量，命名为**dt**
17. 点击**获取结构化数据**组件，输出**数据表**属性写入**dt**

## 预览数据表
18. 搜索**预览数据表**组件并拖拽放置于**序列**内
19. **数据表**属性写入**dt**

## 运行查看结果
20. 点击**运行**按钮，可看到获取的第一页数据在运行时被展示了出来

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/ExtractStructruedData/result.png)
