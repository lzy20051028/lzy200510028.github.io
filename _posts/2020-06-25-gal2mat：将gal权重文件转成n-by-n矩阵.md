---
layout:     post
title:      gal2mat：将gal权重文件转成n-by-n矩阵
subtitle:   
date:       2020-06-25
author:     刘政永Dmer
header-img: img/post-bg-dmers.jpg
catalog: true
tags:
    - 听取树蛙一篇
---
## 1.gal格式文件

GeoDa 生成的gal权重文件为文本格式，可用“记事本”打开。如下图所示的描述中国31个大陆省份邻近情况的文件内容，其第一行为文件头说明，表示有31个单元，基于shape文件Province31生成，识别单元的变量为POLY_ID。第2行表示POLY_ID编号为1的单元有2个邻居，它们的编号在第3行给出，分别为15和19；第4行和第5行给出编号为2的邻居信息，余者类推。需要说明的是，海南（编号为20）没有邻居，因此其邻居数为0，下面一行为空。

## 2.R语言程序gal2mat

利用R语言包spdep包中的nb2mat，可以将gal文件转成n*n矩阵。nb2mat默认为行标准化。如果有单元无邻居，需要将zero.policy设为TRUE。

现自编R语言程序gal2mat()将gal文件转成n*n矩阵，其参数设定如下：

gal2mat(gal, row.st = TRUE)

其中，gal为文件路径，row.st设定要不要行标准化，默认为TRUE。

注：你会发现，如果有单元无邻居，这会带来一些问题。如何解决？且听下回分解。

代码

#设置为自己的工作文件夹

> setwd("…\\gal2mat")

#用nb2mat将gal文件转成矩阵

> library(spdep)

> mynb <- read.gal("province31.gal")

> spmat1 <- nb2mat(mynb, zero.policy=TRUE)

#用自编函数将gal文件转成矩阵

#载入函数gal2mat

> source("gal2mat.R")

> spmat2 <- gal2mat("province31.gal")

Read 198 items

Warning messages:

1: In gal2mat("province31.gal") : Unit 20 has no neighbor.

2: In FUN(newX[, i], ...) : The sum of row is 0.

#比较spmat1和spmat2是否一致，结果显示为一致

> all(spmat1 == spmat2)

[1] TRUE

#写出n*n空间权重矩阵

> write.csv(spmat2, "spmat.csv")


