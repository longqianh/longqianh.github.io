---
title: 电动力学笔记
date: 2020-02-18 13:32:41
tags:
categories:
- Physics
- Electromagnetism
---

# 电动力学整理

## 0 麦克斯韦方程和规范理论概述起源（杨振宁）

- Electrotonic state, Faraday	
  $$
  H=\nabla \times A
  $$

- Maxwell
  $$
  Light=EM\ waves
  $$
  
- Maxwell : A Dynamical Theory of the Electromagnetic Field
  $$
  energy\;\ density=\frac{1}{8\pi ^2}(E^2+H^2)
  $$
  
- Dirac‘s sea

- Renormalization
  $$
  \alpha=(g-2)/2
  $$
  
- gauge theory 规范理论, non-Abelian gauge theory, 重整化群
- Symmetry breaking, Standard Mode 



**“妙的地方”**

$ \\ $ <!--more-->



## 1 矢量分析整理

### 符号约定

- Kronecker
  $$
  \delta_{ij}=\begin{cases}1\quad i=j,\\0 \quad i\neq j.\end{cases}
  \notag
  $$

- Levi-Civita

$$
\varepsilon_{ijk}=\begin{cases}1\quad (ijk)偶排列,\\ -1 \quad (ijk)奇排列, \\
0 \quad 下标中有两个相等.\end{cases}
\notag
$$

- $$
  \begin{aligned}
  &\varepsilon_{ijk}\varepsilon_{lmn}=\left|\begin{array}{cccc} 
      \delta_{il} & \delta_{im} &  \delta_{in}\\ 
       \delta_{jl}& \delta_{jm}& \delta_{jn}\\ 
      \delta_{kl}& \delta_{km}& \delta_{kn}
  \end{array}\right|\\
  &\varepsilon_{ijk}\varepsilon_{lmk}=\delta_{il}-\delta_{jm}
  \end{aligned}
  $$
  
  
  
- Einstein 求和约定
  $$
  A_i\vec e_i\equiv \sum_{i=1}^n A_i\vec e_i=\vec A\notag
  $$



### 点乘和叉乘

$$
\begin{aligned}
&\vec A\times \vec B=A_iB_j\varepsilon_{ijk}\vec e_k=
\left|\begin{array}{cccc} 
    \vec e_x & \vec e_y & \vec e_z \\ 
    B_x & B_y & B_z\\ 
    C_x & C_y & C_z 
\end{array}\right|\\
&\vec A\cdot (\vec B\times\vec C)=\vec B\cdot (\vec C\times \vec A)=\vec C\cdot (\vec A\times \vec B)=
\left|\begin{array}{cccc} 
    A_x & A_y & A_z \\ 
    B_x & B_y & B_z\\ 
    C_x & C_y & C_z 
\end{array}\right| \\
& \vec A\times (\vec B\times\vec C)=(\vec A\cdot \vec C)\vec B-(\vec A\cdot \vec B)\vec C\\
& (\vec A\times \vec B)\times \vec C=(\vec A\cdot \vec C)\vec B-(\vec B\cdot\vec C)\vec A
\end{aligned}
$$



### 多元微分

#### 1. 理解

（1）多元标量函数求导：梯度

（2）矢量函数求导可以看成有两种：散度、旋度

（3）标量函数可以求梯度，但无法求散度和旋度

（4）矢量函数可以求散度和旋度，但无法求梯度



#### 2. 积规则

#### （1）梯度

- 乘积
  $$
  \nabla(fg)=f\nabla g+g\nabla f
  \notag
  $$

- 

$$
\nabla(\frac{f}{g})=\frac{g\nabla f-f\nabla g}{g^2}\notag
$$

- 复合

$$
\nabla [f(g)]=\nabla f\odot \nabla g
\notag
$$



- 点乘

$$
\nabla(\vec A\cdot \vec B)=\vec A\times(\nabla \times\vec B)+\vec B\times(\nabla\times\vec A)+(\vec A \cdot \nabla)\vec B+(\vec B\cdot \nabla )\vec A
\notag
$$

