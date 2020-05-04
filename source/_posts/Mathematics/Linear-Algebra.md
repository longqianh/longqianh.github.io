---
title: Linear Algebra
date: 2020-02-28 09:44:42
tags:
categories:
  - Mathematics
  - Algebra
mathjax: true
---

# 线性代数学习笔记

不加入例题

主要是例题中用到的基本性质和定理的证明

推荐网站：[线代启示录](https://ccjou.wordpress.com/)

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
\begin{aligned}
W_1\cap W_2&=\mathcal{L}(\alpha_1,\cdots,\alpha_r)\\
W_1&=\mathcal{L}(\alpha_1,\cdots,\alpha_r,\beta_1,\cdots,\beta_s)\\
W_2&=\mathcal{L}(\alpha_1,\cdots,\alpha_r,\gamma_1,\cdots,\gamma_t)\\
\implies W_1+W_2&=\mathcal{L}(\alpha_1,\cdots,\alpha_r,\beta_1,\cdots,\beta_s,\gamma_1,\cdots,\gamma_t)
\end{aligned}
$$


​		按线性无关定义写出式子，把 $\gamma$ 项移到等式右边，

​		利用 $W_1\cap W_2$ 可以把两边都表示成 $\alpha$ 项的线性组合，

​		依次利用移项后是 $W_2$ 和 $ W_1 $ 的基，最后得到全是 $0$。





### 直和

设 $U_1,\cdots,U_m$ 都是 $V$ 的子空间，则:

- （定义）$U_1+\cdots+U_m$ 是直和，如果 $U_1+\cdots+U_m$ 中的每个元素都可以唯一的表示成 $u_1+\cdots+u_m$ ，其中每个 $u_j\in U_j$。
- $\iff$ $0$ 唯一分解成 $0+\cdots+0$

- 对于两个子空间的直和，$U+W=U\oplus W\iff U\cap W=\{0\}$



##### 常用结论：

- $\dim V<\infty$ ，若 $T\in \mathcal{L}[V]$ 是幂等变换，则 $V=N(T)\oplus R(T)$ .
- $T\in\mathcal{L}[V],\dim V=n\implies V=R(T^n)\oplus N(T^n)$







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



### 线性映射的矩阵表示

(搞晕了很久 现在终于弄明白了)

#### （1）对基

$$
T(e_1,\cdots,e_n)=(f_1,\cdots,f_m)M(T)\\
Te_k=M(T)第k列
\notag
$$

​	其中，$e$ 是原空间的基， $f$ 是像空间的基。



#### （2）对向量

​	设 $X=(x_1,\cdots,x_n)^T$ 为向量 $\xi$ 在基 $e=(e_1,\cdots,e_n)$ 下的坐标。 
$$
\xi=(e_1,\cdots,e_n)X
\notag
$$
​	$T$ 作用后的向量为：
$$
\begin{aligned}
T(\xi)&=T(e_1,\cdots,e_n)X\\
&=(f_1,\cdots,f_m)M(T)X
\end{aligned}
$$
​	$T$ 作用后得到的向量的坐标是 $M(T)X$.  

(美妙的证明)



#### （3）线性映射在不同基下表示表示矩阵的关系

相似。
$$
\begin{aligned}
T[(e_1,\cdots,e_n)]&=T[(f_1,\cdots,f_m)A]\\
&=T[(f_1,\cdots,f_m)]A\\
&=(f_1,\cdots,f_m)M_fA\\
&=(e_1,\cdots,e_n)A^{-1}M_fA
\end{aligned}
$$
所以，$M_e=A^{-1}M_fA$, $A$ 为基的过渡矩阵，$M_e,M_f$ 为线性映射在不同基下的矩阵表示。



#### （4）同一个向量在不同基下的坐标关系

$T:V\to W$

$\xi=(v_1,\cdots,v_n)A=(w_1,\cdots,w_m)B$

其中 $A=(a_1,\cdots,a_n)^T$, $B=(b_1,\cdots,b_m)^T$ (注意有转置，**基是行向量，坐标是列向量**)

是 $\xi$ 在不同基下的坐标

则 ：
$$
B=M(T)^{-1}A\notag
$$



#### （5）总结

由此可见，线性映射对应的矩阵：

- 对基的变换是右乘作用，对基的 $k$ 分量变换后的结果为矩阵的第 $k$ 列
- 对向量的坐标的变换为左乘
- 在不同基下的表示矩阵相似







### 线性方程组

设矩阵 $A\in M_{m\times n}(\mathbf{F})$, 若 $r(A)=r$, 则齐次线性方程组 $AX=0$ 的解空间 $N(A)$ 是一个 $n-r$ 维子空间。

证明：

​	$A$ 与一个线性映射 $\sigma\in L(V_1,V_2)$ 对应, $\dim V_1=n, \dim V_2=m$ .

​	$AX=0$  解空间中的基是 $\sigma$ 核空间的基关于 $V_1$ 的坐标, 解空间的基和 $N(\sigma)$ 的基一一对应 .



简单证明：

​	把 $A$ 看作线性变换， $rank(A)=Range(A)$ , $A$ 的核 $N(A)$ 就是方程组的解空间。



**注**：矩阵的秩：矩阵列向量中极大线性无关组的元素个数，等于矩阵作为线性变换对应矩阵的像空间维数。





### 幂等变换的性质 

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

 

## 3. 内积空间

带有内积的向量空间。

内积：对第一个分量成线性，对第二个分量成共轭线性，有共轭对称性。



### 线性映射的内积表示

$$
\begin{align}
T((v_1,\dots,v_n)&=(v_1,\dots,v_n)A\notag \\
T(v_i)&=\sum_{j=1}^n v_j a_{ji}\notag \\
\therefore \quad a_{ij}&=\langle Tv_j,v_i\rangle
\end{align}
$$





### 柯西-施瓦茨不等式

$$
|\langle u,v \rangle|\leq\|u\|\|v\|
$$

证明：

将 $u$ 正交分解:
$$
u=\frac{\langle u,v\rangle}{\|v^2\|}v + w
$$
则 
$$
\begin{aligned}
\|u\|^2&=\bigg\|\frac{\langle u,v\rangle}{\|v^2\|}v\bigg\|^2+\|w\|^2\\
&\geq \bigg\|\frac{\langle u,v\rangle}{\|v^2\|}v\bigg\|^2=\frac{|\langle u,v\rangle|^2}{\|v\|^2}
\end{aligned}
$$
乘过去即得。



### Shcmidt 正交化

设 $v_1,\dots,v_m$ 是 $V$ 中的线性无关向量组，设 $e_1=v_1/\|v_1\|$.
$$
e_j=\frac{v_j-\langle v_j,e_1\rangle e_1-\cdots-\langle v_j,e_{j-1}\rangle e_{j-1}}{\|v_j-\langle v_j,e_1\rangle e_1-\cdots-\langle v_j,e_{j-1}\rangle e_{j-1}\|}
$$
$\{e_1,\dots,e_m\}$ 是 $V$ 中的规范正交组。



### 舒尔定理

设 $V$ 是有限维的复向量空间且 $T\in \mathcal{L}(V,\mathbf{F})$ ，则 $T$ 关于 $V$ 的某个规范正交基具有上三角矩阵。



证明：

​		设 $V=span\{v_1,\dots,v_n\}$ , $\{e_1,\dots,e_n\}$ 为其规范正交基。

​		则 $span\{e_1,\dots,e_n\}=span\{v_1,\dots,v_n\}$

​		由于存在 $T$ ,其关于 $\{v_1,\dots,v_n\}$ 具有上三角矩阵，则对于每个 $j=1,\dots,n$ 	

​		$ span\{v_1,\dots,v_j\}$在 $T$ 作用下不变

​		故 $span\{e_1,\dots,e_j\}=span\{v_1,\dots,v_j\}$ 在 $T$ 作用下不变

​		所以 $T$ 关于 $\{e_1,\dots,e_n\}$ 具有上三角矩阵。



##### 关于上三角矩阵

设 $T\in\mathcal{L}[V]$，$(v_1,\dots,v_n)$ 是 $V$ 的基。

TFAE：

- $T$ 关于 $v_1,\dots,v_n$ 的矩阵是上三角的
-  $Tv_j\in span\{v_1,\dots,v_j\}$
- $span\{v_1,\dots,v_j\}$ 在 $T$ 作用下不变





### 对偶空间

#### 符号说明

- $\mathcal{L}(V,W)$ 表示从 $V$ 到 $W$ 的全部线性映射
- $\mathbf{F}^{m,n}\triangleq \mathbf{F}^m\times\mathbf{F}^n$ 可看作所有 $m\times n$ 矩阵
- 线性泛函：从 $V$ 到 $\mathbf{F}$ 的线性映射，即为 $\mathcal{L}(V,\mathbf{F})$ 中的元素
- 对偶空间 $V’$：$V$ 上所有线性泛函构成的向量空间

- 对偶基 $\{\varphi_1,\dots,\varphi_n\}$： $\varphi_j(e_k)=\delta_{jk}$
- 对偶映射 $T’$：$T’(\varphi)=\varphi\circ T ,\quad T’\in\mathcal{L}(V’,W’), \varphi\in W’,T’\in V'$
- 零化子 $U^0$：$U^0=\{\varphi\in V’:\varphi(u)=0,\forall u\in U\},U\subset V$



#### 重要结论

- $\mathcal{M}(T)$ 为 $T\in\mathcal{L}(V,W)$ 的矩阵表示 , 其实是一个从 $\mathcal{L}(V,W)\to\mathbf{F}^{m,n}$ 的同构。

- 对偶映射的代数性质：$(aS+bT)’=aS’+bT’$, $(ST)’=T’S'$
- $T’$ 的矩阵是 $T$ 的矩阵的转置
- $\dim V’=\dim V$
- $\dim U+\dim U^0=\dim V$
- $T 满\iff T’单, N(T’)=R(T)^0$
- $ T单\iff T’满,R(T’)=N(T)^0$

- $\dim R(T)=\dim R(T')$





### 里斯表示定理

设 $V$ 是有限维的且 $\varphi$ 是 $V$ 上的线性泛函，则存在唯一的向量 $u\in V$ 使得对每个 $v\in V$ 均有 $\varphi(v)=\langle v,u\rangle$. 







## 4. 多项式

### 带余除法

设 $p,s\in \mathcal{P}(\mathbb{F})$ 且 $s\neq 0$, 则存在唯一多项式 $q,r\in\mathcal{P}(\mathbb{F})$ 使得
$$
p=sq+r
\notag
$$
且 $\deg\ r<\deg\ s$ .



证明： 

​		记 $n=\deg p,m =\deg s$ 

​		$n>m$ 时：
$$
\begin{aligned}
&\because T:\mathcal{P_{n-m}}\times\mathcal{P_{m-1}}\to\mathcal{P_{n}},\quad (q,r)\mapsto sq+r \quad 是线性双射
\\
&\therefore\{(q,r)\mid q\in \mathcal{P_{n-m}},r\in\mathcal{P_{m-1}}\}\cong\{sq+r\mid q\in \mathcal{P_{n-m}},r\in\mathcal{P_{m-1}}\}
\\
&\because \dim \mathcal{P_{n-m}}\times\mathcal{P_{m-1}}=(n-m+1)+(m-1+1)=n+1\\
&\therefore \dim R(T)=n+1=\dim \mathcal{P_n}\\
&\therefore \{sq+r\mid q\in \mathcal{P_{n-m}},r\in\mathcal{P_{m-1}}\}\cong \mathcal{P_n(\mathbb{F})}
\end{aligned}
$$





### 代数基本定理

任何一个次数大于 $0$ 的复多项式都至少有一个复数根。

证明：

​		若 $p\in \mathbf{C}[x]$  没有根，则 $\displaystyle\frac 1 p$ 为全平面有界的解析函数。由刘维尔定理知其必为常数。



### 拉格朗日多项式

$$
f_i (x)=\prod_{\substack{s=1\\s\neq i}}^n \frac{x-c_s}{c_i-c_s}
$$

$\{f_0,f_1,\dots,f_n\}$ 构成了 $\mathbf{F}[x]_{\leq n} $ 的一组代入意义下的单位正交基（ $f_i(c_j)=\delta_{ij}$）

拉格朗日插值公式： $g(x)=\sum b_i f_i $ 满足： $g(c_i)=b_i$ .





## 5. 矩阵

### 秩

- 定义与意义

矩阵的列向量的极大线性无关组的元素个数。

$A:m\times n\iff \sigma:\mathbb{R}^n\to\mathbb{R}^m$

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





### 行列式

- $\det (A)=\det(A^T)$ 	证：初等矩阵转置行列式不变，将矩阵 $A$ 进行初等矩阵分解





## 6. 特征值理论

### 特征向量线性无关

相应于不同特征值的特征向量线性无关。

证明：

​		设 $T\in \mathcal{L}(V)$ ，设 $\lambda_1,\dots,\lambda_m$ 是 $T$ 对互不相同的特征值， $v_1,\dots,v_m$ 是相应的特征向量，则 $v_1,\dots,v_m$ 是线性无关的。

​		设 $k$ 是使得 $v_k=span\{v_1,\dots,v_{k-1}\}$ 成立的**最小**正整数。
$$
\begin{aligned}
v_k&=a_1v_1+\cdots+a_{k-1}v_{k-1}\\
T(v_k)=\lambda_k v_k&=a_1\lambda_1v_1+\cdots+a_{k-1}\lambda_{k-1}v_{k-1}\\
\lambda_k v_k&=a_1\lambda_k v_1+\cdots+a_{k-1}\lambda_{k}v_{k-1}
\\
\\
\implies &a_1(\lambda_1-\lambda_k)v_1+\cdots+a_{k-1}(\lambda_{k-1}-\lambda_{k})v_{k-1}=0\\
\implies &a_1=\cdots=a_{k-1}=0
\end{aligned}
$$
​		矛盾，故不存在这样的 $k$ ， 特征向量线性无关。



### 特征子空间

特征子空间是不变子空间。

特征子空间的和是直和。

$i.e.$ 
$$
W=E_{\lambda_1}+\cdots + E_{\lambda_m}=E_{\lambda_1}\oplus \cdots \oplus E_{\lambda_m}
\notag
$$
证明：

设$\lambda_j$ 和 $E_{\lambda_j}$ 是 $n$ 维线性空间 $V$ 的线性变换 $T$ 的 $m$ 个互不相同的特征值及相应的特征子空间，则只需证明**零向量**在 $W$ 中的**分解唯一**。

即证： $\xi_1+\cdots \xi_m=0\implies \xi_i=0,\quad \xi_i\in E_{\lambda_i}$ 

注意 $\xi_i$ 是特征子空间 $E_{\lambda_i}$ 中的向量，由属于 $\lambda_i$ 的特征向量线性组合而成，仍有 $T(\xi_i)=\lambda_i\xi_i$

**归纳**证明：
$$
\begin{aligned}
m=2: \quad \xi_1+\xi_2=0 &\implies T(\xi_1+\xi_2)=\lambda_1\xi_1+\lambda_2\xi_2=0\\
&\implies (\lambda_1-\lambda_2)\xi_2=0\\
&\implies \xi_1=\xi_2=0\\


\end{aligned}
$$
设对 $m-1$ 结论成立，考虑 $m$ :
$$
\begin{aligned}
& \xi_1+\cdots+\xi_m=0\\
&T(\xi_1+\cdots+\xi_m)=\lambda_1\xi_1+\cdots+\lambda_m\xi_m=0\\
&(\lambda_1-\lambda_m)\xi_1+\cdots+(\lambda_{m-1}-\lambda_m)\xi_{m-1}=0\\
\implies& \xi_1=\cdots=\xi_{m-1}=0\implies \xi_m=0
\end{aligned}
$$


由此也可以得到属于不同特征值的特征向量线性无关，因为 $E_{\lambda_i}\cap E_{\lambda_j}={\vec 0}$



### 可对角化的条件

$n$ 维线性空间 $V$ 上的线性变换 $T$ 的表示矩阵 $M(T)$ 可对角化：

$ \iff$  $T$ 有 $n$ 个(线性无关的)特征向量  or  $V$ 有由 $T$ 的特征向量构成的基

$\iff$ $V=E_{\lambda_1}\oplus \cdots \oplus E_{\lambda_m} $  (已经知道和是直和，接下来只需证明和就是 $V$ ,由有由特征向量构成的基即得)

$\iff$ $T$ 的每个特征值的重数等于其特征子空间的维数 ( 代数重数 $=$ 几何重数 ）, 且不同特征值的重数之和等				   于 $n$ 

注：一般情况下，代数重数大于等于几何重数，证明先放一放。



###  矩阵的秩、维数与特征值

特征值个数等于矩阵的维数。其中，不等于 $0$ 且**不同**的特征值个数为矩阵的秩。



也就是说，矩阵的秩是特征子空间的种类数，如何理解和证明？





### 广义特征向量

#### 零空间的停止增长



#### 广义特征向量线性无关性



#### 广义特征空间



##### 刻画













## 7. 算子理论

### 不变子空间

待整理



### 正交投影

待整理



### 自伴算子

$T=T^*$.

类比：$z$ 是实数

#### 性质

- $\langle Tv,w\rangle=\langle v,Tw\rangle$

- 特征值都是实数 

  证：$\lambda\|v\|^2=\langle \lambda v,v\rangle=\langle Tv,v\rangle=\langle v,Tv\rangle=\langle v,\lambda v\rangle=\overline\lambda \|v\|^2$

- 在 $\mathbf{C}$, 只有零算子才能使 $Tv$ 总正交于 $v$ : $\forall v\in V ,\langle Tv,v\rangle=0\implies T\equiv 0$

  证：
  $$
  \begin{aligned}
  \forall u,w\in V\\
  \langle Tu,w \rangle=&\frac{\left\langle T(u+w),u+w\right\rangle-\left\langle T(u-w),u-w\right\rangle}{4}\\
  &+\frac{\left\langle T(u+iw),u+iw\right\rangle-\left\langle T(u-iw),u-iw\right\rangle}{4}
  \end{aligned}
  $$

- 在 $\mathbf{C}$, $\forall v\in V,\langle Tv,v\rangle\in \mathbf{R} $  (充要) 

  证： $\langle Tv,v\rangle-\overline{\langle Tv,v\rangle}=0$

- 相应于不同特征值的特征向量正交



### 正规算子

和伴随可交换：$TT^*=T^*T$

类比：复数 $z$ : 显然 $zz^*=z^*z$



#### 性质

- $\|Tv\|=\|T^* v\|$  (充要)

  证： $TT^*-T^*T=0\iff \forall v\in V, \langle (TT^*-T^*T)v,v\rangle=0\iff \|T^*v\|^2=\|Tv\|^2$

- $T$ 和 $T^*$ 有相同的特征向量 （是充分的吗？）

  具体：$v$ 是 $T$ 的相应于特征值 $\lambda$ 的特征向量，则 $v$ 也是 $T^*$ 的相应于 $\overline\lambda$ 的特征向量

  证：$0=\|(T-\lambda I)v\|=\|(T-\lambda I)^*v\|=\|(T^*-\overline\lambda I)v\|$

- 相应于不同特征值的特征向量正交

  证：$(\lambda-\mu)\langle v,w\rangle=\langle \lambda v,w\rangle-\langle v,\overline\mu w\rangle=\langle Tv,w\rangle-\langle v,T^*w\rangle=0$

  注：$\lambda$ 是 $T$ 的特征值当且仅当 $\overline\lambda$ 是 $T^*$ 的特征值。 （ $\det (T-\lambda I)=0\iff \det (T^*-\overline \lambda I)=0$ ）






### 幂零算子







### 谱分解

#### 复谱定理



#### 实谱定理



#### 谱分解定理





### 奇异值分解

#### 正算子



##### 刻画



#### 等距同构



##### 刻画





#### 极分解





#### 奇异值分解

##### 奇异值



##### 线性变换奇异值定理



##### 矩阵的奇异值分解











