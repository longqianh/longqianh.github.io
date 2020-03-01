---
title: 论文笔记-L2-Net
date: 2020-02-23 16:42:04
tags:
---

论文链接：http://www.nlpr.ia.ac.cn/fanbin/pub/L2-Net_CVPR17.pdf

代码链接：https://github.com/yuruntian/L2-Net

研读次数：1

## 提出的好方法

- a progressive sampling strategy 渐进采样策略，可使网络在有限次数内获得大量样本

- Discriminative Intermediate Feature map (DIF)  在中间的特征层施加了额外的监督

- Loss function that takes three important error aspects into account:

  - descriptor similarity 未完全理解
  - descriptor compactness :  ‘An interesting finding is that the degree of overfitting is directly related to the degree of correlation among descriptor dimensions’ 
  - intermediate feature maps 未完全理解

  

### 须了解的相关知识

- SIFT descriptor
- NNS (nearest neighbor search)
- MatchNet (a typical Siamese network)

 

### 应用

- 实现 *特征匹配* 的神经网络的训练

