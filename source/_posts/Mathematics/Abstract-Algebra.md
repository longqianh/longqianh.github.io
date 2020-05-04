---
title: Abstract Algebra
tags: 代数
categories:
  - Mathematics
  - Algebra
mathjax: true
date: 2020-01-20 10:20:43

---

# 抽象代数内容整理

## 1  群论

### 1.1 群 Group

#### 1.1.1 群的定义

一个*群* 是带有下列性质的合成法则的集合$G$ :

1. 合成法则满足结合律
2. 包含单位元
3. 每个元素都有逆元

=&gt; 消去律

$ \\ $ <!--more-->



#### 1.1.2 子群 

#### 1.1.2.1 定义

1. 对运算具有封闭性
2. 包含单位元
3. 每个元素都有逆元

$ \\ $

#### 1.1.2.2 正规子群 

$ N \trianglelefteq G $

$ \iff  $ $ \forall a\in N,g\in G \quad gag^{-1}\in G $ $ \\ $ 

$ \iff  $ $ gNg^{-1}=N $

$ \iff $ $ gN=Ng $

$ \\ $

#### 1.1.3 同态 

两个群中与合成法则相容的映射。

$\varphi : G\to G', s.t \\ \forall a,b \in G, \quad \varphi(ab)=\varphi(a)\varphi(b)  $

$\implies$ $\varphi$ 把单位元映射为单位元，把逆元映射为逆元

$\implies$ $ im \varphi \leqslant G', \quad \ker \varphi \trianglelefteq G$ 

$\implies$ 群同态基本定理： $G/\ker\varphi \cong im\varphi$

$ \\ $

#### 1.1.4 同构

双射群同态。

$\implies$ 第一同构定理：

 $ \varphi$ 是一个满同态， $\pi $ 是典范态射 $(canonical)$ 

则存在唯一一个同构映射$\overline \varphi : \overline G\to G' \quad  s.t. \quad \varphi=\overline\varphi \circ \pi$



- 验证 $\varphi:G\to G’$ 是同构的方法：

  只需验证 $\ker \varphi=\{1\},im\varphi=G'$

  

#### 1.1.5 陪集 

关于同余关系的等价类。

#### 1.1.5.1 左陪集 

$ H\leqslant G, a\in G, aH=\{ah|a\in H  \}$ 

$\implies$ $a\in bH \Leftrightarrow aH=bH$

$\implies$ $ |G|=[G:H]\cdot|H|$

$ \\ $

#### 1.1.5.2 拉格朗日定理 

子群的阶整除群的阶。 $i.e. |H| \biggm| |G|$

$\implies$ 素数阶群是循环群

  $ \\ $

#### 1.1.6 对应定理 

$\varphi : G\to G' $ 是一个满同态.

$ K=ker\varphi, H'\leqslant G', H\supset K$ .

$\implies$ 若 $H'$ 是正规子群，则 $H$ 也是正规子群。$\varphi$ 是满射，$H$ 是正规子群，则$H'$ 也是正规子群。

$\implies$ $\{G的含有K的子群 \}\longleftrightarrow \{G'的子群\}$

$ \\ $

#### 1.1.7 积群

$G\times G'=\{(g,g') |g\in G, g'\in G'\}$

$ \\ $

$\implies$ $r$、$s$ 互素，则 $C_{rs}\cong C_r\times C_s$

$\implies$ 命题 $2.11.4$ :

$H,K \leqslant G, let \quad f:H\times K \to G$ 是一个映射，

$def : f(h,k)=hk. \quad imf=HK=\{hk|h\in H,k\in K \} $

$then$ $f$  是一个同构   i.e  $H\times K \cong HK $ 

$ \iff$ $H\cap K={1},HK=G,\quad H\trianglelefteq G,K\trianglelefteq G.  $

$ \\ $

#### 1.1.8 商群

群$G$在正规子群$N$的陪集的集合上定义合成法则，这个运算法则使得正规子群的陪集成为一个群，称为*商群*。

$\overline G=G/N\triangleq \{ \overline g|\overline g=gN,g\in G \}$

$ \\ $