​	

注意梯度算符同时具有矢量性和微分性。



#### （2）散度

- $$
  \nabla \cdot (f\vec A)=(\nabla f)\cdot\vec A+f (\nabla \cdot \vec A)
  \notag
  $$

  

- $$
  \nabla\cdot(\frac{\vec A}{g})=\frac{(\nabla\cdot \vec A)g-(\nabla g)\cdot \vec A}{g^2}
  \notag
  $$

  

- $$
  \nabla \cdot (\vec A\times \vec B)=\vec B\cdot (\nabla \times\vec A)-\vec A\cdot (\nabla\times \vec B)\notag
  $$

  

#### （3）旋度

- $$
  \nabla\times(f\vec A)=(\nabla f)\times \vec A+f(\nabla\times \vec A)
  \notag
  $$

  

- $$
  \nabla\times(\frac{\vec A}{g})=\frac{(\nabla\times\vec A)g-(\nabla g)\times\vec A}{g^2}
  \notag
  $$



- $$
  \nabla\times(\vec A\times \vec B)=(\nabla\cdot \vec B)\vec A-(\nabla\cdot \vec A)\vec B+(\vec B\cdot \nabla)\vec A-(\vec A\cdot \nabla)\vec B
  \notag
  $$

  



#### （4）二阶微分

- Laplace
  $$
  \Delta T\triangleq\nabla\cdot \nabla T
  \notag
  $$

- 梯度的旋度为零
  $$
  \nabla\times(\nabla T)=0
  \notag
  $$
  
- 旋度的旋度
  $$
  \nabla\times\nabla\times\vec A=\nabla(\nabla\cdot \vec A)-\nabla^2 \vec A
  \notag
  $$
  







### 多元积分

#### 1. 总：广义 $Stokes$ 定理

$$
\int_V dw=\int_{\partial V}w
$$



#### 2. 理解

（1）两边的矢量性/标量性要一致

（2）分两类，一类是两边都是标量，一类是两边都是矢量



#### 3. 积分公式

可以通过同时点乘或叉乘常矢量 $\vec c$ ，然后使用积规则（类似分布积分）证明出。

####  （1）梯度

- 梯度的线积分不依赖于路径

$$
\int _a^b (\nabla T)\cdot d\vec \ell=T(b)-T(a)
\notag
$$



- $$
  \int_V (\nabla T)d\tau=\int_{\partial V}Td\vec\sigma
  \notag
  $$



#### （2）散度

- $$
  (Gauss)\qquad \int_V(\nabla\cdot \vec A) d\tau=\int_{\partial V}\vec A\cdot d\vec \sigma
  \notag
  $$

  

- $$
  \int_S (\nabla\cdot \vec A)d\vec\sigma=\int_{\partial S}\vec A\times d\vec \ell
  \notag
  $$

  

#### （3）旋度

- $$
  \int _V(\nabla \times \vec A)d\tau=\int_{\partial V} d\vec \sigma\times\vec A=-\int_{\partial V}\vec A\times d\vec \sigma
  \notag
  $$

  

​	注意 $\vec A$ 始终要在叉乘符号的右边



- $$
  (Stokes)\qquad \int_S(\nabla\times\vec A)\cdot d\vec\sigma=\int_{\partial S}\vec A\cdot d\vec \ell
  \notag
  $$

  

- $$
  \int_S (\nabla T)\times d\vec \sigma=-\int_{\partial S}Td\vec \ell
  \notag
  $$



​	注意左边是旋度积分而且两边都是矢量性的，如果右边积分变量写正常，多个负号







### 狄拉克函数

- 考虑一个正交的曲线坐标系，它由三个参数 $u,v,w$ 来确定（$u=const,v=const,w=const$ 的面互相垂直）。沿着三个相互垂直的方向的无穷小线元的长度分别是 $du/U,dv/V,dw/W$ 。则：

