---
title: OLAP的基本分析操作
date: 2019-12-23 23:48:38
tags: [OLAP,数据仓库,数据分析]
categories: 数据仓库
notebook: 数据仓库
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OLAP作为数据仓库的自然扩展功能，是数据分析的重要组成部分，下面来看下基于数据仓库的OLAP基本分析操作。

<img src="OLAP的基本分析操作/eggs.jpeg" width="500" height="300"/>

<!-- more -->

1. 切片
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在多维数据集的某一维上选定一个维成员的操作称为切片，例如，在多维数组（维1，维2，维3，...，维n，度量列表）中选定一维，即维i，并取其中一维成员v1，所的的多维数组的子集（维1，维2，维3，...，v1，维i+1，...，维n，度量列表）称为v1上的一个切片；
2. 切块
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在多维数据集（维1，维2，维3，...，维n，度量列表）中通过对2个或多个维执行选择得到子集的操作称为切块；
3. 旋转
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;又称为转轴，是一种视图操作，即改变一个报告或页面显示的维方向，可以得到不同视角的数据，即转动数据的视角以提供数据的替代表示，例如旋转可能包含交换行和列，即维的位置互换，就像是二维表的行列转换，或是把某一个行维移动到列维中取，或把页面显示中的一个维和页面外的维进行交换。
4. 上卷
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;上卷操作通过维的概念分层向上攀升或者通过维规约（即将4个季度的值加到一起为一年的结果）在数据立方体上进行聚集。如在产品维度上，由产品向小类上卷，可得到小类的聚集数据，再由小类向大类上卷，可得到大类层次的聚集数据。
5. 下钻
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;下钻是上卷的逆操作，它由不太详细的数据到更详细的数据。使用户在多层数据中能通过导航信息而获得更多的细节数据。下钻可以沿维的概念分层向下或引入新的维或维的层次来实现。


- - -
<b>You must always do some investment in yourself anytime.</b>