$\implies$ 典范态射：$\pi : G\to \overline G \quad g\mapsto\overline g$  	这是一个满同态。

$ \\ $



### 1.2 群作用

#### 1.2.1 轨道、稳定子

#### 1.2.1.1 定义

orbit： $O_s=\{s'\in S | s'=gs,g\in G\}$

stabilizer：$G_s=\{g\in G|gs=s\}$

$ \\ $

#### 1.2.1.2 计数公式

$|G|=|G_s|\cdot |O_s|$

$ \\ $

$\implies$  $|O_s|=[G:G_s]$

$\implies$ $|S|=|O_1|+|O_2|+\cdots +|O_k|$

$ \\ $

#### 1.2.2 对陪集的作用

#### 1.2.2.1 诱导表示

#### 1.2.3 置换表示

群$G$的置换表示送从该群到一个对称群的同态.

$\varphi : G\to S_N$

$[G在S上的作用]\leftrightarrow[置换表示]$

$ \\ $

#### 1.2.3.2 凯莱定理

每一个有限群都同构于某个置换群的子群.

如果$|G|=n$ , 则 $G\hookrightarrow S_n$

$ \\ $

#### 1.2.4 共轭作用

#### 1.2.4.1 中心化子、共轭类

中心化子：元素$x$关于共轭作用的稳定子。

$Z(x)=\{g\in G|gx=xg\}$

共轭类：$x$关于共轭作用的轨道。

$C(x)=\{x'\in G|x'=gxg^{-1},g\in G\}$

$ \\ $

$\implies$ $|G|=|Z(x)|\cdot |C(x)|$

$ \\ $

####  1.2.4.1 类方程

共轭类划分群$G$。

$ |G|=\sum\limits_{共轭类C} |C|=|Z|+\sum\limits_ {x\in g}|C(x)| $

$ \\ $

#### 1.2.5 Sylow定理

设 $|G|=n=p^e m$ .

#### 1.2.5.1 p-群相关命题

p-群：阶是素数 $p$ 的正幂的群。

- p-群 $G$ 的中心是非平凡群。

- （不动点定理）$G$是p-群，$S$ 是一个有限集合，$G$ 在 $S$ 上面作用。若$p\nmid |S|$ , 则$G$的作用有个不动点$s$， 它的稳定子是整个群。

- $p^2$ 阶群是 $Abel$ 群。

  $ \\ $

#### 1.2.5.4 Sylow-I 

阶被素数 $p$ 整除的有限群包含一个 $Sylow-p$ 子群。

$ \\ $

$=>$ 阶被素数 $p$ 整除的有限群包含一个 $p$ 阶的元素。

$ \\ $

#### 1.2.5.5 Sylow-II

(a) $G$ 的 $Sylow-p$ 子群是共轭子群。

(b) $G$的每一个p-群的子群都包含在一个 $Sylow-p$ 子群里。 

$ \\ $

$\implies$ 群 $G$ 只有一个 $Sylow-p$ 子群$\iff$这个子群是正规子群

$ \\ $

#### 1.2.5.6 Sylow-III

$G$ 的 $Sylow-p$ 子群的个数整除 $m$ 且模 $p$ 余 $1$.

$ \\ $



### 1.2.6 [自由群](https://zh.wikipedia.org/wiki/%E8%87%AA%E7%94%B1%E7%BE%A4)

群的元素的一个集合称为是*自由的*，如果其元素除了群的公理给出的关系外不满足任何别的关系。

具有自由的生成元的集合的群称为*自由群*。

$ \\ $



## 2  环论

### 2.1 环的定义 Ring

一个*环* $R$ 是一个具有两种合成法则$+$和$\times$ 的集合。

关于加法为阿贝尔群，关于乘法满足结合律。

关于加法和乘法满足分配律。

$ \\ $

**整环**（Integral Domain）：不含零因子的环。整环满足消去律。

**诺特环**：一个环是诺特环如果它的每个理想都是有限生成的。

$ \\ $

### 2.2 环同态 

从一个环到另一个环的映射，与加法和乘法的合成法则相容。

$\varphi (a+b)=\varphi(a)+\varphi(b),\quad \varphi(ab)=\varphi(a)\cdot \varphi(b)$

