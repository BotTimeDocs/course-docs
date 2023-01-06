<br><br>

## 一、课程简介

<br>

**【课程目标】**

<br>

通过对变量、参数及RPA数据类型的学习，完成用RPA组件模拟搭建一个模拟实现计算器功能流程。冲吧~

<br><br>

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727351319863.jpg"/>



<br>

**课时内容：**

> * RPA第三课 (2023年)
> * 课程时长：  20分钟 ,7节课时
> * 编辑器下载：[https://www.encoo.com/download](https://www.encoo.com/download)




<br><br>

**目录：**

> RPA小任务：模拟计算器功能 (课程时长:5分钟)

> 知识点1：变量的定义及其创建办法 (课程时长:3分钟) 

> 知识点2：变量的范围及包含关系 (课程时长:2分钟)

> 知识点3：常用的RPA数据类型 (课程时长:3分钟) 

> 知识点4：参数——流程间传递数据 (课程时长:3分钟)

> 知识点5：参数 VS 变量 (课程时长:2分钟)

> 知识点6：表达式编译器 (课程时长:2分钟)

<br><br><br>



## 二、学习内容：

* 课程简介：
* 学习目标：掌握 ★★★
* 难易程度：一般 ★★
* 讲义下载：文末进群-获取“讲义PPT”


<br><br>


### 2.1 视频教程：

<video controls height='100%' width='100%' src="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023%E8%AF%BE%E7%A8%8B/RPA%E5%B0%8F%E4%BB%BB%E5%8A%A1%EF%BC%9A%E6%A8%A1%E6%8B%9F%E8%AE%A1%E7%AE%97%E5%99%A8%E5%8A%9F%E8%83%BD.mp4"> </video>




<br><br>

### 2.2 文档教程：


<br><br>

**具体操作步骤**

<br><br>


**第一步：** 

* 拖入确认框组件，并填写对应属性值。
* 在输出的确认结果处创建类型为Boolean的变量承接数据。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727351705120.jpg"/>


<br><br>

**第二步：** 
* 拖入输入框组件，并填写相应属性。
* 在输出处新建类型为String的变量承接内容。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727351838422.jpg"/>


<br><br>

**第三步：** 
* 复制输入框并修改属性。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727351950300.jpg"/>

<br><br>

* 在输出处新建第二个类型为String的变量承接内容。


<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352086802.jpg"/>




<br><br>

**第四步：**

* 拖入赋值组件，并新建一个类型为Int32的变量。
* 将先前String类型的变量（num1）通过代码转换为Int32类型。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352267347.jpg"/>



<br><br>

**第五步：**

* 复制一个赋值组件
* 将第二个String类型的变量（num2）通过代码转换为Int32类型。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352376926.jpg"/>


<br><br>

**第六步：**

* 拖入条件（If）组件，当变量isAdd==true，即做加法。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352484622.jpg"/>


<br><br>

**第七步：**

* 在条件成立面板，拖入赋值组件
* 新建一个类型为Int32的变量result输出结果。值为：num1+num2。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352636339.jpg"/>


<br><br>

**第八步：**

* 在条件不成立时做减法，同样拖入赋值组件
* 此处变量result的值为num1-num2。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352769053.jpg"/>



<br><br>

**第九步：**

* 拖入写入日志组件
* 将String类型变量通过代码转换为Int32类型，并打印出最终结果。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727352913655.jpg"/>



<br><br>

**第十步：** 
* 点击运行，流程即会按设定弹出确认框和输入框，并进行运算。

<img width = '400'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2023/01/03/16727353015507.jpg"/>


<br><br><br>

### 案例小结：

1. 创建两种类型的变量：String类型 & Boolean类型

2. 转换String类型变量为Int32数据类型(通过简单易学的C#表达式System.Convert.ToInt32(number1_str)

3. 通过“赋值组件”对变量进行赋值

4. 通过条件（If）组件结合Boolean类型变量进行条件判断

<br><br>


### END：

<img width = '600'  src ="https://doria-encooacademyimages.oss-cn-shanghai.aliyuncs.com/2022/12/29/16723050031273.jpg"/>
