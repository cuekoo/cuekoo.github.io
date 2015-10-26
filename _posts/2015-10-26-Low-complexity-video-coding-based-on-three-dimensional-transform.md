---
title:  "Low complexity video coding based on three dimensional transform"
layout: post
data:   2015-10-26 13:11:40.420263
categories: blog
---

* TOC
{:toc}

With team members Wu Gang and Li Suoheng. Our goal is to design a "simple"
codec based on 3-D Discrete Cosine Transform (DCT) to eliminate the
computational complexity in conventional coding schemes that involve motion
estimation (ME).

![](/images/videocodec/system.png)

We worked on the following problems:

1. determine the transform block size
2. find fast 3-D DCT algorithm
3. determine the scanning scheme, based on
    * correlation of moving pixels
    * order of quantized coefficients 
    * entropy coding



