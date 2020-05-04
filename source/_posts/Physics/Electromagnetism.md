---
title: Electromagnetism
date: 2020-02-18 13:32:41
tags:
categories:
- Physics
---

# 电动力学笔记

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
  \nabla\times(\nabla\times\vec A)=\nabla(\nabla\cdot \vec A)-\nabla^2 \vec A
  \notag
  $$
  





#### 3. 波常用

- $$
  \begin{align}
  \nabla e^{i\vec k\cdot \vec r}&=i\vec k e^{i\vec k\cdot \vec r}\\
  \nabla^2e^{i\vec k\cdot \vec r}&=\nabla\cdot(\nabla e^{i\vec k\cdot \vec r})\notag\\
  &=i(\nabla\cdot\vec k)e^{i\vec k\cdot \vec r}+i(\nabla e^{i\vec k\cdot\vec r})\cdot\vec k\notag\\
  &=-k^2 e^{i\vec k\cdot \vec r}
  \end{align}
  $$

- 平面波 $ \vec E=\vec E_0 e^{i\vec k\cdot\vec r}$
  $$
  \begin{align}
  \nabla\cdot\vec E&=i\vec k \cdot \vec E\\
  \nabla\times\vec E&=i\vec k\times\vec E\\
  \end{align}
  $$
  





### 多元积分

#### 1. 总：广义Stokes​定理

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
  



- $\displaystyle \frac{\vec e_r}{r^2}$
  $$
  \notag
  \nabla\cdot \frac{\vec e_r}{r^2}=0\\
  \nabla\frac{\vec e_r}{r^2}=\frac{\nabla \vec r r^3-(\nabla r^3)\vec r}{r^6}=\frac{\overleftrightarrow I-3\vec e_r\vec e_r}{r^3}
  $$
  

以上对 $\vec r-\vec r’$ 同样适用。



### 张量相关

$$
\begin{aligned}
&\iint \vec e_r d\Omega =0\\
&\iint \vec e_r\vec e_r d\Omega=\frac {4\pi}{3}\overleftrightarrow I
\end{aligned}
$$











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

### 原始形式

$$
\begin{aligned}
\nabla\cdot \vec E&=\frac{\rho}{\varepsilon_0}\\
\nabla\times \vec E&=-\frac{d\vec  B}{dt}\\
\nabla \cdot\vec  B&=0\\
\nabla\times\vec  B&=\mu_0 \vec j+\varepsilon_0\mu_0\frac{\partial \vec E}{\partial t}
\end{aligned}
$$



### 介质形式

$$
\begin{aligned}
\nabla\cdot \vec D&=\rho\\
\nabla\times \vec E&=-\frac{d \vec B}{dt}\\
\nabla \cdot \vec B&=0\\
\nabla\times \vec H&=\vec  j+\frac{\partial\vec  D}{\partial t}
\end{aligned}
$$

其中：
$$
\begin{aligned}
\vec D&=\varepsilon_0\vec E+\vec P\\
\vec H&=\frac{1}{\mu_0}\vec B-\vec M
\end{aligned}
$$
其中：

$\vec P=\rho_p\vec \ell$ 为极化强度，是单位体积内分子的总偶极矩。

$\vec M$ 为单位体积内的磁矩。



这一部分需要再细细整理。



### 边界条件

$$
\begin{aligned}
\vec D^{\perp }_1-\vec D_2^\perp&=\sigma_f\\
\vec E_1^{\parallel}-\vec E^{\parallel}_2&=0  \\ 
\vec H_1^{\parallel}-\vec H_2^{\parallel}&=\vec K_f\times\vec n\\
\vec B_1^\perp-\vec B_2^\perp&=0 

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



### 麦克斯韦应力张量

$$
\begin{aligned}
\vec f&=\rho \vec E+\rho \vec v\times\vec B=\rho\vec E+\vec j\times \vec B\\
&=\nabla\cdot \overleftrightarrow{\mathcal{T}}-\varepsilon_0\mu_0\frac{\partial \vec S}{\partial t}

\end{aligned}
$$

其中，麦克斯韦应力张量：
$$
\overleftrightarrow{\mathcal{T}}=\varepsilon_0\vec E\vec E+\frac{1}{\mu_0}\vec B\vec B-\frac{1}{2}\big(\varepsilon_0\vec E^2+\frac{1}{\mu_0}\vec B^2\big)\overleftrightarrow I
$$
分量形式为：
$$
T_{ij}=\varepsilon_0(E_iE_j-\frac 1 2 \delta_{ij}E^2)+\frac 1 \mu_0 (B_iB_j-\frac 1 2 \delta_{ij}B^2)
$$




空间 $V$ 内电荷所受合力为：
$$
\vec F=\int_V\vec f d\tau=\int_S\overleftrightarrow{\mathcal{T}}\cdot d\vec \sigma-\varepsilon_0\mu_o\frac{d}{dt}\int_V \vec S d\tau
$$




### 动量

