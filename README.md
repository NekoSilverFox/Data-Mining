<p align="center">
 <img width="100px" src="https://raw.githubusercontent.com/NekoSilverFox/NekoSilverfox/403ab045b7d9adeaaf8186c451af7243f5d8f46d/icons/silverfox.svg" align="center" alt="NekoSilverfox" />
 <h1 align="center">数据挖掘</h1>
 <p align="center"><b>子标题（说明）</b></p>
</p>


<div align=center>



[![License](https://img.shields.io/badge/license-Apache%202.0-brightgreen)](LICENSE)
![Library](https://img.shields.io/badge/Library-Scikit--learn-orange)
![Python](https://img.shields.io/badge/Python-3.8+-blue)



<div align=left>
<!-- 顶部至此截止 -->



[toc]



# 环境安装与介绍

| 库         | 说明                                                |
| ---------- | --------------------------------------------------- |
| matplotlib |                                                     |
| numpy      |                                                     |
| pandas     |                                                     |
| TA-Lib     | 技术指标库                                          |
| tables     | 读取某一种数据文件（hdf5 - 经过压缩的一种数据文件） |
| jupyter    | 数据分析与展示的平台                                |



## Jupyter Notebook

### 简介

**Jupyter Notebook 可以理解为 web 版本的 iPython**

Jupyter项 目是一个非盈利的开源项目，源于2014年的Python项目，并逐渐发为支持跨所有编程语言的交互式数据科学计算的工具。

- JupyterNotebook，原名 ipython Notebook，是 iPython 的加强网页版，一个开源Web应用程序
- 名字源自 Julia、 Python 和 R（数据科学的三种开源语言）
- 是一款程序员和科学工作者的编程/文档/笔记/展示软件
- `ipynb` 文件格式是用于计算型叙述的 **JSON文档格式**的正式规范



**为什么使用 Jupyter Notebook？**

- 画图和展示数据方便



### cell 操作

**cell：一对 In-Out 会话被视作一个代码单元，称为 cell**

Jupyter 支持两种模式：

- 编辑模式（ Enter）
    - 命令模式 下`回车 Enter` 或 `鼠标双击 cell` 进入编辑模式
    - 可以操作 cell 内文本或代码，剪切/复制/粘贴移动等操作
- 命令模式（Esc）
    - 按Esc退出编辑，进入命令模式
    - 可以操作 cell 单元本身进行剪切/复制/粘贴/移动等操作

![image-20220126001603579](doc/pic/README/image-20220126001603579.png)



### 使用 Jupyter Notebook

| 功能                                 | 快捷键                                               |
| ------------------------------------ | ---------------------------------------------------- |
| 打开 Jupyter Notebook                | 终端中输入：`jupyter notebook` 或 `ipython notebook` |
| 运行此单元格的代码，并自动选择下一个 | Shift + Enter                                        |
| 运行此单元格的代码，留在此单元       | Ctrl + Enter                                         |
|                                      |                                                      |



| 命令模式下（ESC 进入） | 操作                        |
| ---------------------- | --------------------------- |
| A                      | 在当前 cell 上面插入新 cell |
| B                      | 在当前 cell 下面插入新 cell |
| 双击D                  | 删除当前 cell               |



| 编辑模式下（Enter 进入）  | 操作       |
| ------------------------- | ---------- |
| Ctrl + / 或 CMD + /       | 添加注释   |
| 按住 Alt 或 Option 点鼠标 | 多光标操作 |
| Tab                       | 补全代码   |



## Matplotlib



### 简介

![image-20220126002904416](doc/pic/README/image-20220126002904416.png)

**名字：**

- mat - matrix
- plot - 画图
- lib - library



**功能：**

- 专门用于开发 2D 或 3D 图表的 Python 库
- 使用起来极其简单
- 以渐进、交互式方式实现数据可视化



**为什么学习 Matplotlib**

将数据可视化，更直观的呈现；在我们进行数据挖掘和分析之前可以帮助我们选择一个更加适合的方法。

言外话：在 JavaScript 中好用的数据可视化工具有 D3 和 百度的 echarts



### 图像结构

![image-20220126005157777](doc/pic/README/image-20220126005157777.png)



### Matplotlib 三层结构

![image-20220126172822687](doc/pic/README/image-20220126172822687.png)

#### 容器层

**由底向高：**

- **画板层（Canvas）**

​	Canvas是位于最底层的系统层，在绘图的过程中充当画板的角色，即放置画布（Figure）的工具。



- **画布层（Figure）**

    Figure是 Canvas上方的*第一层*，也是需要用户来操作的应用层的第一层，在绘图的过程中充当画布的角色

    创建或设置画布：`plt.figure()`

    

- **绘图区/坐标系（Axes）**

    Axes是应用层的第二层，在绘图的过程中相当于画布上的绘图区的角色

    画布上是默认有一个绘图区，一个绘图区是有 x、y 轴张成的区域

    手动创建新的话：`plt.subplots()`

    - **图像层**

        每一个绘图区上的不同图像层都可以画不同的图表

        图像层指 Axes 内通过 plot、scatter、bar、histogram、pie 等函数根据数据绘制出的图像

        

    - **辅助显示层**

        图像上的那些坐标、网格、辅助线等。辅助图像的显示

        辅助显示层为 Axes（绘图区）内的除了根据数据绘制出的图像以外的内容，主要包括 Axes外观（facecolor）、边框线（spines）、坐标轴（axis）、坐标轴名称（axis labe）、坐标轴刻度（tick）、坐标轴刻度标签（tick label）、网格线（grid）、图例（legend）、标题（title）等内容

        该层的设置可使图像显示更加直观更加容易被用户理解，但又不会对图像产生实质的影响



**特点：**

- 一个 figure（画布）可以包含多个axes（坐标系/绘图区），但是一个axes只能属于个 figure
- 一个axes（坐标系/绘图区）可以包含多个axis（坐标轴），包含两个即为2d坐标系，3个即为3d坐标系



**总结：**

- Canvas（画板）位于最底层，用户一般接触不到
    - Figure（画布）建立在 Canvas 之上
        - Axes（绘图区）建立在 Figure之上
            - 坐标轴（axis）、图例（legend）等辅助显示层以及图像层都是建立在 Axes 之上

![image-20220126171952434](doc/pic/README/image-20220126171952434.png)

![image-20220126171055906](doc/pic/README/image-20220126171055906.png)



### 辅助显示层







### 图像层













































































































