---
title:  "IR Analyzer"
layout: post
data:   2015-10-25 14:36:06.388367
categories: blog
---

* TOC
{:toc}

这是一个红外序列分析工具，基于OpenCV和Qt实现。主要功能如下：

1. 播放本地或网络传输的红外序列

   左下角可以显示：光标当前位置；光标位置像素值（包含16位数值和映射成8位后的数值）

   右下角为当前帧号

2. 截取图像一部份进行缩放以观测像素值

3. 测试相关算法（比如小目标检测）

4. 显示特征图

示例如下： 

{% include images.html url="/images/iranalyzer/original-image.png" description="原始图像" %}

{% include images.html url="/images/iranalyzer/zoomed-image.png" description="zoom" %}

{% include images.html url="/images/iranalyzer/image-with-target.png" description="测试小目标检测算法" %}

{% include images.html url="/images/iranalyzer/feature-image.png" description="小目标检测特征图像" %}
