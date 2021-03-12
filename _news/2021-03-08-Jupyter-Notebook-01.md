---
layout: post
title: Jupyter Notebook 入门配置
tags:
- python
---


Jupyter Notebook作为学习数据分析、机器学习的必备工具(相对于其他IDE)，安装方法这里不做描述，网上有很多，
最简单的方式就是安装Anaconda，当然似乎使用Anaconda也要必直接安装Python更好，如果你是要学习数据分析或机器学习的话
，因为它给你已经集成了大多常用的三方包和依赖项。   

##### 1. 设置Jupyter的默认文件路径

- 修改jupyter的配置文件    
点击菜单中的Jupyter Notebook 快捷方式，启动应用，会看到File目录中有大量的文件，这一般是显示的默认文件夹
目录，我们需要切换到专门的目录中去。首先通过下面命令：
```
jupyter notebook --generate-config
```
查找到jupyter_notebook_config.py文件的位置，如下图所示文件位置：
![1.png](https://i.loli.net/2021/03/09/zoNHWtV5yUTYi3C.png)
   
打开文件jupyter_notebook_config.py，找到关键字 "c.NotebookApp.notebook_dir" 放开注释，设置
新的默认文件路径，如下图    
![](https://i.loli.net/2021/03/10/HP8Gm9h5F7dcnUL.png)
> 注意：输入命令要满足python格式，开头不要有空格，否则会出错，Windows系统特别要注意文件路径要用反斜杠，或者双斜杠
或者前面加r,比如：
```shell script
c.NotebookApp.notebook_dir = 'E:/developer/jupyter'
c.NotebookApp.notebook_dir = 'E:\\developer\\jupyter'
c.NotebookApp.notebook_dir = r'E:\developer\jupyter'
```

- 修改jupyter快捷方式    
删除掉快捷方式-->目标中的"%USERPROFILE%/",如下图，然后点击应用和确定    
![](https://i.loli.net/2021/03/10/a7BMSYjklLsN65u.png)

- 重启Jupyter notebook ,就是清爽版的Jupyter 了
![](https://i.loli.net/2021/03/10/Y4BZn58eux73Fgt.png)

##### 2. Jupyter界面

- 关联conda环境和包    
执行下面命令将conda环境关联到Jupyter，便于你在jupyterNotebook的使用中，
在不同环境中创建笔记本进行工作。
```
conda install nb_conda
```
![](https://i.loli.net/2021/03/10/oj1WwqUSzb9yThi.png)

- 安装Nbextensions页面    
Nbextensions页面提供了多个Jupyter Notebook的插件，使其功能更加强大。    
因为jupyter没有提供MarkDown编辑器，需要安装插件的方式来实现。    
```shell script
conda install -c conda-forge jupyter_contrib_nbextensions
```
