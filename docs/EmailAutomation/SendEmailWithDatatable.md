# 如何发送包含表格内容的邮件

大家好，这节课我们就来讲讲如何使用云扩 RPA 的【发送邮件】组件来发送包含表格数据内容的邮件，我们在使用【发送邮件】组件的时候，发现发送内容只能是 String 数据类型，但是读取 Excel 内容的数据表区域的数据类型是 Datatable 类型，这时我们想要将表格内容发送邮件，组件使用过程需要特殊处理一下。

接下来，我们介绍流程开发的详细步骤及思路。

## **准备工作**

1. 准备开发流程的电脑，请打开云扩学院链接查看云扩 RPA 编辑器运行的硬件&软件要求。(<https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md?>)

2. 打开云扩官网（<https://www.encoo.com/>)下载编辑器并安装。

3. 准备一个简单的 Html 文件，具体文件内容请看下面描述。

## **操作流程**

![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable1.png)

## **操作步骤**

1. 新建一个临时 HTML 文件，文件内容如下：
  
  ```html
  <html>
   <head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
  <title>HTML</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
   </head>
  <body style="margin: 0; padding: 0; auto" >
   <div>
   <span>
  文本内容
   </span>
   </div>
   <table  border="1" cellspacing="0" cellpadding="0">
    <tbody>
  表格内容
    </tbody>
   </table>
  </body>
</html>
  ```

  ![代码内容](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable2.png)  

2. 创建并打开项目：

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable3.png)

3. 打开 Excel，并获取需要发送的表格内容

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable4.png)

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable5.png)

4. 新建 2 个变量来分别接受文本内容和表格内容的数据

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable6.png)

5. 拖入 "读取文件" 组件，来读取临时 Html 的文件内容

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable7.png)

6. 拖入 "C#代码" 组件来处理需要写入的表格内容
    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable8.png)

    那么同理，我们来执行 C#处理表格数据 datatable 时，就可以通过如下代码来实现：

 ```c#
//代码执行入口，请勿修改或删除
public void Run()
{
    try{
    //循环遍历datatable每一行
    foreach(DataRow dr in dt.Rows)   
    {     
    //每次开始一行时，就往变量中加入一个<tr>标签
    表格内容 = 表格内容 + "<tr>";
    for(int j=0;j<dt.Columns.Count;j++)      
    {   
      //每次开始遍历一行中每个列的值时，就往变量中加入一个<td>标签
      表格内容 = 表格内容 + "<td  width=\"100\"><span>";  
      Console.WriteLine(dr[j].ToString()); 
      
      //接着在这个td标签后面加上表格中值的内容
      表格内容 = 表格内容 + dr[j].ToString() +"</span></td>";      
    } 
    //每次结束一行时，就往变量中加入一个</tr>标签
    表格内容 = 表格内容 + "</tr>";  
  }  
  
  //最后将表格中每个值都读取完成之后，就将临时变量
  //处理的网页代码内容替换原来html网页中表格内容4个字
  htmlText = htmlText.Replace("表格内容",表格内容);
  //将赋值的文本内容替换原来html网页中文本内容4个字
  htmlText = htmlText.Replace("文本内容",文本内容);
  }
  catch(Exception e)
  {  
    Console.WriteLine(e.Message);
  }  
    
}
//在这里编写您的函数或者类
```

  ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable9.png)

7. 拖入 "发送邮件" 组件，并配置邮件信息

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable10.png)

8. 运行观察结果

    ![](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/SendEmailWithDatatable/202122SendEmailWithDatatable11.png)

 好了各位，今天的课程就到此为止，有任何问题或者其他开发思路可留言告诉我们，下节课再见~