---
title: Linear Algebra
date: 2020-02-28 09:44:42
tags:
categories:
- Mathematics
- LA
---

# 线性代数学习笔记

不加入例题

主要是例题中用到的基本性质和定理的证明

## 1. 线性空间

### 基的可扩充性

$V^n$ 的任意一组线性无关的向量都可扩充为一组基。

证明：

​		对于一个有 $m$ 个向量的线性无关组，若 $m<n$ ，则 $V$ 中肯定**存在向量 $x$ 不能被他们表示**。

​		可以证明 $x$ 与他们线性无关，把 $x$ 添进去，构成新的线性无关组。

​		这样一直添，最后可以扩充为一组基。



### 维数公式

$$
dim\ W_1+dim\ W_2=dim(W_1+W_2)+dim(W_1\cap W_2)
\notag
$$

证明：

​		取 $W_1\cap W_2$ 的一组基，分别扩充为 $W_1$ 和 $W_2$ 的基，

​		则它们组合起来组成的向量组可以张成 $W_1+W_2$ 。

​		接下来只需证明它们线性无关。
$$
W_1\cap W_2=\mathcal{L}(\alpha_1,\cdots,\alpha_r)\\
W_1=\mathcal{L}(\alpha_1,
\cdots,\alpha_r,\beta_1,\cdots,\beta_s)\\
W_2=\mathcal{L}(\alpha_1,\cdots,\alpha_r,\gamma_1,\cdots,\gamma_t)\\
=>W_1+W_2=\mathcal{L}(\alpha_1,\cdots,\alpha_r,\beta_1,\cdots,\beta_s,\gamma_1,\cdots,\gamma_t)
\notag
$$


​		按线性无关定义写出式子，把 $\gamma$ 项移到等式右边，

​		利用 $W_1\cap W_2$ 可以把两边都表示成 $\alpha$ 项的线性组合，

​		依次利用移项后是 $W_2$ 和 $ W_1 $ 的基，最后得到全是 $0$。





### 直和

设 $U_1,\cdots,U_m$ 都是 $V$ 的子空间，则:

- （定义）$U_1+\cdots+U_m$ 是直和，如果 $U_1+\cdots+U_m$ 中的每个元素都可以唯一的表示成 $u_1+\cdots+u_m$ ，其中每个 $u_j\in U_j$。
- $\iff$ $0$ 唯一分解成 $0+\cdots+0$

- 对于两个子空间的直和，$U+W=U\oplus W\iff U\cap W=\{0\}$





## 2. 线性映射

### 线性映射的维数定理

$T:V\to W'$,  $dim\ N(T)+dim\ R(T)=dim\ V$

即：$dim\ Ker(T)+dim\ Im(T)=dim\ V$

证明1：

​		去证 **$\overline T:\overline V\to W$, $\overline v\mapsto T(v)$ 是线性映射且为双射**, $\overline T$ 是由 $T$ 诱导出来的线性映射。

​		其中 $W=Im(T)$, $\overline V=V/ker(T)$。 从而 $V/ker(T)\cong Im(T)$。

  1.   $\overline T$ 的**定义是合理的**：$\overline T(\overline v)=T(v), \forall k\in Ker(T),\overline v=v+k$

       这需要证明对 $\overline v=v+k_1$ 和  $\overline {v+k_2}=\overline v=v+k_2$, $\overline T(\overline {v+k_1})=\overline T(\overline {v+k_2})=T(v)$. 

       即 $\overline T(\overline v)=T(v)$ 的成立不依赖于 $v’\in \overline v=v+Ker(T) $ 的选取

       这是由于 $\forall k\in Ker(T),\overline T(\overline {v+k})=T(v+k)=T(v)+T(k)=T(v)$

  2.   $\overline T$ **是线性映射**：

       - 加法：

         $\overline T(\overline {v_1+v_2})=T(v_1+v_2)=T(v_1)+T(v_2)=\overline T(\overline v_1)+\overline T(\overline v_2)$

       - 数乘：

         $\overline T(\lambda \overline {v})=\overline T(\overline {\lambda v})=T(\lambda v)=\lambda T(v)=\lambda\overline T(\overline v)$