$$
\delta^{(3)}(\vec x-\vec x')=\delta(u-u')\delta(v-v')\delta(w-w')UVW
$$



- $$
  -\nabla^2\frac{1}{|\vec r-\vec r'|^2}=\nabla \cdot (\frac{\vec r - \vec r'}{|\vec r-\vec r'|^3})=4\pi\delta^3(\vec r-\vec r')
  \notag
  $$

  










### 位置矢量 $\vec r$ 相关

- 定义

$$
\vec r=x\vec e_x+y\vec e_y+z\vec e_z\\
r=\sqrt{x^2+y^2+z^2}
\notag
$$

- $r$
  $$
  \begin{aligned}
  \nabla r=\frac{\vec r}{|r|}=\vec e_r
  \end{aligned}
  $$

- $\vec r$

$$
\begin{aligned}
\nabla\cdot \vec r=3\\
\nabla\times \vec r=0
\end{aligned}
$$

- $\displaystyle\frac{1}{r}$

$$
\nabla(\frac{1}{r})=-\frac{\nabla r}{r^2}=-\frac{\vec e_r}{r^2}=-\frac{\vec r}{r^3}
\notag
$$

$$
\nabla^2 \frac{1}{r}=-4\pi\delta(r)
\notag
$$



- $\vec e_r$
  $$
  \nabla \cdot \vec e_r=\frac{2}{r}
  \notag
  $$
  

以上对 $\vec r-\vec r’$ 同样适用。



## 2 电磁学公式

### 高斯定律

$$
\nabla\cdot \vec E(\vec r)=\frac{\rho(r)}{\varepsilon_0}
$$



### 电流密度

$$
\vec j=\rho_{+}\vec v_++\rho_-\vec v_-
$$



### 电荷的连续性方程

$$
\frac{\partial\rho}{\partial t}+\nabla\cdot \vec j=0
$$



### 毕奥—萨伐尔定律

