---
title: 数学建模 模型学习
date: 2020-02-01 20:28:07
tags:
Categories:
- Mathematics 
- Mathematics Modeling
---

# 数学建模 模型学习

## 1 确定性连续模型

## 1.1 静态优化模型/微分法建模

### 1.1.1 不允许缺货的存贮模型

1. 模型假设：

   - 每天存货费用：$c_1$  元/吨
   - 每次订货费用：$c_2$  元
   - 每天货物需求量：$r$ 吨/天
   - 任意时刻 $t$ 的货物贮存量：$q(t)$
   - 订货周期：$T$  天
   - 每次订货数量：$Q$  吨

2. 模型假设：

   每次订货后库存量均匀下降：
   $$
   \frac{dq}{dt}=-r,\qquad q(0)=Q \\
   q(t)=-r\cdot t+Q
   $$
   
3. 模型建立：

   - 订货数量、订货周期、每日货物需求的关系：

   $$
   Q=r\cdot T
   $$

   

   - 每日平均花费：

   $$
   Cost(T)=\frac{1}{T}\cdot(c_2+c_1\int_0^Tq(t)dt)=\frac{c_2}{T}+\frac{1}{2}c_1 rT
   $$

   

   - 目标：$min[Cost]$

   $$
   \frac{dCost}{dT}=0\\=> T=\sqrt{\frac{2c_2}{c_1r}},\quad Q=\sqrt{\frac{2c_2r}{c_1}}
   $$

   





### 1.1.2 允许缺货的存贮模型







## 2 遗传算法 GA

### 2.1 算法流程

- 适应度函数

  目标函数，函数的最优值便是适应度最高（最适合生存）的种群的适应度

- 变异

  产生跳出局部最优解的可能





### 2.2 单目标优化

pass







## 3 综合评价方法

### 3.1 层次分析法 AHP

Analytic Hierarchy Process.

[算法流程](https://zhuanlan.zhihu.com/p/38207837)：

- 建模，确定各层次因素

- 进行单层次排序（从上往下）

  - 对于每一个上一层对元素，挨个分析每一层因素的相对重要性，构建成对比较矩阵（使用**1-9标度法**）
  - 进行一致性检验（传递性），不通过则需要调整相对重要性
  - 获得归一化的最大特征向量，最为当前层对上一层对权重向量 

- 进行层次总排序，获得最下层每个元素对最终目标的归一化权重向量（从下往上）

- 得到决策结果

  

为什么特征向量可以作为权重？

可证充分性。$AX$的列向量的第 $i$ 个元素可以作为第 $i$ 个指标的综合评价（=$\sum_j$第 $i$ 个元素对第 $j$ 个元素的重要程度$\times$ 第 $j$ 个元素的最终权重），正比于第 $i$ 个元素的最终权重（$AX=\lambda X $）



### 3.2 主成分分析 PCA

Principle Component Analysis.

应用：

- 变量较多，需要从数据中挖掘出主要成分。通过正交变换，消除变量之间的相关影响。

- 对多变量的截面数据表进行最佳综合简化。

- 对指标进行客观赋权。（从相关系数矩阵的特征值引出的信息贡献率可作为”新变量“的权重）

  

算法流程：

- 设指标变量为 $\mathbf{x}=[x_1,\cdots,x_n]$
- 将变量标准化、去除量纲：$\mathbf{\widetilde x}=\displaystyle\frac{\mathbf{x}-\mu}{\sigma}$
- 获得 $\mathbf{\widetilde x}$ 的相关系数矩阵 $R=(r_{ij})_{n\times n }$
- 计算 $R$ 的特征值 $\lambda_1\geq\cdots \geq\lambda_n$ 和对应的特征(列)向量 $\mathbf{\mu_1,\cdots\mu_n}$
- 设 $\mathbf{\mu_i}=[\mu_{1i},\cdots,\mu_{ni}]^T$, 得到新的变量：$\mathbf{y_i}=\sum_j \mu_{ji}\cdot\widetilde x_i$
- 特征值 $\lambda_i$ 的信息贡献率 $b_i=\lambda_i\big/(\sum_i \lambda_i)$, 累计贡献率 $\alpha_p=(\sum_{j=1}^p \lambda_j)\big/(\sum_i\lambda_i)$
- 根据累计贡献率挑选出主成分
- 根据信息贡献率得到基于主成分的综合评价得分：$Z=\sum_{j=1}^p b_j y_j$





### 3.3 模糊综合评价

Fuzzy Comprehension Evaluation.

应用：评价的人多的时候比较好，比如人事考核，军训打分。

#### （1）一级模糊综合评判

- 确定因素集 $U=\{u_1,\cdots,u_n\}$

- 确定各因素权重  $A=[a_1,\cdots,a_n]$

  - 主成分分析
  - [熵权法](https://zhuanlan.zhihu.com/p/28067337)（基于多个样本在指标下的离散程度赋权）
  - 专家评估
  - 众人打分

- 确定评语集 $V=\{v_1,\cdots,v_m\}$

- 对每个因素 $u_i$ 获得一个对应评语集的评价向量 $R_i=[r_{i1},\cdots,r_{im}]$, 得到模糊综合判断矩阵 $R=(r_{ij})_{n\times m}$ （$r_{ij}\%$ 的人认为第 $i$ 个因素可以达到评语 $v_j$ ）

- 综合评判 $B=A\cdot R=[b_1,\cdots, b_m]$, 可取数值最大的评语作为最终结果（最大隶属度原则）

  

#### （2）多级模糊综合评判

[例子](http://html.rhhz.net/ZGJCYJ/html/2007-03-30.htm)



### 3.4 灰色关联评估

灰色系统理论的一个分支，应用于受多种相互关联因素影响的事物和现象的综合评价问题。



### 3.5 可作为综合题练习

第1辑第3章医疗保健系统评估问题。





## 模拟/仿真方法

### 元胞自动机

制定规则，模拟。

- [模拟交通流](https://blog.csdn.net/Harrytsz/article/details/85094334)
- [模拟游客疏散](https://blog.csdn.net/weixin_39590507/article/details/86760958) 
- [比较全面地模拟游客疏散](https://github.com/chen622/Louvre)
- [模拟流言传播](https://blog.csdn.net/your_answer/article/details/79287367)







## 模型

- 贝叶斯信念网络 （概率图）

- 小世界模型

- Lotka–Volterra方程（捕食者-被捕食者方程） 可发挥创造性推广至多捕食者多被捕食者的动态网络。

- 扩散模型
  - 扩散方程
  - 高斯烟流模式：大气污染预测
  - 技术扩散模型：Bass Diffusion Model
  - 创新扩散模型：Diffusion of Innovations Theory

- 拓扑网络

  - 局部中心
  - 影响度
  - Pagerank 佩奇排名算法度量网络节中心性

- 普林斯顿海洋模型（POM） 47、48

- Forrester 世界模型 51

  

  