3. $\overline T$ **是双射**：

      - 单射：

        $\overline T(\overline v)=0=>T(v)=0=>v\in Ker(T)=>\overline v=0\\ =>Ker(\overline T)=0$

      - 满射：

        $\forall w\in W=Im(T),\exist v\in V,s.t.\quad T(v)=w\\ =>\exist\overline v, \overline T(\overline v)=T(v)=w$



证明2:

​		取 $ N(T)$ 的一组基 $(v_1,\cdots,v_s)$ ，将其扩充为 $V$ 的一组基 $(v_1,\cdots,v_s,v_{s+1},\cdots,v_n)$

​		则 $R(T)=\mathcal{L}\big[T(v_1),\cdots,T(v_n)\big]=\mathcal{L}\big[T(v_{s+1}),\cdots,T(v_n)\big]$

​		因此 $T(v_{s+1}),\cdots,T(v_{n})$ 可张成 $R(T)$ ，只需证明它们线性无关。

​		如果 $a_1 T(v_{s+1})+\cdots +a_{n-s}T(v_{n})=0$

​		则 $T(a_1v_{s+1}+\cdots+a_{n-s}v_n)=0$

​		$=> a_1v_{s+1}+\cdots+a_{n-s}v_n\in N(T)$

​		故 $\exist v_1,\cdots,v_s, \quad a_1v_{s+1}+\cdots+a_{n-s}v_n=b_1v_1+\cdots b_sv_s$

​		全部移到左边，由于 $v_1,\cdots,v_n$ 是 $V$ 的基，全部系数为 $0$.





### 线性映射的一些定理

- 到更大维数向量空间的线性映射不是满的 

  一定有东西会表示不出来

- 到更小维数向量空间的线性映射不是单的



### ~~线性映射的矩阵表示~~

$$
T(v_1,\cdots,v_n)=(w_1,\cdots,w_m)M(T)
\notag
$$

$M(T)$ 的第 $k$ 列可以看成 $T$ 对 $v_k$ 的作用
$$
Tv_k=a_{1,k}w_1+\cdots+a_{m,k}w_m\notag
$$
例子：微分映射 $T:P_3\to P_2$

<img src="https://tva1.sinaimg.cn/large/00831rSTly1gccb7lqu5wj31ld0rsaee.jpg" alt="image-20200228185111592" style="zoom: 25%;" />



注意 $M(T)$ 是代表线性变换。



### ~~同一个向量在不同坐标下的坐标关系~~

$T:V\to W$

$\xi=(v_1,\cdots,v_n)A=(w_1,\cdots,w_m)B$

其中 $A=(a_1,\cdots,a_n)^T$, $B=(b_1,\cdots,b_m)^T$ (注意有转置，**基是行向量，坐标是列向量**)

是 $\xi$ 在不同基下的坐标

则 ：晕了



### 线性方程组

设矩阵 $A\in M_{m\times n}(\mathbf{F})$, 若 $r(A)=r$, 则齐次线性方程组 $AX=0$ 的解空间 $N(A)$ 是一个 $n-r$ 维子空间。

证明：

​	$A$ 与一个线性映射 $\sigma\in L(V_1,V_2)$ 对应, $\dim V_1=n, \dim V_2=m$ .

​	$AX=0$  解空间中的基是 $\sigma$ 核空间的基关于 $V_1$ 的坐标, 解空间的基和 $N(\sigma)$ 的基一一对应 .



简单证明：

​	把 $A$ 看作线性变换， $rank(A)=Range(A)$ , $A$ 的核 $N(A)$ 就是方程组的解空间。



**注**：矩阵的秩：矩阵列向量中极大线性无关组的元素个数，等于矩阵作为线性变换对应矩阵的像空间维数。







###幂等变换的性质 

幂等变换: $T:V\to W,\quad T^2=T$  

- $N(T)=\{v-T(v)\mid v\in V \}$

- $N(T)\cap R(T)=0$
- $V=N(T)\oplus R(T)$

证明：

​		对第二条，只需证明核空间与像空间的交是 $0$

​		如果 $w\in N(T)\cap R(T)$, 则：

