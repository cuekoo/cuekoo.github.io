---
title:  "Undergraduate thesis"
layout: post
data:   2015-10-26 12:42:54.476107
categories: blog
---

* TOC
{:toc}

**《手机图像来源手机图像来源鉴别技术研究》Study on Cell-phone Image Source Identification**

概要地回顾了手机来源鉴别的各种方法，然后实现了其中的两种算法，并建立图像库对这两种算法的准确率进行测试与比较。 

Implemented two algorithms to identify the cell-phone image source, and conducted a series of experiments to test the accuracy.

Algorithm 1
-----------

    Gül G, Avcibaş İ. Source cell phone camera identification based on singular
    value decomposition[C]. Information Forensics and Security, 2009. WIFS
    2009. First IEEE International Workshop on. IEEE, 2009: 171-175.

利用奇异值分解SVD从图像中提取出了三种类型的特征，
并根据这些特征，利用支持向量机SVM对特征进行分类，以实现图像来源鉴别。

![](/images/undergraduatethesis/projects1-1.png)

Algorithm 2
-----------

    Fridrich J, Lukas J, Goljan M. Digital camera identification from sensor
    noise[J]. IEEE Transactions on Information Security and Forensics, 2006, 1(2):
    205-214.

利用传感器模式噪声对图像来源进行鉴别。

![](/images/undergraduatethesis/projects1-2.png)

对比实验数据集
--------------

![](/images/undergraduatethesis/dataset.png)

实验结论
--------

算法一在图像库为灰度图像的情况下，通过对图像中特征的提取，获得了良好的鉴
别效果。其鉴别不限于品牌与型号，可以对同品牌同型号的手机图像进行区分。但算法
一的准确率与手机的品牌，型号，分辨率都具有密切关系。由于需要利用统计学得到鉴
别模型，因此用于建立模型的图像的多少会对实验结果产生直接地影响。

算法二具有优良的鉴别效果。如果计算参考模式噪声的图像数量增加，截取区域面
积增加，则可以获得更高的鉴别准确率。其鉴别同样不限于品牌与型号，可以对同品牌
同型号的手机图像进行区分。不管手机是什么品牌、型号、分辨率，其鉴别准确率普遍
较高。
