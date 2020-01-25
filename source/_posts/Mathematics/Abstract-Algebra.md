---
title: Abstract Algebra
tags: 代数
categories:
  - Mathematics
  - Algebra
date: 2020-01-20 10:20:43

---

# 抽象代数内容整理

## 1. 群论

## 1.1 群 Group

### 1.1.1 群的定义

一个*群* 是带有下列性质的合成法则的集合$G$ :

1. 合成法则满足结合律
2. 包含单位元
3. 每个元素都有逆元



$=>$ 消去律



### 1.1.2 子群 subgroup

#### 1.1.2.1 定义

1. 对运算具有封闭性
2. 包含单位元
3. 每个元素都有逆元



#### 1.1.2.2 正规子群 normal subgroup

$ N \trianglelefteq G \\ \iff \forall a\in N,g\in G \quad gag^{-1}\in G\\ \iff gNg^{-1}=N \\ \iff gN=Ng $



### 1.1.3 同态 homomorphism

两个群中与合成法则相容的映射。

$\varphi : G\to G',\; s.t \\ \forall \;a,b \in G, \quad \varphi(ab)=\varphi(a)\varphi(b)  $



$=>$ $\varphi$ 把单位元映射为单位元，把逆元映射为逆元

$=>$ $ im \varphi \leqslant G', \quad ker \varphi \trianglelefteq G$ 

$=>$ 群同态基本定理： $G/ker\varphi \;\cong\; im\varphi$



### 1.1.4 同构 isomorphism 

双射群同态。



$=>$ 第一同构定理：

 $ \varphi$是一个满同态， $\pi $ 是典范态射 $(canonical)$ 

则存在唯一一个同构映射$\overline \varphi : \overline G\to G' \; s.t.\; \varphi=\overline\varphi \circ \pi$



### 1.1.5 陪集 Coset

关于同余关系的等价类。

#### 1.1.5.1 左陪集 

$ H\leqslant G, a\in G, aH=\{ah\;|\;a\in H  \}$ 



$=>$ $a\in bH \Leftrightarrow aH=bH$

$=>$ $ |G|=[G:H]\cdot|H|$



#### 1.1.5.2 拉格朗日定理 Lagrange Theorem

子群的阶整除群的阶。 $i.e. |H| \biggm| |G|$



$=>$ 素数阶群是循环群

  

### 1.1.6 对应定理 The Correspondence Theorem 

$\varphi : G\to G' $ 是一个满同态.

$ K=ker\varphi,\; H'\leqslant G', H\supset K$ .

$=>$ 若 $H'$ 是正规子群，则 $H$ 也是正规子群。$\varphi$ 是满射，$H$ 是正规子群，则$H'$ 也是正规子群。

$=>$ $\{G的含有K的子群 \}\longleftrightarrow \{G'的子群\}$



### 1.1.7 积群

$G\times G'=\{(g,g') \;|\;g\in G,\; g'\in G'\}$



$=>$ $r$、$s$ 互素，则 $C_{rs}\cong C_r\times C_s$

$=>$ 命题 $2.11.4$ :

$H,K \leqslant G, let \quad f:H\times K \to G$ 是一个映射，

$def : f(h,k)=hk. \quad imf=HK=\{hk\;|\;h\in H,k\in K \} $

$then$ $f$  是一个同构   i.e  $H\times K \cong HK $ 

$ \iff$ $H\cap K={1},\;HK=G,\;\;H\trianglelefteq G,K\trianglelefteq G.  $



### 1.1.8 商群

群$G$在正规子群$N$的陪集的集合上定义合成法则，这个运算法则使得正规子群的陪集成为一个群，称为*商群*。

$\overline G=G/N\triangleq \{\overline g\;|\;\overline g=gN,g\in G\}$



$=>$ 典范态射：$\pi \; :\; G\to \overline G \quad g\mapsto\overline g$  	这是一个满同态。







## 1.2 群作用

### 1.2.1 轨道、稳定子 Orbit and Stablizer

#### 1.2.1.1 定义

orbit： $O_s=\{s'\in S | s'=gs,g\in G\}$

stabilizer：$G_s=\{g\in G|gs=s\}$



#### 1.2.1.2 计数公式

$|G|=|G_s|\cdot |O_s|$



$=>$  $|O_s|=[G:G_s]$

$=>$ $|S|=|O_1|+|O_2|+\cdots +|O_k|$



### 1.2.2 对陪集的作用

#### 1.2.2.1 诱导表示

### 1.2.3 置换表示