​				由于 $w\in N(T)$, $T(w)=0$

​				由于 $w\in R(T)$, $\exist v\in V,w=T(v)$, **两边再作用一下 $T$**, 得到：$0=T(w)=T^2(v)=T(v)=w$ 

​		

​		对第一条，

​		这是由于 $\forall v\in V,T^2(v)=T(v)=>T[T(v)-v]=0=>T(v)-v\in N(T)=>\{v-T(v)\}\subseteq N(T)\\ \forall v\in N(T),v=v-T(v)=>\{v-T(v)\}\supseteq N(T) $



### 算子

算子：向量空间到自身的线性映射

对有限为空间的算子 $T$：$T$ 可逆$\iff$ $T$ 单 $\iff T$ 满





### 对偶

 

## 3. 欧氏空间

### Shcmidt 正交化

- 正交化

  给定一组基 $\alpha=\{\alpha_1,\cdots,\alpha_n\}$, 

  设 $\beta_1=\alpha_1$

  ​	$\beta_2=\alpha_2+\lambda_{1,2}\beta_1$ ，	$<\beta_1,\beta_2>=0$ => $\displaystyle \lambda_{1,2}=-\frac{<\alpha_2,\beta_1>}{<\beta_1,\beta_1>}$

  已求得正交向量 $\beta_1,\cdots,\beta_{m-1}$,

  则设 
  $$
  \beta_m=\alpha_m+\lambda_{m-1,m}\beta_{m-1}+\cdots+\lambda_{2,m}\beta_2+\lambda_{1,m}\beta_1
  \notag
  $$
  

  由$<\beta_m,\beta_k>=0$ 得到：
  $$
  \lambda_{k,m}=-\frac{<\alpha_m,\beta_k>}{<\beta_k,\beta_k>}
  \notag
  $$
  
- 单位化

  $\displaystyle \varepsilon_m=\frac{\beta_m}{|\beta_m|}$



## 4. 多项式

### 带余除法

设 $p,s\in \mathcal{P}(\mathbb{F})$ 且 $s\neq 0$, 则存在唯一多项式 $q,r\in\mathcal{P}(\mathbb{F})$ 使得
$$
p=sq+r
\notag
$$
且 $\deg\ r<\deg\ s$ .



证明： 

设 $n=\deg p,m =\deg s$ 

$n>m$ 时：
$$
\because T:\mathcal{P_{n-m}}\times\mathcal{P_{m-1}}\to\mathcal{P_{n}},\quad (q,r)\mapsto sq+r \quad 是线性双射
\\
\therefore\{(q,r)\mid q\in \mathcal{P_{n-m}},r\in\mathcal{P_{m-1}}\}\cong\{sq+r\mid q\in \mathcal{P_{n-m}},r\in\mathcal{P_{m-1}}\}
\\
\because \dim \mathcal{P_{n-m}}\times\mathcal{P_{m-1}}=(n-m+1)+(m-1+1)=n+1\\
\therefore \dim R(T)=n+1=\mathcal{P_n}\\
\therefore \{sq+r\mid q\in \mathcal{P_{n-m}},r\in\mathcal{P_{m-1}}\}\cong \mathcal{P_n(\mathbb{F})}
\notag
$$





## 5. 矩阵

### 秩

- 定义与意义

矩阵的列向量的极大线性无关组的元素个数。

$A:m\times n\iff \sigma:\R^n\to\R^m$

由于：
$$
R(A)=\left(
\begin{matrix}
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n\\
a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n\\
\vdots\\
a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n
\end{matrix}
\right)
=\mathscr{L}\left\{ \left(\begin{aligned}a_{11}\\a_{21}\\ \vdots \\ a_{m1}\end{aligned}\right),\left(\begin{aligned}a_{12}\\a_{22}\\ \vdots \\ a_{m2}\end{aligned}\right),\cdots,\left(\begin{aligned}a_{1n}\\a_{2n}\\ \vdots \\ a_{mn}\end{aligned}\right)\right\}
$$
$A$ 的列秩等于 $A$ 的列空间维数，也是对应线性映射的像空间维数 $\dim R(A)$。



- 行秩 $=$ 列秩

