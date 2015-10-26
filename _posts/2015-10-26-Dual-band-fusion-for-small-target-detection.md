---
title:  "Dual-band fusion for small target detection"
layout: post
data:   2015-10-26 16:27:27.416970
categories: blog
---

* TOC
{:toc}

原始图像
--------

给定中长波图像分别如下图所示，其中白色矩形内待检测的真实目标。

{% include images.html url="/images/fusion/mw.png" description="中波图像" %}

{% include images.html url="/images/fusion/lw.png" description="长波图像" %}

原始特征图像
-----------

分别对中长波图像进行计算我们选定的小目标特征。此时，每个像素对应一个特征向量
$$\mathbf{x}\in \mathbb{R}^2$$。对特征向量进行直方图统计得到下图。其中白色十字
为目标对应的特征。由直方图可见，与目标向量具有相近特征向量的像素点有将近100个。
此时很难简单地从特征向量中提取目标。

{% include images.html url="/images/fusion/histMwLw.png" description="双波段原始特征直方图" %}

融合特征图像
------------

我们采取**融合算法**对双波段进行融合，此时仍然使得每个像素对应一个特征向量$$\mathbf{x}\in
\mathbb{R}^2$$。由下图可见，

1. 此时目标对应的特征向量约有10个像素，大致与目标中像素个数相当
1. 目标对应的特征向量两个维度均取比较大的值，信噪比得到了提升

{% include images.html url="/images/fusion/histSumErr.png" description="融合后双波段特征直方图" %}

基于融合目标检测结果
--------------------
我们对特征向量的两个维度均取0.5做为阈值，得到如下检测结果。

{% include images.html url="/images/fusion/detectResult.png" description="基于融合目标检测结果" %}


结论
---

融合算法能够提高信噪比，综合两个波段的信息提高目标检测性能。