#### 1.2.3.1 置换表示

群$G$的置换表示送从该群到一个对称群的同态.

$\varphi : G\to S_N$

$[G在S上的作用]\leftrightarrow[置换表示]$



#### 1.2.3.2 凯莱定理

每一个有限群都同构于某个置换群的子群.

如果$|G|=n$ , 则 $G\hookrightarrow S_n$



### 1.2.4 共轭作用 Conjugate Action

#### 1.2.4.1 中心化子、共轭类

中心化子：元素$x$关于共轭作用的稳定子。

$Z(x)=\{g\in G|gx=xg\}$

共轭类：$x$关于共轭作用的轨道。

$C(x)=\{x'\in G|x'=gxg^{-1},g\in G\}$



$=>$ $|G|=|Z(x)|\cdot |C(x)|$



####  1.2.4.1 类方程

共轭类划分群$G$。

$|G|=\sum_\limits {共轭类C} |C|=|Z|+\sum\limits_{x\in g}|C(x)|$



### 1.2.5 Sylow定理

设 $|G|=n=p^e m$ .

#### 1.2.5.1 p-群相关命题

p-群：阶是素数 $p$ 的正幂的群。

- p-群 $G$ 的中心是非平凡群。

- （不动点定理）$G$是p-群，$S$ 是一个有限集合，$G$ 在 $S$ 上面作用。若$p\nmid |S|$ , 则$G$的作用有个不动点$s$， 它的稳定子是整个群。

- $p^2$ 阶群是 $Abel$ 群。

  

#### 1.2.5.4 Sylow-I 

阶被素数 $p$ 整除的有限群包含一个 $Sylow-p$ 子群。



$=>$ 阶被素数 $p$ 整除的有限群包含一个 $p$ 阶的元素。



#### 1.2.5.5 Sylow-II

(a) $G$ 的 $Sylow-p$ 子群是共轭子群。

(b) $G$的每一个p-群的子群都包含在一个 $Sylow-p$ 子群里。 



$=>$ 群 $G$ 只有一个 $Sylow-p$ 子群$\iff$这个子群是正规子群



#### 1.2.5.6 Sylow-III

$G$ 的 $Sylow-p$ 子群的个数整除 $m$ 且模 $p$ 余 $1$.





### 1.2.6 [自由群](https://zh.wikipedia.org/wiki/%E8%87%AA%E7%94%B1%E7%BE%A4)

群的元素的一个集合称为是*自由的*，如果其元素除了群的公理给出的关系外不满足任何别的关系。

具有自由的生成元的集合的群称为*自由群*。





## 2. 环论

### 2.1 环的定义 Ring

一个*环* $R$ 是一个具有两种合成法则$+$和$\times$ 的集合。

关于加法为阿贝尔群，关于乘法满足结合律。

关于加法和乘法满足分配律。



**整环**（Integral Domain）：不含零因子的环。整环满足消去律。

### 2.2 环同态 Ring Homomorphism 

从一个环到另一个环的映射，与加法和乘法的合成法则相容。

$\varphi (a+b)=\varphi(a)+\varphi(b),\quad \varphi(ab)=\varphi(a)\cdot \varphi(b)$

若环有乘法单位元，则 $\varphi(1)=1$



### 2.3 理想 Ideal

- 环$R$的左理想$I$是满足下列性质的非空子集：

（1）关于加法封闭

（2）$\forall r\in R, s\in I, \quad rs\in I$



- 极大理想：$M< R(M\neq R),$ 若$I\subseteq M,$ 则 $I=M$ 或 $I=R$ 。



$=>$ 整数环 $Z$ 的极大理想是有素数生成的主理想。

$=>$ $F$ 是一个域，$F[x]$ 的极大理想是由既约的首一多项式生成的主理想



### 2.4 商环, 第一同构定理

类似群论。

### 2.5 对应定理

$\varphi ：R\to R'$ 是满射环同态，则存在一个双射对应：