$$
\begin{aligned}
&\vec f=\frac{d\vec p_{mech}}{dt}=-\frac{d}{dt}(\varepsilon_0\mu_0\vec S)+\nabla\cdot\overleftrightarrow {\mathcal{T}}\\
\iff &\frac{d}{dt}\bigg(\vec p_{mech}+\vec g\bigg)=-\nabla\cdot\overleftrightarrow{\Tau}
\end{aligned}
$$

其中 $\vec p_{mech}$ 为机械动量密度， $\vec g\equiv\vec p_{em}$ 为电磁动量密度，$\overleftrightarrow \Tau=-\overleftrightarrow{\mathcal{T}}$ 为动量流密度。



电磁场动量密度
$$
\vec g=\varepsilon_0\mu_0\vec S=\frac{1}{c^2}\vec S
$$
动量流密度
$$
\overleftrightarrow\Tau=\frac{1}{2}\big(\varepsilon_0\vec E^2+\frac{1}{\mu_0}\vec B^2\big)\overleftrightarrow I-\varepsilon_0\vec E\vec E-\frac{1}{\mu_0}\vec B\vec B
$$




### 角动量

电磁场角动量密度
$$
\vec \ell_{em}=\vec r\times\vec g=\varepsilon_0\big[\vec r\times\vec E\times \vec B\big]
$$


### 电磁辐射压强

$$
\mathcal{P}=\frac{\Delta F}{\Delta A}=\frac{g\Delta V}{\Delta t\Delta A}=\frac{g\Delta \ell}{\Delta t}=cg
$$

这是完全吸收时的辐射压强，其中 $c$ 为光速。

不完全吸收时, $\mathcal{P}=cg(1+r)$ , 其中 $r$ 为反射系数。







## 6 静电问题

### 电势

$$
\begin{aligned}
V(\vec r)&\equiv -\int _{\mathcal{O}}^ r\vec E\cdot d\vec \ell\\
&=\int_r^\infty \vec E\cdot d\vec \ell
\end{aligned}
$$



### 多极展开

#### 原理

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
&\nabla\nabla(\frac{1}{|\vec r-\vec r_0|})=-\frac{\overleftrightarrow I r^3- r^2 \vec e_r\vec r}{r^6}=\frac{3\vec e_r\vec e_r-\overleftrightarrow I}{|\vec r-\vec r_0|^3}

\end{aligned}
$$



