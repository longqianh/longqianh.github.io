---
title: Image Processing 学习笔记
date: 2020-01-24 23:34:36
tags:
categories: 
- Computer Science
- image processing

---

# 图像信息处理

##  1  灰度变换与空间滤波

### 1.1 灰度变换：$s=T(r)$

- 图像反转：$s=L-1-r$
- 对数变换：$s=c\log(1+r)$
- 伽马变换：$s=cr^\gamma$
- 分段分式线性变换：对比度拉伸、灰度级分层、比特平面分层



### 1.2 直方图处理

$ h(r_k)=n_k$ ，$r_k$ 是第 $k$ 级灰度值，$n_k$ 为图像中灰度为 $r_k$ 的像素个数。

归一化： $p(r_k)=n_k/MN$

#### 1.2.1 直方图均衡化

1. $p_s(s)=p_r(r)\cdot |\displaystyle\frac{dr}{ds}|=p_r(r) / |T^{'}(r)|$
2. 选取变换函数  $s=T(r)=(L-1) \displaystyle\int_0 ^r p_r(w)dw$
3. $=> \quad p_s(s)=\displaystyle\frac{1}{L-1}$
4. 离散形式：$ s_k=T(r_k)=(L-1)\displaystyle\sum\limits_{j=0}^k p_r(r_j)=\displaystyle\frac{L-1}{MN}\sum\limits_{j=0}^k n_j $，最后取值四舍五入

#### 1.2.2 直方图规定化

#### 1.2.3 局部直方图处理

略～





## 1.2 空间滤波

空间滤波器由一个邻域和预定义操作组成。

$g(x,y)=\displaystyle\sum\limits_{s=-a}^b\sum\limits_{t=-b}^b w(s,t)f(x+s,y+t)$

### 1.2.1 空间相关与卷积

相关上滤波器模版移过图像并计算每个位置乘积之和的处理，卷积的机理类似，但滤波器首先要旋转$180^o$

#### 1.2.1.1 平滑空间滤波器

- 均值滤波器：$g(x,y)=\displaystyle\frac{\sum\limits_{s=-a}^a\sum\limits_{s=-b}^b w(s,t)f(x+s,y+t)}{\sum\limits_{s=-a}^a\sum\limits_{s=-b}^b w(s,t)}$
- 统计排序滤波器   $e.g. $ 中值滤波器：去除椒盐噪声

$ \\ $

#### 1.2.1.2 锐化空间滤波器

