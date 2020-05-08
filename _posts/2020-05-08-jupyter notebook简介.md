---
layout:     post
title:      jupyter notebook简介
subtitle:   jupyter是什么怎么用
date:       2020-05-08
author:     刘政永Dmer
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - 数据挖掘故事
---
##  1.Jupyter notebook 是什么？
在没有notebook之前，在IT领域工作的我都是这样工作的：

在普通的 Python shell 或者在IDE（集成开发环境）如Pycharm中写代码，然后在word中写文档来说明你的项目。

这个过程很反锁，通常是写完代码，再写文档的时候我还的重头回顾一遍代码。最蛋疼的地方在于，有些数据分析的中间结果，我还的重新跑代码，然后把结果弄到文档里给客户看。

有了notebook之后，我的世界突然美好了许多，因为notebook 可以直接在代码旁写出叙述性文档，而不是另外编写单独的文档。也就是它可以能将代码、文档等这一切集中到一处，让用户一目了然。

![]({{site.baseurl}}/img/post-bd-jupyter.png)

所以，你现在明白了上面这句话是在说什么了：

Jupyter notebook（http://jupyter.org/） 是一种 Web 应用，能让用户将说明文本、数学方程、代码和可视化内容全部组合到一个易于共享的文档中。
Jupyter Notebook 已迅速成为数据分析，机器学习的必备工具。因为它可以让数据分析师集中精力向用户解释整个分析过程。

Jupyter这个名字是它要服务的三种语言的缩写：Julia，PYThon和R，这个名字与“木星（jupiter）”谐音。

## 2.如何启动 Jupyter notebook？

对于做数据分析这么有用的神器，不安装使用下是不是很遗憾？

安装 Jupyter 的最简单方法是使用 Anaconda。该发行版附带了 Jupyter notebook。你能够在默认环境下使用 notebook。

如何打开notebook？

点击开始菜单栏，找到anconda3打开，找到jupyter notebook，点击打开就可以了。

启动notebook 服务器后，在浏览器中会自动打开notebook页面地址：http://localhost:8888
（其中localhost 表示你的计算机，而 8888 是服务器的默认端口）

## 3.新手如何快速使用notebook？

### （1）顶部的3个选项卡

顶部的3个选项卡是：Files（文件）、Running（运行）和 Cluster（集群）。

Files（文件）显示当前“notebook工作文件夹”中的所有文件和文件夹。

点击 Running（运行）选项卡会列出所有正在运行的 notebook。可以在该选项卡中管理这些 notebook。

Clusters一般不会用到。因为过去在 Clusters（集群）中创建多个用于并行计算的内核。现在，这项工作已经由 ipyparallel 接管。

### （2）如何创建一个新的notebook？

像下面图片中一样，在右侧点击“New”（新建），创建新的 notebook、文本文件、文件夹或终端。

“Notebooks”下的列表显示了你已安装的内核，这里直接选择你电脑上默认的环境名即可。

这样你就打开了页面，你会看到外框为绿色的一个小方框。它称为单元格。单元格是你编写和运行代码的地方。以后你就可以在这里写你的数据分析代码了。

在这里你可以输入自己人生中的第一行Python代码Hello world。然后点击图中的运行按钮，会执行你当前所在的代码，其实我更喜欢用快捷键（键盘上同时按住ctrl+enter键）来执行代码。