- 常用展开：把 $\displaystyle \frac{1}{|\vec r- \vec r|}$ 在 $\vec r’=0$ 附近作泰勒展开 
  $$
  \frac{1}{|\vec r-\vec r'|}=\frac{1}{r}+\frac{\vec r'\cdot\vec e_r}{r^2}+\frac{(3\vec r'\vec r'-r'^2\overleftrightarrow I):\vec e_r\vec e_r}{2r^3}+\cdots
  \notag
  $$

- 更方便地展开：把 $\displaystyle \frac{1}{|\vec r- \vec r|}$ 展开成勒让德多项式 ( $r$ 很大时)
  $$
  \begin{aligned}
  \frac{1}{|\vec r-\vec r'|}&=\frac{1}{\sqrt{r^2+r'^2-2rr'\cos\theta'}}\\
  &=\sum_{n=0}^\infty \frac{(r')^n}{r^{n+1}}P_n(\cos\theta')\\
  &=\frac{1}{r}+\frac{r'}{r^2}\cos\theta'+\frac{r'^2}{r^3}[\frac{1}{2}(3\cos^2\theta'-1)]+\cdots\\
  &=\frac{1}{r}+\frac{\vec r'\cdot\vec e_r}{r^2}+\frac{(r')^2(3\cos^2\theta'-1)}{2r^3}+\cdots
  \end{aligned}
  $$





#### 静电场的多极展开

#### 	单极

$$
\varphi_1=\frac{1}{4\pi\epsilon_0}\frac{Q}{r}
\notag
$$



#### 	偶极

$$
\varphi_2=\frac{1}{4\pi\epsilon_0}\frac{\vec p\cdot \vec e_r}{r^2}
\notag
$$

- 电偶极矩 
  $$
  \vec p=\int_V\vec r\cdot\rho(\vec r) d\tau
  \notag
  $$
  $\vec r$ 为每个电荷的位置矢量



#### 	四极

$$
\varphi_3=\frac{1}{4\pi\epsilon_0}\frac{\overleftrightarrow{\mathcal{D}}\colon(3\vec e_r\vec e_r-\overleftrightarrow I)}{2r^3}=\frac{1}{4\pi\epsilon_0}\frac{\overleftrightarrow {D}\colon \vec e_r\vec e_r}{2r^3}
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





### 电偶极子在电场中的受力

#### 位能与受力

$$
\begin{aligned}
U&=-\vec p\cdot\vec E\\
\vec F&=-\nabla U=\nabla(\vec p\cdot \vec E)
\end{aligned}
$$

#### 力矩

$$
\vec \tau=\vec p\times \vec E\notag
$$





### 唯一性定理

- 若边界上的电势或者电势的法向变化率已知
- 除导体外， $V$ 内电荷分布一致，表面有已知的第一类或第二类边界条件。若导体表面电势已知
- 若导体所带的总电量已知

满足一点，则区域 $V$ 内的电势分布有唯一解。





### 电像法

对球类电场，可以添加镜像电荷使球面电势为 $0$, 若导体球带电荷 $Q$ ，再于球心放置一个电荷量为 $Q$ 的等效电荷。

球半径为 $R$ , 原电荷在距球心 $a$ 处，电荷量为 $q$ , 则镜像电荷放置到距球心 $\displaystyle\frac{R^2}{a}$ 处，电荷量为 $\displaystyle-\frac{R}{a} q$ .





### 格林函数法

- 格林函数 $G$ ：

$$
\Delta G=\delta^{(3)}(\vec x-\vec x')
\notag
$$



- 各种解：



- 应用：







## 7 静磁问题

### 电流

电流由库仑每秒来量度， $1A=1C/s$

- 线电流 : $\vec I=\lambda \vec v=I d\vec \ell $  

- 面电流密度 : $\displaystyle\vec K\equiv\frac{d\vec I}{dl_{\perp}}=\sigma\vec v$ （电流带带上的电流除以带宽度） $I=\displaystyle\int_\ell \vec K\cdot d\vec \ell$
- 体电流密度 : $\displaystyle\vec J\equiv\frac{d\vec I}{da_{\perp}}=\rho \vec v$ （垂直于电流方向上单位面积流过的电流） $I=\displaystyle\int_S \vec J\cdot d\vec \sigma$



注：
$$
\begin{aligned}
\vec jd\tau&=C\delta(r-a)\delta(\theta-\frac\pi 2)d\varphi \vec e_\varphi\\
Id\vec \ell&=Iad\varphi\vec e_\varphi\\
&=\int_{d\ell}\vec j(\vec r)d\tau=\vec e_\varphi\int _{d\varphi}C\delta(r-a)\delta(\theta-\frac\pi 2)r^2\sin\theta \, dr d\theta d \varphi\\
&=Ca^2d\varphi\vec e_\varphi\\
\implies C&=\frac{I}{a}\\
\therefore\int \vec j(\vec r)d\tau&=\int\vec e_\varphi \frac I a\delta(r-a)\delta(\theta-\frac\pi 2)r^2\sin\theta\, drd\theta d\varphi \\
&=I\int\vec e_\varphi a\,d\varphi=I\int d\vec \ell
\end{aligned}
$$
**相关公式**

- 表面电流密度 $\vec K=\vec M\cdot \hat n$
- 内部体电流密度 $\vec J=\nabla\times \vec M$

- 磁感应强度 $\vec B=\mu_0 \vec K$



###  受力

#### 一段载流导线

$$
\begin{aligned}
\vec F&=\int (\vec v\times \vec B)dq=\int (\vec v\times\vec B)\lambda d l=\int (\vec I\times \vec B)dl\\
&=I\int \vec d\ell\times\vec B
\end{aligned}
$$

#### 磁偶极子

$$
\begin{aligned}
U&=-\vec m\cdot \vec B\\
\vec F&=\nabla(\vec m\cdot \vec B)\\
\vec \tau&=\vec m\times\vec B
\end{aligned}
$$











### 源起

静磁场满足的微分方程：
$$
\begin{aligned}
&\nabla\cdot \vec B=0\\
& \nabla\times \vec B=\mu_0\vec j\\
&\nabla\cdot \vec j=0
\end{aligned}
$$

### 磁矢势

$\nabla\times\vec A=0$ 在库仑规范 $\nabla\cdot \vec A=0$ 下得到矢量泊松方程 $\nabla^2\vec A=-\mu_0\vec j$

磁库仑解为：
$$
\vec A=\frac{\mu_0}{4\pi}\int_全 \frac{\vec j(\vec r')}{|\vec r-\vec r'|}d\tau'
\notag
$$
具体：
$$
\begin{aligned}
\vec A&=\frac{\mu_0}{4\pi}\int_V \frac{\vec J(\vec r')}{|\vec r-\vec r'|}d\tau'（体电流产生的磁矢势）\\
&=\frac{\mu_0}{4\pi}\int_S \frac{\vec K(\vec r')}{|\vec r-\vec r'|}da'（面电流产生的磁矢势）\\
&=\frac{\mu_0}{4\pi}\int_l \frac{\vec I(\vec r')}{|\vec r-\vec r'|}dl'=\frac{\mu_0 I}{4\pi}\int_l \frac{1}{|\vec r-\vec r'|}d\vec \ell（线电流产生的磁矢势）
\end{aligned}
$$




由此可得到毕奥-萨伐尔定律：
$$
\begin{aligned}
\vec B&=\nabla\times \vec A=\frac{\mu_0}{4\pi}\int_全 \nabla\times\bigg(\frac{\vec j(\vec r')}{|\vec r-\vec r'|}\bigg)d\tau'\\
&=\frac{\mu_0}{4\pi}\vec e_k\int_全 \varepsilon_{ijk}\partial_i \bigg(\frac{\vec j_j(\vec r')}{|\vec r-\vec r'|}\bigg)d\tau' \\
&=\frac{\mu_0}{4\pi}\vec e_k\int_全\varepsilon_{ijk}\frac{-(x_i-x_i')}{|\vec r-\vec r'|^3}j_j(\vec r')d\tau'\\
&=\frac{\mu_0}{4\pi}\int _全 \vec j(\vec r')\times\frac{\vec r-\vec r'}{|\vec r-\vec r'|^3}d\tau'\\
&=\frac{\mu_0}{4\pi}\int_全 \frac{\vec j(\vec r')\times e(\vec r-\vec r')}{|\vec r-\vec r'|^2 }d\tau'\\
&=\frac{\mu_0}{4\pi}I\int_l \frac{\vec d\ell'\times e(\vec r-\vec r')}{|\vec r-\vec r'|^2}（线电流）\\
&=\frac{\mu_0}{4\pi}\int_S \frac{\vec K(\vec r')\times e(\vec r-\vec r')}{|\vec r-\vec r'|^2}da' （面电流）\\
&=\frac{\mu_0}{4\pi}\int_V \frac{\vec J(\vec r')\times e(\vec r-\vec r')}{|\vec r-\vec r'|^2 }d\tau'（体电流）
\end{aligned}
$$



一般地，磁矢势的方向和电流方向一致。

对称性好的情况下，已知磁感应强度利用磁通量求磁矢势（类似安培定理）：
$$
\begin{aligned}
\oint\vec A\cdot d\vec \ell=\int_S(\nabla\times\vec A) \cdot da=\int_S \vec B\cdot d\vec a=\Phi
\end{aligned}
$$





### 磁矢势多极展开

$$
\begin{aligned}
\vec A&=\frac{\mu_0}{4\pi}\int\frac{\vec j(\vec r')}{|\vec r-\vec r'|}d\tau'\\
&=\frac{\mu_0}{4\pi}\sum_{n=0}^\infty \frac{1}{r^{n+1}}\int\vec j(\vec r')\big[(r')^n P_n(\cos\theta')\big]d\tau'\\
&=\frac{\mu_0}{4\pi}
\int\vec j(\vec r')\big[\frac 1 r+\frac {r'\cos\theta'}{r^2}+\frac{r'^2(3\cos^2\theta'-1)}{2r^3}+\cdots\big]d\tau'\\
\\
\vec A_{偶极}&=\frac{\mu_0}{4\pi}\int\vec j(\vec r')\frac{\vec r'\cdot \vec e_r}{r^2}d\tau'\\
&\equiv\frac{\mu_0}{4\pi}\frac{\vec m \times\vec e_r}{r^2}\\
\\
\vec B_{偶极}&=\frac {\mu_0}{4\pi}\frac{1}{r^3}\left[3(\vec m\cdot\vec e_r)\vec e_r-\vec m\right]
\end{aligned}
$$



- 磁偶极矩 $\vec m$ :

$$
\begin{aligned}
\vec m&\equiv\frac 1 2\int\vec r'\times\vec j(\vec r')d\tau'
\end{aligned}
$$

​	   其中$\vec j$ 为电流密度。

- 环形电流圈（半径为 $a$ ）：
  $$
  \begin{aligned}
  \vec m&=\frac1 2 I\oint \vec r'\times d\vec \ell=\frac 1 2 Ia\cdot2\pi a\vec e_k=I\vec S\\
  m&=\frac {dq}{dt}S=\frac{q_e}{2\pi a/v}\pi a^2=\frac 1 2q_e v r
  \\
  \vec A_{偶}&=\frac{\mu_0 I}{4\pi}\frac{\vec S\times \vec e_r}{r^2}\\
  \vec B_{偶}&=\nabla\times\vec A_{偶}=\frac{\mu_0}{4\pi}\frac{\vec m}{r^3}\cdot (3\vec e_r\vec e_r-\overleftrightarrow I)\\
  &=\frac{\mu_0}{4\pi}\frac{1}{r^3}[3(\vec m\cdot \vec e_r)\vec e_r-\vec m]
  \end{aligned}
  $$

  对指向 $z$ 轴的 $\vec m $ : 
  $$
  \vec B_{偶}=\frac{\mu_0}{4\pi}\frac{m}{r^3}\left(2\cos\theta\vec e_r+\sin\theta\vec e_\theta\right)
  $$
  



### 常用磁场

长直导线
$$
\vec B=\frac{\mu_0 I}{4\pi d}\left(\sin\theta_1-\sin\theta_2\right)
$$






### 磁标势

已知磁化强度 $\vec M$, 以及静磁方程：
$$
\begin{aligned}
&\nabla\cdot\vec B=0\\
&\nabla\times\vec H=\vec j\\
&\vec B=\mu_0(\vec H+\vec M)
\end{aligned}
$$


对于没有传导电流的*单连通区域* $V$ :	$\nabla\times \vec H=0$

所以存在磁标势 $\varphi_m$ : $\vec H=-\nabla\varphi_m$

由静磁方程推出：$\nabla^2\varphi_m=\nabla\cdot \vec M$









## 8 电磁波的传播

### 能量

$$
\begin{aligned}
&u=\frac 1 2 \varepsilon E^2+\frac{1}{2\mu}B^2=\varepsilon E^2=\frac{1}{\mu}B^2\\
&\vec S=\frac{1}{\mu}\vec E\times\vec B=cu\hat k\\
&\vec g=\frac 1 {c^2}\vec S=\frac 1 c u\hat k
\end{aligned}
$$

周期平均值：
$$
\begin{aligned}
\langle fg\rangle&=\frac 1 2 Re(\widetilde f\widetilde g ^*)\\
\langle u\rangle&=\frac 1 2 \varepsilon E^2\\
\langle S\rangle&=c\langle u\rangle\\

\end{aligned}
$$
强度与辐射压强：
$$
\begin{aligned}
I&\triangleq \langle S\rangle\\
P&=c\bar g=\frac{\langle S \rangle}{c}=\frac{I}{c}
\end{aligned}
$$


### 偏振



### 在线性介质中的传播

由相位在边界上相等可以得到折射定律和反射定律，利用边界条件进一步分析可得到菲涅尔定律等。

#### 折射定律和反射定律的导出

$$
Ae^{i(\vec k_i\cdot \vec r-\omega t)}+Be^{i(\vec k_r\cdot \vec r-\omega t)}=Ce^{i(\vec k_t\cdot \vec r-\omega t)}\\

\implies\begin{cases}
\omega_i=\omega_r=\omega_t\equiv \omega=kc\\
\vec k_i\cdot \vec r=\vec k_r\cdot \vec r=\vec k_t\cdot \vec r\biggm |_{z=0}
\end{cases}\\
\begin{aligned}
&\implies k_{i_x}=k_{r_x}=k_{t_x}\\
&\implies k_i\sin\theta_i=k_r\sin\theta_r=k_t\sin\theta_t
\end{aligned}
$$

进而可以推出折射定律和反射定律。





#### 菲涅尔定律

不抄了，利用边界条件推导即可，没必要记。





#### 布儒斯特角

偏振方向平行界面入射的波以这角入射时反射波完全消失。
$$
\theta_B=\arctan \frac{n'}{n}
$$




### 在导电介质中的传播

#### 麦克斯韦方程

$$
\begin{aligned}
\nabla\cdot \vec E&=0\\
\nabla\cdot \vec B&=0\\
\nabla\times\vec E&=-\frac{\partial\vec B}{\partial t}\\
\nabla\times\vec B&=\mu\varepsilon \frac{\partial \vec E}{\partial t}+\mu\sigma\vec E
\end{aligned}
$$

良导体。差别在磁场的旋度中多了一项。



#### 平面波解

$$
\widetilde E(z,t)=\widetilde E_0e^{-\kappa z}e^{i(kz-\omega t)}\\
\widetilde B(z,t)=\widetilde B_0e^{-\kappa z}e^{i(kz-\omega t)}\\
\notag
$$

注意电场与磁场不再同相，振幅的倍数也不再是 $c$ :
$$
\begin{aligned}
&\widetilde B_0=\frac{\widetilde k}{\omega}\widetilde  E_0=\frac{Ke^{i\phi}}{\omega}\widetilde  E_0 \\
&\frac{B_0}{E_0}=\frac{K}{\omega}=\sqrt{\varepsilon\mu\sqrt{1+\left(\frac{\sigma}{\varepsilon\omega}\right)^2}}
\end{aligned}
$$

#### 折射定律和反射定律

仍然成立。







### 波导

#### 边界条件

$$
\begin{cases}
\vec E^{\parallel}=0\\
\vec B^\perp=0
\end{cases}
\notag
$$

磁场和电场不同的边界条件导致 $TE$ 和 $TM$ 波的不同。



#### 重要方程

由于导体的影响，波导内的波一般不再是横波。推导中引入了纵向分量:
$$
\widetilde E_0=E_x\hat x+E_y \hat y +E_z\hat z\\
\widetilde B_0=B_x\hat x+B_y \hat y +B_z\hat z
\notag
$$
代入麦克斯韦方程组可以写出各分量方程。

最后得到独立的 $E_z$ 和 $B_z$ 的方程：
$$
\left[\frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\left(\frac{\omega}{c}\right)^2-k^2\right]E_z=0\\
\left[\frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\left(\frac{\omega}{c}\right)^2-k^2\right]B_z=0
$$


#### 重要结论

中空波导中 $TEM$ 波不能发生。 



#### 矩形波导

##### $TE$ 波

$E_z=0$, 分离变量求解得：
$$
B_z=B_0\cos(\frac{m\pi}{a}x)\cos(\frac{n\pi}{b}y)
\notag
$$


##### $TM$ 波

$B_z=0$.
$$
E_z=E_0\sin(\frac{m\pi}{a}x)\sin(\frac{n\pi}{b}y)
\notag
$$


##### 相关物理量

$$
\begin{aligned}&k_x=\frac{m\pi}{a},k_y=\frac{n\pi}{b}\\&\omega_{mn}\equiv c\sqrt{k_x^2+k_y^2}=c\pi\sqrt{\left(\frac{m}{a}\right)^2+\left(\frac{n}{b}\right)^2}(\text{截断频率})\\&k=\sqrt{\left(\frac{\omega}{c}\right)^2-k_x^2-k_y^2}=\frac{1}{c}\sqrt{\omega^2-\omega_{mn}^2}\end{aligned}
$$



##### 波速与群速度

$$
\begin{aligned}&v=\frac \omega k=\frac{c}{\sqrt{1-(\omega/\omega_{mn})^2}}\\&v_g=\frac{1}{dk/d\omega}=c \sqrt{1-(\omega/\omega_{mn})^2}\end{aligned}
$$







## 9 电磁波的激发

### 麦克斯韦方程组的探讨

$$
\begin{align}
\nabla\cdot \vec E&=-\frac {\rho(\vec r,t)}{\varepsilon}\label{E-divergence}\\
\nabla\times\vec E&=-\frac{\partial \vec B}{\partial t}\label{E-curl}\\
\nabla\cdot\vec B&=0\label{B-divergence}\\
\nabla \times\vec B&=\mu\vec J+\varepsilon\mu\frac{\partial\vec E}{\partial t}\label{B-curl}
\end{align}
$$

$\vec J$ 是电流密度。

由标势和矢势可以确定电场和磁场：

由 $(\ref{B-divergence})$ 可得
$$
\vec B=\nabla\times\vec A\label{B}
$$
这将确定磁场。

由 $(\ref{E-curl})$ 可得
$$
\begin{align}
&\nabla\times\left (\vec E+\frac{\partial \vec A}{\partial t}\right)=0\notag \\
\implies &\vec E=-\nabla \varphi-\frac{\partial \vec A}{\partial t}\label{E}
\end{align}
$$
这将确定电场。



由 $(\ref{E-divergence})$ 和 $(\ref{B-curl})$ 可以确定电荷分布和电流分布：
$$
\begin{align}
-\frac{\rho} \varepsilon&=\nabla^2\varphi+\frac{\partial}{\partial t}(\nabla\cdot \vec A)\\
-\mu \vec J&=\nabla^2\vec A-\varepsilon\mu\frac{\partial^2 }{\partial t^2}\vec A-\nabla\left(\nabla\cdot \vec A+\varepsilon\mu \frac{\partial}{\partial t }\varphi \right)
\end{align}
$$


麦克斯韦方程组本来有六个变量 $E_x,E_y,E_z,B_x,B_y,B_z$ ，利用矢势和标势将其浓缩为四个变量 $A_x,A_y,A_z,V$ ，留下两个自由度可以用来做规范变换。



### 规范变换

#### 一般规范

$$
\begin{aligned}
&\varphi\mapsto  \varphi'=\varphi+\alpha(\vec r,t)\\
&\vec A\mapsto  \vec A'=\vec A+\vec \beta(\vec r,t)
\end{aligned}
$$

代入 $(\ref{B})$ $\vec B$ 应保持不变，得到 $\nabla\times\vec \beta=0$

再代入 $(\ref{E})$ $\vec E$ 也应保持不变，得到 $\nabla \alpha+\displaystyle\frac{\partial\vec \beta}{\partial t}=0$

$\implies$
$$
\begin{align}
&\varphi\mapsto  \varphi'=\varphi-\frac{\partial}{\partial t}\lambda \\
&\vec A\mapsto  \vec A'=\vec A+\nabla\lambda
\end{align}
$$


#### 库仑规范

选取 $\lambda$ 使
$$
\nabla\cdot \vec A=0\notag
$$


#### 洛伦兹规范

选取 $\lambda$ 使
$$
\nabla\cdot \vec A+\epsilon\mu\frac{\partial}{\partial t}\varphi=0
$$





### 推迟势

$$
\begin{align}
\varphi&=\frac{1}{4\pi\varepsilon_0}\int \frac{\rho(\vec r',t_r)}{|\vec r-\vec r'| }d\tau'\\
\vec A&=\frac {\mu_0}{4\pi}\int \frac{\vec J(\vec r',t_r)}{|\vec r-\vec r'|}d\tau'\\
t_r&=t-\frac{|\vec r-\vec r'|}{c}
\end{align}
$$

非静止状态下，信息不是源现在的状态，而是较早时间 $t_r$ 时信息离开当时的源时的状态。



**证明**：

洛伦兹规范下，得到（真空中）
$$
\begin{cases}
\displaystyle
\nabla^2 \vec A-\frac 1 {c^2}\frac {\partial^2}{\partial t^2}\vec A=-\mu_0\vec J\\
\displaystyle
\nabla^2 \varphi-\frac 1 {c^2}\frac{\partial^2}{\partial t^2}\varphi=-\frac{\rho}{\varepsilon_0}
\end{cases}
\notag
$$
考虑
$$
\nabla^2 \psi-\frac 1 {c^2}\frac{\partial^2}{\partial t^2}\psi=-4\pi f(\vec r,t)
\notag
$$
将 $f$ 写成点源形式 
$$
f(\vec r,t)=\int f(\vec r',t)\delta(\vec r-\vec r')d\tau'
\notag
$$
将 $\psi$ 也写成如此形式
$$
\psi=\int G(\vec r-\vec r',t)d\tau'
\notag
$$
可以得到
$$
\nabla^2 G-\frac 1 {c^2}\frac{\partial^2}{\partial t^2}G=-4\pi f(\vec r',t)\delta(\vec r-\vec r')
\notag
$$
可以固定这时的 $\vec r’$ 为源点，利用球坐标拉普拉斯算子得到
$$
\frac 1{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}G\right)-\frac 1 {c^2}\frac{\partial^2}{\partial t^2}G=0\qquad(\vec r\neq \vec 0)
\notag
$$
令 $R(\vec r,t)=r G(\vec r,t)$, 得到
$$
\left(\frac{\partial}{\partial r}-\frac 1 c \frac{\partial}{\partial t}\right)\left(\frac{\partial}{\partial r}+\frac 1 c \frac{\partial}{\partial t}\right)R=0
\notag
$$
引入光锥坐标 
$$
\begin{align}
u=r-ct\\
v=r+ct
\end{align}
$$
可得 
$$
\begin{aligned}
&4\frac{\partial^2}{\partial u \partial v}R=0\\
\implies\quad &R(u,v)=g_1(k_1u)+g_2(k_2 v)
\end{aligned}
$$
取 $\displaystyle k_1=-\frac{1}{c},k_2=\frac 1 c$ ，并舍去超前时间，最终得到
$$
G=\frac 1 r g_1(t-\frac r c)\notag
$$


$\vec r\to \vec 0$ 时，对时间的偏导相对梯度都可以略去，有
$$
\begin{aligned}
\nabla^2 G(\vec r,t)&=-4\pi f(\vec 0,t)\delta(\vec r)\\
\implies \lim_{\vec r\to\vec 0} G&=\frac{f(\vec 0,t) }r
\end{aligned}
$$
对比非零处可以得到
$$
g_1(t-\frac r c)=f(\vec 0,t-\frac r c)\notag
$$

$$
\begin{aligned}
\therefore G(\vec r,t)&=\frac{f(0,t-\displaystyle \frac r c)}{r}& \vec r'=\vec 0\\
\implies  G(\vec r-\vec r',t)&=\frac{f(0,t-\displaystyle \frac {|\vec r -\vec r'|} c)}{r}& \vec r'\neq\vec 0\\
\psi(\vec r,t)&=\int G(\vec r-\vec r',t)d\tau'

\end{aligned}
$$



### 李纳-维谢尔势

特定轨迹 $\vec w(t)$ 的运动点电荷产生的势（推迟势）。
$$
\begin{align}
\phi(\vec r,t)&=\frac{1}{4\pi\varepsilon_0}\frac{q}{|\vec r-\vec w(t_r)|}\cdot \frac{1}{\displaystyle 1-\frac{\vec v(t_r)}{c}\cdot\frac{\vec r-\vec w(t_r)}{|\vec r-\vec w(t_r)|}}\\
&=\frac{1}{4\pi\varepsilon_0}\frac{q}{|\vec R|}\cdot \frac{1}{\displaystyle1-\frac{\vec v(t_r)}{c}\cdot \hat R}
\\

\vec A(\vec r,t)&=\frac{\vec v(t_r)}{c^2}\varphi(\vec r,t)
\end{align}
$$


注意这里面最终的时间都是推迟时间。

其中，有一些重要的量和关系经常用到：
$$
\begin{align}
\vec R&=\vec r-\vec w(t_r)\\
t_r&=t-\frac{|\vec r-\vec w(t_r)|}{c}=t-\frac{|\vec R|}{c}\\
\vec v(t)&=\vec w'(t)=\frac{d}{dt}\vec w(t)\\
\vec v(t_r)&=\vec w '(t_r)=\frac{d}{d t_r}\vec w(t_r)\\(&=\frac {d}{dt}\vec w(t)\biggm|_{t=t_r}=\frac {d}{d t_r}\vec w(t)\cdot\frac{d t_r}{dt})\notag\\

\end{align}
$$


比较神奇的是，因子 $\displaystyle\frac{1}{\displaystyle 1-\frac{\vec v(t_r)}{c}\cdot \hat R}$  恰好是 推迟时间对时间的导数：
$$
\begin{align}
&c(t-t_r)= |\vec R|\\
\implies &c(1-\partial_t t_r)=\partial_t R=\partial_{t_r}R\cdot \partial_t t_r\notag\\
\implies &\partial_t t_r=\frac{1}{1-\displaystyle\frac 1 c\partial_{t_r}R}\notag\\
\notag \\
\because\quad \partial_{t_r}R&\overset{技巧}{=}\frac{\partial\sqrt{\vec R\cdot \vec R}}{\partial t_r}\notag \\&=\frac{\vec R}{R}\frac{\partial\vec R}{\partial t_r}\notag \\&=\vec w'(t_r)\cdot \hat {R}=\vec v\cdot \hat{R}\notag\\
\therefore\quad \partial_t t_r&=\displaystyle\frac{1}{\displaystyle 1-\frac{\vec v(t_r)}{c}\cdot \hat R}
\end{align}
$$



### 运动电荷的场

#### 一般运动电荷的场

艰难链式法则求导。
$$
\begin{align}
\vec E&=\frac q {4\pi\varepsilon_0}\frac{R}{(\vec R\cdot\vec u)^3}\left[(c^2-v^2)\vec u+\vec R\times (\vec u\times \vec a)\right]\\
\vec B&=\frac 1 c \hat R\times\vec E\\ \notag \\

t_r&=t-\frac{R}{c}\quad (or: c(t-t_r)=R)\label{t_r}\\

\vec R&=\vec r-\vec w(t_r),\label{r-w(t_r)}\\ 
\vec u&=c\hat R-\vec v,\\
\vec v&=\vec v(t_r)=\partial_{t_r}w(t_r),=w'(t_r)\notag
\\ \vec a&=w''(t_r)\notag
\end{align}
$$
其中 ，$\vec E$ 的第一项为广义库仑场, 第二项为辐射场。由 $(\ref{t_r})$ 和 $(\ref{r-w(t_r)})$ 可以解出 $t_r$ 。



#### 匀速运动电荷的场

$\vec a=0,\vec w(t)=\vec v t$。
$$
\begin{align}
\vec E(\vec r,t)&=\frac{q}{4\pi\varepsilon_0}\frac{1-v^2/c^2}{\left(1-v^2\sin^2\theta/c^2\right)^{\frac 3 2}}\frac{\vec r-\vec v t}{|\vec r -\vec v t|^3}\\
\vec B&=\frac 1 c \hat R\times \vec E=\frac 1 {c^2}(\vec v\times \vec E)
\end{align}
$$


<img src="https://tva1.sinaimg.cn/large/007S8ZIlly1gebpwaba5qj30wa0rsjsw.jpg" style="zoom:25%;" />

运动垂直方向上：
$$
\vec E=\frac{q}{4\pi\varepsilon_0}\frac{1}{\rho^2}\frac{1}{\sqrt{1-v^2/c^2}}\vec e_\rho
$$
运动水平方向上：
$$
\vec E=\frac{1}{4\pi\varepsilon_0}\frac 1 {\rho^2}\cdot(1-v^2/c^2)\vec e_\rho
$$







## 10 电磁辐射

### 偶极辐射

#### 电偶极子辐射

在 $d\ll \lambda\ll r$ 的近似下展开。
$$
\begin{align}
q&=q_0\cos \omega t\notag \\
I&=\frac{dq}{dt}\vec e_z=-q_0\omega\sin\omega t\vec e_z\notag\\
V&=\frac{1}{4\pi\varepsilon_0}\left(\frac{q_0\cos[\omega(t-\vec r_{+}/c)]}{\vec r_+}-\frac{q_0\cos[\omega(t-\vec r_{-}/c)]}{\vec r_-}\right)\notag \\
&=-\frac{p_0\omega}{4\pi\varepsilon_0 c}\left(\frac{\cos\theta}{r}\right)\sin[\omega(t-r/c)]\\
\vec A&=\frac{\mu_0}{4\pi}\int_{-d/2}^{d/2} \frac{\vec I}{|\vec r-\vec z'|}dz'\notag
\\&=-\frac{\mu_0 p_0\omega}{4\pi r}\sin[\omega(t-r/c)]\vec e_z\\
\notag \\
\vec E&=-\nabla V-\partial_t\vec A\notag \\
&=-\frac{\mu_0p_0\omega^2}{4\pi}\left(\frac{\sin\theta}{r}\right)\cos[\omega(t-r/c)]\vec e_\theta\\
\vec B&=\nabla\times\vec A\notag \\
&=-\frac{\mu_0p_0\omega^2}{4\pi c}\left(\frac{\sin\theta}{r}\right)\cos[\omega(t-r/c)]\vec e_\phi\\
&=\frac 1 c \hat r\times \vec E\\
\notag \\
(辐射功率)\quad P&=\int \langle \vec S\rangle\cdot d\vec \sigma=\frac{\mu_0p_0^2\omega^4}{12\pi c}



\end{align}
$$






## 习题

### 高斯定律

Three isolated infinite metal (i.e. conducting) slabs have their normals along the *z* axis, so the slabs are parallel to each other. The top slab has total charge *Q*, while the bottom slab has total charge *q*. Find the charge on the top surfaces of each slab and on the bottom surfaces of each slab. ([Solusion](chrome-extension://ohfgljdgelakfkefopgklcohadegdpjf/https://web.pa.msu.edu/people/duxbury/courses/phy481/Fall2009/MidtermIBSolutions-2009.pdf))



