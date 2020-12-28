# Python组件应用

云扩 RPA 已加入了对 Python 的支持，并封装了3个 Python 组件，在**组件面板** > **代码工具** > **Python**目录下可以找到,分别是**安装Python**、**Python环境**和**执行Python代码**。
- **安装Python组件**：检测本机是否已安装 Python，若未安装便将指定的 Python 安装文件自动安装在计算机上。
- **Python环境组件**：作为Python 的运行环境，指定 Python 环境及工作目录。
- **执行Python代码组件**：包含Python代码，支持编写和传参等。

   > **说明：**
   >
   > **执行Python代码**组件仅可运行在**Python环境组件**内。

## 准备工作
已下载Python安装程序。

## 编写流程
1. 在编辑器中创建项目并命名为**Python_Demo**
2. 在组件面板找到**安装Python**组件，并拖入到设计面板。属性配置如下：
    - **安装文件路径：** 输入已下载到本机的Python安装程序路径（参考："K:\Python\python-3.9.0-amd64.exe"）  
    - **安装至目录：** 输入欲安装的目标目录。本课程中为空，为空则安装至计算机默认目录
3. 在组件面板找到**Python环境**组件，并拖入到设计面板。属性配置如下：
    - **Python环境路径：** 若为空则默认读取当前计算机Python环境变量。（参考： @"C:\Users\jingk\AppData\Local\Programs\Python\Python39"）
    - **工作目录：** 指定Python文件的工作目录。本课程中为空
    - 
    ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-1.png)

4. 在组件面板找到**执行Python代码**组件，并拖入到**Python环境**组件内。此时会在**项目目录**->**.code**->**Python**下自动生成一个名为执行Python代码.py的文件。

    ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-2.png)

    ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-2-1.png)

5. 点击**编辑代码**并编写如下代码：

    ```python
    import sys
    from function import add

    if __name__ == "__main__":
        firstNumber=sys.argv[1]
        secordNumber=sys.argv[2]
        sum=add(int(firstNumber),int(secordNumber))
        #Sample code for output argument
        print("Output argument 'sum' value is: {0}".format(sum)

    ```

6. 点击**设置参数**并配置如下：

    ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-3.png)

7. 在Python文件下创建一个名为**function.py**的文件，并编写如下代码：

    ```python
    import sys

    def add(a,b):
       return a+b

    def sub(a,b):
       return a-b
    ```
    ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-4.png)

8. 将**写入日志**组件拖入到设计面板，属性配置如下：

    **日志内容：** 将计算结果输出到日志

    ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-5.png)

9. 点击**运行**，在输出面板查看执行结果，如下图：
   ![Python](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/Python/Python-6.png)