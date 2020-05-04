---
title: Image Processing 学习笔记
date: 2020-01-24 23:34:36
tags:
categories: 
- Computer Science
- Image Processing

---

# 图像信息处理

##  1  灰度变换与空间滤波

### 1.1 灰度变换：$s=T(r)$

- 图像反转：$s=L-1-r$
- 对数变换：$s=c\log(1+r)$
- 伽马变换：$s=cr^\gamma$
- 分段分式线性变换：对比度拉伸、灰度级分层、比特平面分层

$ \\ $ <!--more-->

### 1.2 直方图处理

$ h(r_k)=n_k$ ，$r_k$ 是第 $k$ 级灰度值，$n_k$ 为图像中灰度为 $r_k$ 的像素个数。不妨从 $0$ 开始，令 $r_k=k$

归一化： $p(r_k)=n_k/MN$

#### 1.2.1 直方图均衡化

1. $p_s(s)=p_r(r)\cdot |\displaystyle\frac{dr}{ds}|=p_r(r) / |T^{'}(r)|$
2. 选取变换函数  $s=T(r)=(L-1) \displaystyle\int_0 ^r p_r(w)dw$
3. $=> \quad p_s(s)=\displaystyle\frac{1}{L-1}$
4. 离散形式：$ s_k=T(r_k)=(L-1)\displaystyle\sum\limits_{j=0}^k p_r (r _ j)=\displaystyle\frac{L-1}{MN}\sum\limits_{j=0}^k n_j $，最后取值四舍五入

#### 1.2.2 直方图规定化

#### 1.2.3 局部直方图处理

略～

$ \\ $

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

定义: $\displaystyle\frac{\partial f}{\partial x}=f(x+1)-f(x)$ , $\displaystyle\frac{\partial ^2f}{\partial^2 x}=f(x+1)+f(x-1)-2f(x)$

(1) 使用拉普拉斯算子

$\nabla^2 f(x,y)=f(x+1,y)+f(x-1,y)+f(x,y+1)+f(x,y-1)-4f(x,y)$

$g(x,y)=f(x,y)+c[\nabla^2 f(x,y)]$

[比较清楚的介绍](https://www.cnblogs.com/polly333/p/7269843.html)



(2) 非锐化掩蔽

1. 模糊原图像 $\overline f (x,y)$
2. 从原图像中减去模糊图像（产生差值图像，即模版）$g_{mask}(x,y)=f(x,y)-\overline f(x,y)$
3. 将模版加到原图像上 $g(x,y)=f(x,y)+k\cdot g_{mask}(x,y)$



(3) 使用梯度算子

[Soble算子](https://blog.csdn.net/qq_29540745/article/details/51918004)：$M(x,y)=|(z_7+2z_8+z_9)-(z_1+2z_2+z_3)|+|(z_3+2z_6+z_9)-(z_1+2z_4+z_7)$





$ \\ $

### 1.2.2 使用模糊技术进行灰度变换和空间滤波

#### 1.2.2.1 模糊集合论

- 模糊集合：$\{(z,\mu(z))\}$  有元素和它的隶属度函数组成的数对组成，$\mu(z)\in[0,1]$

- 模糊逻辑：

   $ A\ AND\ B\iff\min(\mu_A(z),\mu_B(z)),\quad \forall z\in Z $ ,

   $A\ OR\ B\iff \max(\mu_A(z),\mu_B(z)),\quad \forall z\in Z$ ,

   $A=B\iff\mu_A (z)=\mu_B (z),\quad \forall z\in Z $ , 

  $A\subseteq B\iff \mu_A(z)\leq\mu_B(z),\quad \forall z\in Z $ ,

  $A\supseteq B\iff \mu_A(z)\geq\mu_B(z),\quad \forall z\in Z $ .

  

- 应用步骤：

  - $IF-THEN$ 形式化
  - 输入输出模糊化：$\mu_i(z),\mu_o(z)$ 
  - 既满足 $IF$ 又满足 $THEN$ $=> INPUT\&OUTPUT$ $=> \mu_3(z,v)=\min\{\mu_i(z),\mu_o(v)\}$
  - 对每一个 $z_0$ ，最终模糊输出 $Q(v)=\mu_3(z_0,v)$  , 对于多个 $Q_i(v)$ ，全部模糊响应应为单个模糊响应的并集，取 $\max\limits_i (Q_i (v))$ 
  - 去模糊：计算集合重心：$v_0=\displaystyle\frac{\sum\limits_{v=1}^K vQ(v)}{\sum\limits_{v=1}^K Q(v)}$

  

#### 1.2.2.2 利用模糊集合论进行灰度变换

- 目的：增强对比度。黑的更黑，白的更白，灰的仍灰

- $IF-THEN$ 形式化：

  - $IF\quad dark,\quad THEN \quad darker $

  - $IF\quad gray ,\quad THEN \quad gray$

  - $IF\quad white,\quad THEN \quad whiter$

    

- 输入模糊化：$dark-\mu_{id}(z),\quad gray-\mu_{ig}(z),\quad white-\mu_{iw}(z)$

  - $$\mu_{id}(z)=\begin{equation}
    \left\{
    \begin{aligned}
    1 &, &  0\leq z< 80, \\
     \displaystyle\frac{1}{47}(127-z)& , & 80\leq z\leq 127,\\ 0&,& 127<z\leq 255\end{aligned}
    \right.
    \end{equation} $$
  - $$\mu_{ig}(z)=\begin{equation}
    \left\{
    \begin{aligned}
    0 &, &  0\leq z< 80, \\
     \displaystyle\frac{1}{47}(z-80)& , & 80\leq z\leq 127,\\ \displaystyle\frac{1}{47}(174-z)& , & 127<z\leq 174,\\ 0&,& 174<z\leq 255\end{aligned}
    \right.
    \end{equation} $$
  - $$\mu_{iw}(z)=\begin{equation}
    \left\{
    \begin{aligned}
    0 &, &  0\leq z< 127, \\
     \displaystyle\frac{1}{47}(z-127)& , & 127\leq z\leq 174,\\ 1&,& 174<z\leq 255\end{aligned}
    \right.
    \end{equation} $$



- 输出模糊化：$datker-\mu_{od}(v),\quad gray-\mu_{og}(v),\quad whiter-\mu_{ow}(v)$
  - $$\mu_{od}(v)=\begin{equation}\left \{\begin{aligned}\infty,&\quad v=v_d\\ 0,&\quad otherwise \end{aligned}\right.\end{equation}$$
  - $$\mu_{og}(v)=\begin{equation}\left \{\begin{aligned}\infty,&\quad v=v_g\\ 0,&\quad otherwise \end{aligned}\right.\end{equation}$$
  - $$\mu_{ow}(v)=\begin{equation}\left \{\begin{aligned}\infty,&\quad v=v_w\\ 0,&\quad otherwise \end{aligned}\right.\end{equation}$$



- 输出最终模糊响应：$Q(v)=\max\{Q_d,Q_g,Q_w\}=\max\{\min\limits_{v\in Z}\{\mu_{ik}(z_0),\mu_{ok}(v)\}\}$
- 去模糊：$v_0=\displaystyle\frac{\mu_{id}(z_0)\cdot v_d+\mu_{ig}(z_0)\cdot v_g+\mu_{iw}(z_0)\cdot v_w}{\mu_{id}(z_0)+\mu_{ig}(z_0)+\mu_{iw}(z_0)}$



**Code : ** 

```python
# 基于模糊集合论的灰度变换 
# 增加对比度
import numpy as np
import cv2

def f_id(z):

    if z < 80:
        return 1
    elif z >= 80 and z <= 127:
        return 1 / 47 * (127 - z)
    else:
        return 0


def f_ig(z):

    if z >= 80 and z <= 127:
        return 1 / 47 * (z - 80)
    elif z > 127 and z <= 174:
        return 1 / 47 * (174 - z)
    else:
        return 0


def f_iw(z):

    if z >= 127 and z <= 174:
        return 1 / 47 * (z - 127)
    elif z > 174 and z <= 255:
        return 1
    else:
        return 0


def gray_trans(img):
    vd = 0
    vg = 127
    vw = 255
    output_img = np.copy(img)
    m, n = img.shape
    for i in range(1, m):
        for j in range(1, n):
            tmp1 = f_id(img[i][j]) * vd + f_ig(img[i][j]) * \
                vg + f_iw(img[i][j]) * vw
            tmp2 = f_id(img[i][j]) + f_ig(img[i][j]) + f_iw(img[i][j])
            output_img[i][j] = tmp1 / tmp2
    return output_img


img = cv2.imread('test.jpg', 0)
img2 = gray_trans(img)
cv2.imshow('before', img)
cv2.imshow('after', img2)
cv2.waitKey(0)
cv2.destroyAllWindows()

```



**效果：**(before and after)

![before](https://tva1.sinaimg.cn/large/006tNbRwly1gbdwm7ycd7j30dm0go0w3.jpg)

![after](https://tva1.sinaimg.cn/large/006tNbRwly1gbdwm89b0zj30dm0goq6v.jpg)





#### 1.2.2.3 利用模糊集合进行空间滤波

有一种基于模糊集合的边缘提取方法.

$ \\ $ 



## 2 频率域滤波

### 2.1 傅立叶变换基础

#### 2.1.1 冲激函数相关

1. 冲激函数 对连续函数取样和对离散函数取样定义有所不同

2. 冲激串函数：$\displaystyle s_{\Delta T}(t)=\sum\limits_{n=-\infty}^{\infty}\delta(t-n\Delta T)$ , 以 $\Delta T$ 为间隔取样

   

#### 2.1.2 傅立叶变换相关

1. 傅立叶级数：$\displaystyle f(t)=\sum\limits_{n=-\infty}^\infty c_ne^{j\frac{2\pi n}{T}t},\quad c_n=\frac{1}{T}\int_{-\frac{T}{2}}^\frac{T}{2}f(t)e^{-j\frac{2\pi n}{T}t}$, 其中 $f(t)$ 以 $T$ 为周期

2. 傅立叶变换：$\displaystyle\mathcal{F}[f(t)]=\int_{-\infty}^\infty f(t)e^{-2\pi\mu t} dt $

3. 关于原点对称的宽为 $W$ 、高为 $A$ 的带限函数 $W(t)$ 的傅立叶变换： $\mathcal{F}[W(t)]=AWsinc(m)$, 其中在数字图像处理中，$sinc(x)=\displaystyle\frac{sin(\pi x)}{\pi x}$

4. 冲激函数的傅立叶变换：$\mathcal{F}[\delta(t-t_0)]=e^{-j2\pi\mu t_0}=>\mathcal{F}^{-1}[e^{-j2\pi\mu t_0}]=\delta(t-t_0)=>\mathcal{F}[e^{-j2\pi\mu_0 t}]=\delta(-\mu-\mu_0)$

5. 冲激串函数的傅立叶变换 ：

   - 将冲激串函数用傅立叶级数展开（不展开直接变换似乎不一致收敛，就不能交换求和号和积分号）：$\displaystyle s_{\Delta T}(t)=\sum\limits_{n=-\infty}^\infty c_ne^{j\frac{2\pi n}{\Delta T}t},\quad c_n=\frac{1}{\Delta T}\int_{-\frac{\Delta T}{2}}^\frac{\Delta T}{2} s_{\Delta T}(t)e^{-j\frac{2\pi n}{\Delta T}t}=\frac{1}{\Delta T}e^0=\frac{1}{\Delta T}\\=>\displaystyle  s_{\Delta T}(t)=\frac{1}{\Delta T}\sum\limits_{n=-\infty}^\infty e^{j\frac{2\pi n}{\Delta T}t}$
   - $S(\mu)=\displaystyle\mathcal{F}[ s_{\Delta T}(t)]=\frac{1}{\Delta T}\sum\limits_{n=-\infty}^\infty \delta(\mu-\frac{n}{\Delta T})$

6. 卷积：

   $\begin{aligned} f(t)*g(t)&\iff F(\mu)\cdot G(\mu)\\F(\mu)*G(\mu)&\iff f(t)\cdot g(t)\end{aligned}$

   

#### 2.1.3 取样

- 取样后的函数 $\widetilde f(t)=f(t)\cdot s_{\Delta T}(t)=\displaystyle \sum\limits_{n=-\infty}^{\infty}f(t)\delta(t-n\Delta T)$

- 每个取样值：由加权后的冲激强度给出。 $f_k=\displaystyle\int_{-\infty}^{\infty}f(t)\delta(t-k\Delta T)=f(k\Delta T)$

- 取样后的函数的傅立叶变换：$\displaystyle \widetilde F(\mu)=F(\mu)*S(\mu)=\frac{1}{\Delta T}\sum\limits_{n=-\infty}^{\infty}\int_{-\infty}^{\infty}F(\tau)\delta(\mu-\frac{n}{\Delta T}-\tau)d\tau=\frac{1}{\Delta T}\sum\limits_{n=-\infty}^{\infty}F(\mu-\frac{n}{\Delta T})$

  这是取样前函数$F(\mu)$ 的一个拷贝的无限、周期序列，确切的说是周期为 $\displaystyle\frac{1}{\Delta T}$ 的无限延伸的连续函数。

- 另一方面，直接变换得：$\widetilde F(\mu)=\displaystyle \sum_{n=-\infty}^{\infty}\int_{-\infty}^{\infty}f(t)\delta (t-n\Delta T)e^{-j2\pi \mu t}dt= \sum_{n=-\infty}^{\infty}f(n\Delta T)e^{-j2\pi \mu n\Delta T}$ 

- **取样定理**：如果一超过函数最高频率的两倍的取样率来获得样本，连续的带限函数可以完全地从它的样本集来恢复。 $\displaystyle\frac{1}{\Delta T}>2\mu_{max}$
- 复原：令 $H(\mu)=\begin{equation}\left\{\begin{aligned} \Delta T,&\quad -\mu_{max}\leqslant\mu\leqslant\mu_{max}\\ 0.&\quad otherwise\end{aligned}\right.\end{equation}$,  $F(\mu)=H(\mu)\cdot \widetilde F(\mu)$，进而由傅立叶逆变换可复原 $f$
- 但是，在实践中我们通常要限制函数的持续时间，相当于要乘一个周期内为 $1$ 其他地方为 $0$ 的函数，而这在频率域内相当于用 $sinc(x)$ 作卷积，这就引入了频率域无限周期分量。这样，在频率域截取时总无法截取全部周期，混淆总会产生。





### 2.2 离散傅立叶变换 DFT

#### 2.2.1 单变量$DFT$

对 $\widetilde F(\mu)$ 的一个周期取样是 $DFT$  的基础。

记 $f(n\Delta T)$ 为 $f_n$ ,  $\widetilde F(\mu)=\displaystyle \sum_{n=-\infty}^{\infty}f_ne^{-j2\pi \mu n\Delta T}$ 

想在周期 $\mu = 0$ 和 $\mu=\displaystyle\frac{1}{\Delta T}$ 之间得到 $M$ 个等间距的*样本* ，可令 $\mu=\displaystyle\frac{m}{M\Delta T}$.

离散傅立叶变换 $DFT$ 为：
$$
F_m=\sum\limits_{n=0}^{M-1}f_ne^{-j2\pi mn/M}
$$
离散傅立叶逆变换 $IDFT$ 为：
$$
f_n=\frac{1}{M}\sum\limits_{m=0}^{M-1}F_m e^{j2\pi mn/M}
$$
为了更方便表示，引入 $u$ 和 $x$ 代替 $m$ 和 $n$ ：

$DFT$：
$$
F(u)=\sum\limits_{x=0}^{M-1}f(x)e^{-j2\pi ux/M}
$$
$IDFT$：
$$
f(x)=\frac{1}{M}\sum\limits_{u=0}^{M-1}F(u)e^{j2\pi ux/M}
$$


（PS：有点小疑问：为什么是 $f(x)$ 而不是 $ f(x\Delta T)$ ？）

傅立叶正变换和逆变换得到的函数都是无限周期的，周期为 $M$。



### 2.2.2 二维DFT

略



### 2.2.3 频率域滤波器

过程：空间域 $=>$ 傅立叶变换转到频率域 $=>$ 在频率域使用模版处理振幅或者相位 $=>$ 傅立叶逆变换回到空间域

- 理想低/高通滤波器
- k阶布特沃斯低/高通滤波器
- 高斯低/高通滤波器
- 频率域拉普拉斯算子（需归一化）
- 同态滤波（未完全理解）
- 选择性滤波器：带通滤波器、陷波滤波器（未实现）



**代码实现：**

（1）：低通/高通滤波器

``` python
import cv2
import numpy as np
import matplotlib.pyplot as plt


def IPF(img, d0, flag):
    #  理想滤波器 ideal pass filter，d0 为滤波器半径
    # flag == 1 : low pass filter; flag == 0 : high pass filter
    m, n = img.shape
    ans = np.zeros(img.shape)

    for i in range(m):
        for j in range(n):
            if (i - m / 2)**2 + (j - n / 2)**2 < d0**2:
                ans[i][j] = 1
    if flag == 0:
        ans = 1 - ans

    return ans


def GPF(img, d0, flag):
    # 高斯滤波器
    m, n = img.shape
    d0 = d0**2
    ans = np.zeros(img.shape)

    for i in range(m):
        for j in range(n):
            d = (i - m / 2)**2 + (j - n / 2)**2
            if d < d0:
                ans[i][j] = np.exp(-d / (2 * d0))

    if flag == 0:
        ans = 1 - ans

    return ans


def BPF(img, do, flag, k):
    # k阶布特沃斯高通滤波器
    m, n = img.shape
    d0 = d0**2
    ans = np.zeros(img.shape)

    for i in range(m):
        for j in range(n):
            d = (i - m / 2)**2 + (j - n / 2)**2
            if d < d0:
                ans[i][j] = 1 / (1 + (d / d0)**k)

    if flag == 0:
        ans = 1 - ans

    return ans


# 高通滤波--提取轮廓
# 低通滤波--模糊化
img_man = cv2.imread('ch03_5.jpg', 0)  # 直接读为灰度图像
plt.subplot(131), plt.imshow(img_man, 'gray'), plt.title('before')
plt.xticks([]), plt.yticks([])


rows, cols = img_man.shape
mask1 = np.ones(img_man.shape, np.uint8)  # 高通
mask1[int(rows / 2) - 30: int(rows / 2) + 30,
      int(cols / 2) - 30:int(cols / 2) + 30] = 0

mask2 = np.zeros(img_man.shape, np.uint8)  # 低通
mask2[int(rows / 2) - 30:int(rows / 2) + 30,
      int(cols / 2) - 30:int(cols / 2) + 30] = 1


mask31 = np.ones(img_man.shape, np.uint8)
mask31[int(rows / 2) - 10:int(rows / 2) + 10,
       int(cols / 2) - 10:int(cols / 2) + 10] = 0
mask32 = np.zeros(img_man.shape, np.uint8)
mask32[int(rows / 2) - 80:int(rows / 2) + 80,
       int(cols / 2) - 80:int(cols / 2) + 80] = 1
mask3 = mask31 * mask32  # 带通

mask = IPF(img_man, 30, 1)

f1 = np.fft.fft2(img_man)
f1shift = np.fft.fftshift(f1)
f1shift = f1shift * mask
f2shift = np.fft.ifftshift(f1shift)
img_new = np.fft.ifft2(f2shift)
img_new = np.abs(img_new)
# 调整大小范围便于显示
# img_new = (img_new - np.amin(img_new)) / (np.amax(img_new) - np.amin(img_new))

plt.subplot(132), plt.imshow(mask, 'gray'), plt.title('mask')
plt.xticks([]), plt.yticks([])
plt.subplot(133), plt.imshow(img_new, 'gray'), plt.title('after')
plt.xticks([]), plt.yticks([])
plt.show()

```



（2）：频率域拉普拉斯滤波

``` python
def Laplace(shape):
    m, n = shape
    ans = np.zeros(shape)

    for i in range(m):
        for j in range(n):
            d = (i - m / 2)**2 + (j - n / 2)**2
            ans[i][j] = 1 + 4 * (np.pi**2) * d / (m * n)
            # 之前失败是由于没有处以mn
    return ans


def stdimg(img):
        # 灰度值归一化
    m, n = img.shape
    min_img = np.amin(img)
    max_img = np.amax(img)
    img = np.float64(img)
    for i in range(m):
        for j in range(n):
            img[i][j] = (img[i][j] - min_img) / (max_img - min_img)

    return img


img = cv2.imread('ch03_3.jpg', 0)
img = stdimg(img)
f = np.fft.fft2(img)
f = np.fft.fftshift(f)
mask = Laplace(img.shape)
f *= mask
img_back = np.fft.ifftshift(f)
img_back = np.fft.ifft2(img_back)
img_back = np.abs(img_back)
plt.subplot(131), plt.imshow(img, 'gray'), plt.title('before')
plt.xticks([]), plt.yticks([])
plt.subplot(132), plt.imshow(mask, 'gray'), plt.title('mask')
plt.xticks([]), plt.yticks([])
plt.subplot(133), plt.imshow(img_back, 'gray'), plt.title('after')
plt.xticks([]), plt.yticks([])

plt.show()

```



## 3 图像复原与重建

## 4 彩色图像处理