$$
\begin{aligned}
&d\vec B(\vec r)=\frac{\mu_0}{4\pi}\frac{\vec j(\vec r')\times \vec e(\vec r-\vec r')}{|\vec r-\vec r'|^2}d\tau'\\
&\vec B(\vec r)=\frac{\mu_0}{4\pi}\int_V\frac{\vec j(\vec r')\times \vec e(\vec r-\vec r')}{|\vec r-\vec r'|^2}d\tau'=\nabla\times\vec A\\
&\vec A=\frac{\mu_0}{4\pi}\int_V\frac{j(\vec r')}{|\vec r -\vec r'|}d\tau'
\end{aligned}
$$



### 安培定律

$$
\oint \vec B\cdot d\vec \ell=\mu_0\sum I
$$



### 磁场对电流的力密度

施加在单位体积内在流体上的力。
$$
f=j\times B
$$


### 法拉第电磁感应定律

$$
\mathcal{E}=-\frac{d\Phi}{dt}=\oint \vec E\cdot d\vec \ell ,\quad \Phi=\int_S\vec B\cdot d\vec \sigma
$$





## 3 麦克斯韦方程组

$$
\begin{aligned}
\nabla\cdot E&=\frac{\rho}{\varepsilon_0}\\
\nabla\times E&=-\frac{d B}{dt}\\
\nabla \cdot B&=0\\
\nabla\times B&=\mu_0 j+\varepsilon_0\mu_0\frac{\partial E}{\partial t}
\end{aligned}
$$





## 4 电磁场能动量

### 能量

能流密度：
$$
\vec S=\frac{1}{\mu_0}\vec E\times \vec B\\
$$
电磁场能量密度：
$$
w=\frac{1}{2}(\varepsilon_0 E^2+\frac{1}{\mu_0}B^2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             )
$$


### 动量

电磁场动量密度



动量流密度



### 角动量

电磁场角动量密度



### 麦克斯韦应力张量



### 辐射压强





## 5 电场的多极展开

### 原理

- 泰勒定理

  若函数 $f$ 在点 $P_0(x_0,y_0)$ 点邻域 $U(P_0)$ 上有直到 $n+1$ 阶的连续偏导数，则对 $U({_0})$ 内任一点 $(x_0+h,y_0+k)$ ，存在相应的 $\theta\in(0,1)$ ，使得
  $$
  \begin{aligned}
  f(x_0+h,y_0+k)=&f(x_0,y_0)+\bigg(h\frac{\partial}{\partial x}+k\frac{\partial}{\partial y}\bigg)f(x_0,y_0)\\
  &+\frac{1}{2!}\bigg(h\frac{\partial}{\partial x}+k\frac{\partial}{\partial y}\bigg)^2f(x_0,y_0)+\cdots\\
  &+\frac{1}{n!}\bigg(h\frac{\partial}{\partial x}+k\frac{\partial}{\partial y}\bigg)^n f(x_0,y_0)\\
  &+\frac{1}{(n+1)!}\bigg(h\frac{\partial}{\partial x}+k\frac{\partial}{\partial y}\bigg)^{n+1}f(x_0+\theta h,y_0+\theta k)
  \end{aligned}
  $$
  

- 场量的泰勒展开：对 $f(\vec x-\vec x’)$ 在 $\vec x’=0$ 附近展开

$$
\begin{aligned}
f(\vec x-\vec x')&=f(\vec x)-\sum_{i=1}^3 x_i\frac{\partial f}{\partial x_i}+\frac{1}{2!}\sum_{i,j}x_i x_j \frac{\partial^2 f}{\partial x_i\partial x_j}+\cdots\\
&=f(\vec x)-\vec x'\cdot \nabla f(\vec x)+\frac{1}{2}\vec x'\vec x'\colon \nabla\nabla f(\vec x)+\cdots
\end{aligned}
$$


$$
\begin{aligned}
&\nabla(\frac{1}{|\vec r-\vec r_0|})=-\frac{\vec e_r}{|\vec r-\vec r_0|^2}=-\frac{\vec r}{r^3} \\
&\nabla\nabla(\frac{1}{|\vec r-\vec r_0|})=-\frac{\overleftrightarrow I r^3-e r^2 \vec e_r\vec r}{r^6}=\frac{3\vec e_r\vec e_r-\overleftrightarrow I}{|\vec r-\vec r_0|^3}

\end{aligned}
$$


### 单极

$$
\varphi_1=\frac{1}{4\pi\epsilon_0}\frac{Q}{r}
\notag
$$



### 偶极

$$
\varphi_2=\frac{1}{4\pi\epsilon_0}\frac{\vec p\cdot \vec e_r}{r^2}
\notag
$$

- 偶极矩 
  $$
  \vec p=\int_V\vec r\cdot\rho(\vec r) d\tau
  \notag
  $$
  $\vec r$ 为偶极子的位置矢量



### 四极

$$
\varphi_3=\frac{1}{4\pi\epsilon_0}\frac{\overleftrightarrow{\mathcal{D}}\colon(3\vec e_r\vec e_r-\overleftrightarrow I)}{2r^3}=\frac{1}{4\pi\epsilon_0}\frac{\overleftrightarrow {D}\colon \vec e_r\vec e_r}{2r^3}
\notag
$$

- 二级矩
  $$
  \overleftrightarrow{\mathcal{D}}=\sum_n q_n\vec r_n\vec r_n\\
  \overleftrightarrow{\mathcal{D}}=\int_V \rho(\vec r)\cdot \vec r\vec r d\tau\\
  \notag
  $$



- 四极矩

$$
\overleftrightarrow D=3\overleftrightarrow{\mathcal{D}}-tr(\overleftrightarrow{\mathcal{D}})\overleftrightarrow{I}
\notag
$$



- 四极矩的性质

  - 对称性：$D_{ij}=D_{ji}$
  - 无迹性： $tr(\overleftrightarrow D)=0$

  