若环有乘法单位元，则 $\varphi(1)=1$

$ \\ $

### 2.3 理想 Ideal

- 环$R$的左理想$I$是满足下列性质的非空子集：

（1）关于加法封闭

（2）$\forall r\in R, s\in I, \quad rs\in I$

$ \\ $

- 极大理想：$M< R(M\neq R),$ 若$I\subseteq M,$ 则 $I=M$ 或 $I=R$ 。

$ \\ $

$\implies$ 整数环 $Z$ 的极大理想是有素数生成的主理想。

$\implies$ $F$ 是一个域，$F[x]$ 的极大理想是由既约的首一多项式生成的主理想

$ \\ $

### 2.4 商环, 第一同构定理

类似群论。

### 2.5 对应定理

$\varphi ：R\to R'$ 是满射环同态，则存在一个双射对应：

$\{R的含核 理想\}\leftrightarrow \{R'的理想\}$

$ \\ $

### 2.6 希尔伯特零点定理

多项式环 $\mathbf C[x_1,x_2,\cdots,x_n]$的极大理想与复$n$维空间的点一一对应。$\mathbf{C}^n $ 的一个点$a=(a_1,a_2,\cdots,c_n)$对应于映 $x_i \rightsquigarrow a_i$的代入映射 $s_a:\mathbf{C}[x_1,\cdots, x_n]\to\mathbf{C}$的核$M_a$ . 这个映射的核 $M_a$ 是由 $n$ 个线性多项式 $x_i-a_i$ 生成的理想。

$ \\ $

### 2.7 因子分解

#### 2.7.1 基本概念

- 单位 unit ：有乘法逆元
- 相伴 associate ：$a$ 和 $b$ 相伴$\iff$$(a)=(b)$
- 不可约 irreducible :  不是单位且没有真因子，因子为单位或者相伴元
- 素元 prime : $p$ 是素元 $\iff$ $p\mid ab=>p\mid a \quad or \quad p\mid b$

$ \\ $

#### 2.7.2 欧几里得整环 ED

- 有尺度函数，可进行带余除法
- 常见例子：$\mathbf{Z},F[x],\mathbf{Z}[i]$
- $ED$ is $PID$

$ \\ $

#### 2.7.3 主理想整环 PID

- 所有理想均为主理想
- 理想$(a,b)=Ra+Rb$ 的生成元 $d$ 是 $a,b$ 的最大公因子
- $\exists r,s \in R\quad s.t.\quad d=ra+sb$
- $PID$ 中，元素是不可约的当且仅当它是素的

$ \\ $

#### 2.7.4 唯一分解整环 UFD

- 分解终止，且元素的既约分解唯一
- $ED=>PID=>UFD$

$ \\ $

### 2.7 高斯引理

- 本原多项式：正次数的正系数多项式，且整数系数 $a_1, a_2,\cdots,a_n$的最大公因子是$1$。
- $f$ 是本原的$\iff$$f$ 不能被任何素数  $ p $ 整除 $\iff$ $\forall p: prime,\psi_p(f)\neq 0\quad(\psi_p为系数模素数p的同态)$
- $Gauss's$ $Lemma$ : 本原多项式的积是本原的
- 每个有理系数的正次数多项式 $f(x)$ 可唯一地写成 $f(x)=cf_0(x)$ ，其中 $c\in \mathbb{Q}$，$f_0(x)$ 是本原多项式
- 多项式环 $ \mathbf{Z}[x]$ 是唯一分解整环。每个不是 $\pm 1$ 的非零多项式 $f(x)\in\mathbf{Z}[x]$ 可以写成积的形式： $f(x)=\pm p_1\cdots p_m q_1(x)\cdots q_n(x)$ ，$p_i $ 是整素数，$q_i$ 是本原的既约多项式。

$ \\ $

### 2.8 爱森斯坦判别法

设 $f(x)=a_nx^n+\cdots+a_0$ 是一个整多项式，并设 $p$ 是一个素整数。若 $f$ 的系数满足：

(1) $p\nmid a_n$

(2) $p\mid a_{n-1},\dots,p\mid a_0$

(3) $p^2 \nmid a_0$

则 $f$ 在 $\mathbf{Q}[x]$ 中是既约的。

$ \\ $

### 2.9 模论：环上的线性代数 

#### 2.9.1 模 Module

$R$ 是一个环，$R$-模 $V$ 包含一个加法阿贝尔群与一个标量乘法 $R\times V\to V ,\quad r,v\rightsquigarrow rv $ , 满足一下条件：

$1v=v,\quad (rs)v=r(sv),\quad (r+s)v=rv+sv,\quad r(v+v')=rv+rv'.\qquad\forall r,s \in R,\quad v,v'\in V$

$ \\ $

$=>$ $\mathbf{Z}$-模 与 阿贝尔群 是等价的概念，因为一个合成法则记为加法的阿贝尔群有唯一的 方法构成 $\mathbf{Z}$ 上的一个模。

$ \\ $

#### 2.9.2 子模

在加法和标量乘法下封闭的子集。



$=>$ $R$-模 $R$ 的子模是 $R$ 的理想

$ \\ $

#### 2.9.3 商模

#### 2.9.3.1 模同态

$\varphi : V\to W\quad \varphi(v+v')=\varphi(v)+\varphi(v'),\quad \varphi(rv)=r\varphi(v)$

同态的像是子模。

$ \\ $

#### 2.9.3.2 典范态射

令 $W $ 是 $R$-模 $V$ 的子模。

$\pi : V\to \overline V\quad v\rightsquigarrow\overline v=[v+W]$ 

$\pi$ 是一个满同态，$\ker\pi =W$

$ \\ $

#### 2.9.3.3 第一同构定理 

 $f:V\to V'$ 是模满同态，同态核  $K=W$.  则 $\overline f:\overline V=V/W\to V'$ 是一个同构。

$ \\ $

#### 2.9.3.4 对应定理 

$f:V\to V'$ 是模满同态, 核为 $W$ .  存在一个一一对应：

$\{V的包含W的子模\}\leftrightarrow \{V' 的子模\}$

$ \\ $

#### 2.9.4 自由模

一个模是自由的当且仅当它有基。

设 $R$ 是一个非零交换环。

（1）一个自由模的基变换矩阵是一个可逆矩阵

（2）$R$ 上同一个自由模的两个基具有同样的元素个数

$ \\ $

#### 2.9.5 阿贝尔群结构定理

有限生成阿贝尔群 $V$ 是循环子群 $C_{d_1},\cdots,C_{d_n}$ 和一个自由阿贝尔群 $L$ 的直和：

$$V=C_{d_1}\oplus\cdots C_{d_n}\oplus L,\qquad d_i>1,d_i\mid d_{i+1}$$ 

$ \\ $

进一步分解后：

$=>$ 每一个有限生成阿贝尔群是素数幂阶循环群的直和

$ \\ $



## 3  域论

### 3.1 域 Field

### 3.1.1 域的定义

域 $F$ 具有加法和乘法两个合成法则，关于加法称为阿贝尔群 $F^+$ ，非零元关于乘法称为阿贝尔群 $F^{\times}$，关于加法和乘法满足分配律。

- 含幺交换环 $+$ 每个元素都有逆元 $=>$ 域

子域：域的子集，且关于加减乘除封闭

$ \\ $

### 3.1.2 代数元和超越元  

#### 3.1.2.1 基本概念

代数元：是一个系数属于 $F$ 的某个首一多项式的根

超越元：不是任何一个系数属于 $F$ 的某个首一多项式的根

代数元 $\alpha$ 在 $F$ 上的既约多项式 $f$ : $F[x]$ 上的首一、次数最低、以 $\alpha$ 为根的多项式

$=>$ 由 $f$ 生成的 $F[x]$ 的主理想是一个极大理想

$\alpha$ 在 $F$ 上的次数 : 既约多项式 $f$ 的次数

扩域 $K/F$ 的次数 $[K:F]$：$K$ 作为 $F$ 向量空间 $_F K$ 的维数

$ \\ $

**次数的乘法性质**：$F\subset K\subset L,\quad [L:F]=[L:K]\cdot [K:F]$

$ \\ $



#### 3.1.2.2 相关命题

- 扩域的一个元素 $\alpha$ 是 $F$ 上的代数元 $\iff$ 扩域的次数 $[F(\alpha):F]$ 有限

- $K/F$ 为 $n$ 次有限扩域，$\alpha \in K$ $=>$ $\alpha$ 在 $F$ 上是代数的，且其在 $F$ 上的次数为 $n$

- 令 $F\subset F'\subset L$ 是域. 如果 $L$ 中元素 $\alpha$ 是 $F$ 上的代数元，则它也是 $F'$ 上的代数元。如果 $\alpha$ 在 $F$ 上的次数为 $d$ , 则它在 $F'$ 上的次数最多为 $d$。

- 由有限多个代数元生成的扩域是有限扩域，一个有限扩域由有限多个代数元生成

- 如果 $K$ 是 $F$ 的扩域，则 $K$ 中所有 $F$ 上的代数元的集合构成 $K$ 的子域 （代数元加减乘除还是代数元）

- 设 $K$ 是 $F$ 上的素数 $p$ 次扩域， $\alpha \in K,\alpha\notin F$, 则 $\alpha$ 在 $F$ 上的次数为 $p$ 且 $K=F(\alpha)$ 

  $ \\ $

令 $\alpha$ 是扩域 $K/F$ 上的元素，$\alpha$ 是 $F$ 上的代数元，令 $f$ 是 $\alpha$ 在 $F$ 上的既约多项式。

- $F[\alpha]\cong F(\alpha)$ , 更一般：$F[\alpha_1,\cdots, \alpha_n]\cong F(\alpha_1,\cdots, \alpha_n)\qquad pf:Bezout $

- $[F(\alpha):F]=deg$ $f$ 

  $ \\ $

### 3.1.3 尺规作图

令 $a$ 是一个可构造的实数，则 $a$ 是一个代数数，且它在 $\mathbf{Q}$ 上的次数是 $2$ 的幂。 （“平方根塔”）

$ \\ $

### 3.1.4 扩域中的带余除法 

设 $f$ 和 $g$ 是系数属于 $F$ 的多项式， $f\neq 0$，设 $K$ 是 $F$ 的扩域。

- 在 $F[x]$ 和 $K[x]$ 中，由 $f$ 对 $g$ 作的带余除法得到相同的答案
- 在 $K[x]$ 中 $f$ 整除 $g$ $\iff$ 在 $F[x]$ 中 $f$ 整除 $g$  
- 如果 $f$ 和 $g$ 在 $K$ 上有公共根，则它们在 $F[x]$ 中不是互素的。如果 $f$ 和 $g$ 在 $K[x]$ 中不是互素的，则存在一个扩域 $L$ ，它们在其中有公共根
- 如果 $f$ 在 $F[x]$ 中是既约的且 $f$ 和 $g$ 在 $K$ 中有公共根，则 $f$ 在$F[x]$ 中整除 $g$  

$ \\ $

### 3.1.5 重根 

令 $f(x)$ 是一个系数属于 $F$ 的多项式.

存在 $K/F$ ，在其上 $f(x)$ 有重根$\iff$ $f$ 和 $f'$ 不互素

$ \\ $

$=>$ 若 $f(x)$ 是既约的，且 $char$$F=0$，则 $f$ 在 $F$ 的任意扩域中没有重根

$ \\ $

### 3.1.6 有限域

 $K$ 是有限域 ，则 $char$ $K$ $= p$（素数），$|K|=p^r\triangleq q$

#### 相关命题

- $ K $ 的元素是多项式 $x^q-x $ 的根
- 在素域 $F=\mathbf{F_p}$ 上的多项式 $x^q-x$ 的既约因子是次数整除 $r$ 的 $F[x]$ 上的既约多项式
- 所有的 $q$ 阶域是同构的
- $ K$ 的非零元素的乘法群 $K^{\times}$ 是一个 $q-1$ 阶循环群
- $K$ 内含有 $p^k$ 阶子域当且仅当 $k$ 整除 $r$
- 多项式 $x^q-x$ 在 $F$ 的任何扩域上没有重根 （导数等于 $-1$ ，与 $x^q-x$ 无公共根）
- 在多项式环 $F[x,y]$ 中，$(x+y)^q=x^q+y^q$

$ \\ $



## 4  Galois​ 理论 （部分）

### 4.1 基本概念

- 分裂域 (splitting field) ： $F$ 上 $f$ 的分裂域是扩域 $K/F$ ，使得 $f$ 在 $K$ 里完全分裂 $f=(x-\alpha_1)\cdots (x-\alpha_n),\quad \alpha_i\in K$, 且 $K=F(\alpha_1,\cdots,\alpha_n)$
- $F$$-$同构：令 $K$ 与 $K'$ 是 $F$ 的域扩张，$\sigma : K\to K'$，为限制在子域 $F$ 上为恒等映射的同构
- $Galois$ 群：有限扩张 $K$ 的 $F-$自同构构成一个群，称为 $K$ 在 $F$ 上的 $Galois$ 群 $Gal(K/F)$
- $Galois$扩张：$|Gal(K/F)|=[K:F]$ 的扩张
- 固定域：令 $H$ 是域 $K$ 的自同构群，$H$ 的固定域 $K^H$ 是由 $K$ 的每个群元素固定不动的元素集合：$K^H=\{\alpha \in K|\sigma(\alpha)=\alpha,\sigma\in H \}$





### 4.2 相关定理

#### 4.2.1 Galois​ 扩张的特征性质

令 $K/F$ 是有限扩张，设 $G$ 为它的 $Galois$ 群

$K/F$  is  $Galois$

$\iff$ $|G|=[K:F]$

$\iff$ 固定域 $K^G$ 等于 $F$

$\iff$ $K$ 是 $F$ 的分裂域



#### 4.2.2 主要定理 The Main Theorem 

令 $K$ 是域 $F$ 的 $Galois$ 扩张，设 $G$ 为它的 $Galois$ 群，则在 $G$ 的子群与中间域之间存在一一对应，这个对应把子群 $H$ 与它的固定域、中间域 $L$ 与 $K$ 在 $L$ 上的 $Galois$ 群结合起来.

$\Phi:H\rightsquigarrow K^H$  和 $ \Psi:L\rightsquigarrow G(K/L)$ 是互逆的。

即： $\Phi \circ \Psi (L)=L$, $\Psi\circ\Phi (H)=H$



#### 4.2.3 应用 

 $K/F=F(\alpha)/F$ 上的最小多项式为:

$f(x)=\displaystyle\prod\limits_{\sigma\in Gal(K/F)} (x-\sigma(\alpha))$

$ \\ $

**例：**

Let $N\geqslant 3$ ，$\xi_N$ is a primitive $n$ th root of unit.

Assume $\sigma(\xi_N)=\xi_N ^a$ where $(a,N)=1$

we have :  $\phi: Gal(\mathbb{Q}(\xi_N)/\mathbb{Q})\to (\mathbb{Z}/N\mathbb Z)^{\times}$  is bijective.

$ \phi $ is injective since $\ker \phi=1$ （identity mapping)

$\phi$ is surjective since $\forall p,(p,N)=1 ,\exists \sigma\in Gal(\mathbb{Q}(\xi_N)/\mathbb{Q}),\quad s.t.\quad \sigma(\xi_N)=\xi_N^p$

$\because \mathbb{Q}(\xi_N)$ is the splitting field of $x^N-1$ 

$\therefore \mathbb{Q}(\xi_N)/\mathbb{Q}$ is $Galois$ 

$\therefore [\mathbb{Q}(\xi_N):\mathbb{Q}]=|Gal(\mathbb{Q}(\xi_N)/\mathbb{Q})|=|(\mathbb{Z}/N\mathbb Z)^{\times}|=\varphi(N)$

And the unit polynomial is :

 $f(x)=\displaystyle\prod\limits_{\sigma\in Gal(\mathbb{Q}(\xi_N)/\mathbb{Q})}(x-\sigma(\xi_N))=\displaystyle\prod\limits_{(a,n)=1}(x-\xi_N^a)$ 



