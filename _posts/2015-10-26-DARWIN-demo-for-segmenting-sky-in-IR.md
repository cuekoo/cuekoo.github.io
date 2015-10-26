---
title:  "DARWIN demo for segmenting sky in IR"
layout: post
data:   2015-10-26 11:01:03.396373
categories: blog
---

* TOC
{:toc}


DARWIN

    Stephen Gould. DARWIN: A framework for machine learning and computer vision
    research and development. The Journal of Machine Learning Research,
    13(1):3533–3537, 2012.

is effective for simple cases as demonstrated below, where we are attempting to 
segment out the sky (including cloud) areas. The training set is super simple, just one labeled 
image. For more complex situations, we are trying to

1. Get better training set
1. Use more complex models, such convolutional neural networks

{% include images.html url="/images/darwindemo/demo1.png" description="Test result" %}

{% include images.html url="/images/darwindemo/demo2.png" description="Test result" %}
