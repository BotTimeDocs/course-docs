# 调试的基本操作

## 概述

### 什么是调试？

在流程编辑过程中，经常会出现一个问题：为什么我的流程不运行？

这是任何开发人员日常编辑流程都会出现的问题。此时我们就需要使用**调试**来帮助我们找到问题所在，并帮助你解决它。

**调试**是一个强大的功能，你可以

- 调试项目或调试文件。
- 在“变量面板”查看变量、参数及组件的属性值，并且抛出异常的详细信息也显示在这里。
- 使用“单步执行”将一步步执行调试，而“单步跳过”不会打开容器类型的组件，帮助你跳过无需关注的流程块。
- 使用“单步跳出”将完成当前组件的执行，并返回到容器类型的组件，从而暂停调试过程。
- 使用“重启”按钮从流程中的第一个组件重新启动调试过程。
- 只要在调试过程中遇到异常，可以“暂停”调试，“忽略”该错误并继续调试。
- “重试”按钮将重新调试上一个组件，如果再次遇到异常，则抛出该异常。

### 为什么需要调试？

**调试**主要是在将编辑好的自动化项目投入实际使用之前，通过手动或自动的方式进行测试，识别并修正项目中会导致其运行失败的错误的过程，这是保证自动化项目正确性的一个重要步骤。

掌握调试的使用是开发人员的一项重要技能，这可以提高你在流程编辑过程中查找问题的效率，帮助你轻松快速地完成一个个可靠、健壮的流程。

## 调试的基本操作

### 设置断点并启动调试

如上所述，调试可以帮助你分析流程执行的问题。当你直接启动调试时，会立即开始执行你的流程。由于流程的执行速度非常快，因此你需要能够对某些组件暂停执行。你可以使用**断点**来暂停执行。

通过选择一个组件，右键菜单选择“断点”可以帮助你添加断点。启用断点后，可以看到一个红色圆圈。若要删除断点，可以再打开右键菜单选择“删除断点”。

启用断点后，启用调试将会在命中第一个断点处暂停。

> **注意：**
>
> 此时暂停处的组件并未执行。

![断点操作](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/BreakPoints.gif)

### 运行面板

设置断点并启动调试后，编辑器将显示新的面板和调试操作。

- 调试操作
- 变量状态

![运行面板](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/RunPanel.png)

#### 调试操作

可以使用这些操作来控制流程的执行过程。

![调试操作](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/DebugButton.png)

- 继续或暂停执行

    如果执行已暂停，可以点击“继续”，继续执行流程，直至命中下一个断点再次暂停。如果流程正在执行，此时按钮将切换为“暂停”，可以使用该按钮来暂停执行过程。

    ![继续或暂停执行](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/Break.gif)

- 单步执行

    一次仅执行一个组件。如果下一个组件是容器类组件（如序列），将会打开容器类组件，然后从该组件内的第一个组件依次开始执行。

    ![单步执行](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/Step%20Into.gif)

- 单步跳过

    执行当前上下文中的下一个容器类组件，不会单步执行流程中的非容器类组件（组件仍会执行，只是不会一个个显示）。

    > **说明：**
    >
    > 若容器类组件内的组件存在断点，则仍会进入并执行。

    ![单步跳过](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/StepOver.gif)

- 单步跳出

    如果在容器类组件内部，将会执行该容器类组件的其余组件，并在执行完成后跳出该容器类组件。

    ![单步跳出](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/StepOut.gif)

- 重试

    重新执行上一个组件，如果仍然遇到了异常，将会抛出该异常。

    ![重试](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/Retry.gif)

- 忽略

    忽略遇到的异常，并从下一个组件继续执行，以便可以继续调试其余的流程。

    ![忽略](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/Ignore.gif)

- 重启

    从头开始重新执行流程，执行过程将在命中的第一个断点处暂停。

- 停止

    结束执行并退出调试。

#### 查看变量面板状态

分析导致流程未正确执行的原因时，可以通过“变量面板”查看变量、参数等状态来查找意外更改。

变量面板主要显示：

- 变量：定义的全部变量状态
- 参数：定义的全部参数状态
- 上一个组件的属性：仅显示输入和输出属性
- 异常：流程出错时抛出的异常类型和值

![变量面板](https://docimages.blob.core.chinacloudapi.cn/images/Studio/Extra/Debugging/VariablesPanel.png)
