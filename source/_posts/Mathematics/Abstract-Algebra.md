---
title: Abstract Algebra
tags: 代数
categories:
  - Mathematics
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

子群的阶整除群的阶。 $i.e. |H| \;\biggm| |G|$



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

### 1.2.1 轨道、稳定子

#### 1.2.1.1 轨道

#### 1.2.1.2 稳定子

#### 1.2.1.3 计数公式



### 1.2.2 对陪集的作用

#### 1.2.2.1 诱导表示

#### 



### 1.2.3 置换表示

#### 1.2.3.1 置换表示

#### 1.2.3.2 凯莱定理



### 1.2.4 共轭作用

####  1.2.4.1 类方程



### 1.2.5 Sylow定理

#### 1.2.5.1 p-群

#### 1.2.5.2 不动点定理

#### 1.2.5.3 Sylow-I 

#### 1.2.5.4 Sylow-II

#### 1.2.5.5 Sylow-III



### 1.2.6 自由群





## 2. 环论

## 3. 域论

## 4. Galois

