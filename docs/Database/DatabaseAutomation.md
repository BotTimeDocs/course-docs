
# 数据库操作自动化

在此单元中，将创建一个自动执行MySQL数据库操作（创建表、查询）并将数据输出到CSV的机器人。

目前支持的数据包括：SQL、MySQL、Oracle、Teradata和IBM DB2，本课程中使用的是MySQL


在此单元你将学习到：
- 使用[连接数据库](https://academy.encoo.com/zh-cn/wiki/Activities/Database/ConnectDatabase.md)组件
- 使用[执行事务](https://academy.encoo.com/zh-cn/wiki/Activities/Database/StartTransaction.md)组件
- 使用[执行语句](https://academy.encoo.com/zh-cn/wiki/Activities/Database/ExecuteNonQuery.md)组件
- 使用[查询](https://academy.encoo.com/zh-cn/wiki/Activities/Database/Select.md)组件

准备工作：
- 一个可用的MySQL服务


## 创建项目

1. 在编辑器创建一个新的项目"DatabaseAutomationDemo"
2. 在【组件】面板【数据库】目录下找到【连接数据库】组件，并将其拖拽进新建项目Main设计面板中


## 配置MySQL服务器参数

1. 双击【连接数据库】组件并点击配置【配置向导】

    > **ProviderName：** 选择 MySql.Data.MySqlClient

    > **ConnectionString：** 输入连接到此数据库服务器的字符串 "Server={服务器地址};Database={DB名字，本课程中用Demo};Port={端口号};Uid={uid};Pwd={password};"
2. 点击【测试连接】确认是否可成功连接数据库

    ![DB](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DatabaseAutomation/DB-1.png)

## 数据库操作

1. 将【执行事务】组件拖入【连接数据库】中
2. 并继续向【执行事务】组件中拖入两个【执行语句】组件和一个【查询】组件

    ![DB](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DatabaseAutomation/DB-2.png)

3. 配置第一个【执行语句】组件属性，此组件用于执行在数据库创建表的语句

    > **显示名称：** 为了更加清晰理解组件用途我们在这里将显示名称更改为 "执行语句(创建表)"

    > **Sql语句：** 创建一个名为Students的表, 填充内容为"CREATE TABLE `Students` (`ID` int NOT NULL AUTO_INCREMENT,`UserName` varchar(254) DEFAULT NULL,`Age` int DEFAULT NULL,`Score` varchar(254) DEFAULT NULL,PRIMARY KEY (`ID`)) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci"

4. 配置第二个【执行语句】组件属性
    > **显示名称：** 为了更加清晰理解组件用途我们在这里将显示名称更改为 "执行语句(插入数据)"

    > **Sql语句：** 创建一个名为Students的表, 填充内容为"INSERT INTO `Demo`.`Students`(`UserName`,`Age`,`Score`) VALUES('Leo',18,'90'),('James',17,'90'),('JK',16,'90'),('Iverson',19,'90')"

5. 配置【查询】组件属性

    > **数据表：** 在【变量】面板创建一个数据类型为System.Data.DataTable且范围为MainFlow的变量 dtStudents, 回到属性面板并将此变量填写到此参数

    > **Sql语句：** 输入查询语句 "select * from Demo.Students"

## 将数据结果保存至CSV文件

 1. 回到MainFLow设计面板，将【保存为CSV文件】组件拖入并与【连接数据库】建立连接

     ![DB](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DatabaseAutomation/DB-3.png)

 2. 配置【保存为CSV文件】组件的属性

    > **数据表：** 输入之前定义的变量 dtStudents

    > **文件路径：** 输入".\Files\Students.csv" 将结果保存在项目目录下


## 执行项目查看结果
点击【运行】即可完成在数据库创建表、向表中插入数据并读取数据后将结果保存至项目目录下的Files文件夹
&nbsp;
    ![DB](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DatabaseAutomation/DB-4.png)



## 如何在编辑器中下载并使用本课程示例
1. 打开编辑器，在工具栏点击【流程市场】
2. 搜索此课程名称即可找到此流程
3. 选中流程并点击【下载】图标，在【新建项目】弹窗中输入【项目名称】
4. 点击【创建】此时将会在本地创建一个新的项目
5. 在【工作目录】面板即可打开创建的项目