$\{R的含核 理想\}\leftrightarrow \{R'的理想\}$



### 2.6 希尔伯特零点定理

多项式环 $\mathbf C[x_1,x_2,\cdots,x_n]$的极大理想与复$n$维空间的点一一对应。$\mathbf{C}^n $ 的一个点$a=(a_1,a_2,\cdots,c_n)$对应于映 $x_i \rightsquigarrow a_i$的代入映射 $s_a:\mathbf{C}[x_1,\cdots, x_n]\to\mathbf{C}$的核$M_a$ . 这个映射的核 $M_a$ 是由 $n$ 个线性多项式 $x_i-a_i$ 生成的理想。



### 2.7 因子分解

#### 2.7.1 基本概念

- 单位 unit ：有乘法逆元
- 相伴 associate ：$a$ 和 $b$ 相伴$\iff$$(a)=(b)$
- 不可约 irreducible :  不是单位且没有真因子，因子为单位或者相伴元
- 素元 prime : $p$ 是素元 $\iff$ $p\mid ab=>p\mid a \quad or \quad p\mid b$



#### 2.7.2 欧几里得整环 ED

- 有尺度函数，可进行带余除法
- 常见例子：$\mathbf{Z},F[x],\mathbf{Z}[i]$
- $ED$ is $PID$



#### 2.7.3 主理想整环 PID

- 所有理想均为主理想
- 理想$(a,b)=Ra+Rb$ 的生成元 $d$ 是 $a,b$ 的最大公因子
- $\exist r,s \in R\quad s.t.\quad d=ra+sb$
- $PID$ 中，元素是不可约的当且仅当它是素的



#### 2.7.4 唯一分解整环 UFD

- 分解终止，且元素的既约分解唯一
- $ED=>PID=>UFD$



### 2.7 高斯引理

- 本原多项式：正次数的正系数多项式，且整数系数 $a_1, a_2,\cdots,a_n$的最大公因子是$1$。
- $f$ 是本原的$\iff$$f$ 不能被任何素数 $p$ 整除$\iff$$\forall p: prime,\psi_p(f)\neq 0\quad(\psi_p为系数模素数p的同态)$
- $Gauss's$ $Lemma$ : 本原多项式的积是本原的
- 每个有理系数的正次数多项式 $f(x)$ 可唯一地写成 $f(x)=cf_0(x)$ ，其中 $c\in \mathbb{Q}$，$f_0(x)$ 是本原多项式
- 多项式环 $ \mathbf{Z}[x]$ 是唯一分解整环。每个不是 $\pm 1$ 的非零多项式 $f(x)\in\mathbf{Z}[x]$ 可以写成积的形式： $f(x)=\pm p_1\cdots p_m q_1(x)\cdots q_n(x)$ ，$p_i $ 是整素数，$q_i$ 是本原的既约多项式。



### 2.8 爱森斯坦判别法

设 $f(x)=a_nx^n+\cdots+a_0$ 是一个整多项式，并设 $p$ 是一个素整数。若 $f$ 的系数满足：

(1) $p\nmid a_n$

(2) $p\mid a_{n-1},\dots,p\mid a_0$

(3) $p^2 \nmid a_0$

则 $f$ 在 $\mathbf{Q}[x]$ 中是既约的。



### 2.9 模论：环上的线性代数 

####2.9.1 模 module

$R$ 是一个环，$R$-模 $V$ 包含一个加法阿贝尔群与一个标量乘法 $R\times V\to V ,\quad r,v\rightsquigarrow rv $ , 满足一下条件：

$1v=v,\quad (rs)v=r(sv),\quad (r+s)v=rv+sv,\quad r(v+v')=rv+rv'.\qquad\forall r,s \in R,\quad v,v'\in V$



$=>$ $\mathbf{Z}$-模 与 阿贝尔群 是等价的概念，因为一个合成法则记为加法的阿贝尔群有唯一的 方法构成 $\mathbf{Z}$ 上的一个模。



#### 2.9.2 子模

在加法和标量乘法下封闭的子集。



$=>$ $R$-模 $R$ 的子模是 $R$ 的理想



#### 2.9.3 商模

#### 2.9.3.1 模同态

$\varphi : V\to W\quad \varphi(v+v')=\varphi(v)+\varphi(v'),\quad \varphi(rv)=r\varphi(v)$

同态的像是子模。



#### 2.9.3.2 典范态射

令 $W $ 是 $R$-模 $V$ 的子模。

$\pi : V\to \overline V\quad v\rightsquigarrow\overline v=[v+W]$ 

$\pi$ 是一个满同态，$Ker\pi =W$



#### 2.9.3.3 第一同构定理 

 $f:V\to V'$ 是模满同态，同态核  $K=W$.  则 $\overline f:\overline V=V/W\to V'$ 是一个同构。



#### 2.9.3.4 对应定理 

$f:V\to V'$ 是模满同态, 核为 $W$ .  存在一个一一对应：

$\{V的包含W的子模\}\leftrightarrow \{V' 的子模\}$



### 自由模







## 3. 域论



## 4. Galois

