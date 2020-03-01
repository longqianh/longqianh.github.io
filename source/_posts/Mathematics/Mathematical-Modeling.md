---
title: Mathematical Modeling
date: 2020-02-07 16:37:29
tags:
categories:
- Mathematics 
- Mathematics Modeling
---

# 美赛历年题目学习

## English

- a schematic diagram
- Attributes 属性



## 2016 ICM D

###  1. 关键词

信息.



### 2. 有用的理论

- 图论
  - Nodes 
    - Type : media / person node
    - Degree 
    - State : unknown, known, tired
  - Edges
    - Start node
    - End node
    - Time ( ～ communication tools )



- Pareto Principle
  - 帕雷托法则指出，约仅有20%的变因操纵着80%的局面。也就是说：所有变量中，最重要的仅有20%，虽然剩余的80%占了多数，控制的范围却远低于“关键的少数”。
  - 应用： If the news value meets the Pareto principle, then 20% of the news contains 80% of the total value of all the news in real world.

$ \\ $ <!--more-->

- Indifference Curve 无差异曲线

  - 一条表示当消费者获得同样的效用时的消费组合曲线，其斜率一般为负值，这在经济学中表明在收入与价格既定的条件下，消费者为了获得同样的效用，增加一种商品的消费就必须减少或放弃另一种商品的消费，两种商品在消费者偏好不变的条件下，不能同时减少或增加。

  - 应用：构造方程。“This function meets all the typical properties of an Indifference Curve. Thus it can be used to measure information’s inherent value based on its attributes.” 



- Product life-cycle theory ( 产品生命周期理论， PLC )
  - 产品生命是指市上的营销生命，产品和人的生命一样，要经历形成，成长，成熟，衰退这样的周期。就产品而言，也就是要经历一个开发，转移，成长，成熟，衰退的阶段。而这个周期在不同的技术水平的国家里，发生的时间和过程是不一样的，期间存在一个相互矛盾的差异和时差，正是这一时差，表现为不同国家在技术上的差距，它反映了同一产品在不同国家市场上的竞争层次的差异，从而决定了国际贸易和国际投资的变化。
  - 应用：利用产品生命周期理论模拟新通讯网络的诞生和旧通讯网络的衰落





### 3. O奖论文结构

- 引言、问题重述、假设、符号规定

- 利用图论建立通讯网络的拓扑图，微观（个人-个人）/ 宏观（媒体-个人）
- 建立信息价值模型 ，定义了信息的三个属性/类别 （极端、娱乐、新闻），利用无差异曲线和二八定律（帕雷托法则）构造出信息价值的方程，给出了评判信息是否为新闻的标准
- 建立信息流动的动态模型 ，主要给出了信息流动的过程（绘制了简易流程图）
- 利用BBC新闻的信息流动来作为模型检验和应用的例子，进行了信息的流动模拟仿真
- 利用产品生命周期理论建立信息网络更新换代的模型，用以预测2050年的信息网络变化。给网络容量下了公式定义，并给出了不同的网络性能量化指标。提出未来的三十年将出现三种新的信息网络，并给出了网络的强度（人们使用的频繁程度），然后用线性函数简化模型，给出了新的信息网络生命周期的线性函数表达式。
- 模型进一步扩展，加入了人的选择因素，引入“门槛效应”建立新的信息流动机制
- 灵敏性分析（不知道图是怎么做出来的）、模型优缺点分析



### 4. 总结

- 他们的论文解释的很多很详细，但是就是不知道图是怎么出来的，数据怎么得到的。有的地方给出了公式或者文字说了好多就过去了，似乎不用计算。
- 灵活地应用了各种经济学的模型
- 查阅了详尽资料论文，信息网络有前人的论文可借鉴
- 我们的想法：可以引入香农的信息论内容进行分析







## 2017 ICM E

### 1. 关键词

smart growth

模糊综合评价、层次分析法



### 2. 我们的想法

#### 2.1 smart growth 的10个原则（一级指标）

$U=\{U_i\mid i=1,\cdots,10\}$

给出一级指标集对应的权重向量 $A=[a_1,\cdots,a_{10}]$



#### 2.2 衡量一座城市的10大指标

$V=\{v_i\mid i=1,\cdots10\}$

对每个 $U_i$ , 取其中不同的 $s$ 个指标作为评判不同 $U_i$ 的二级指标。

可以给出 $U_i$ 的指标集对应的权重向量 $A_i=[a_1,\cdots,a_{s}]$



#### 2.3 定义评语集：成功度

$S=\{s_i\mid i=1,\cdots,m\}$



#### 2.4 综合评价

- 根据成功度对不同的二级指标作出评判，得到 10 个二级指标的 $s\times m$ 评判向量 $R_i$ ,  $ i=1,\cdots,10$ 

- 第 $i$ 个一级指标的评判结果：$B_i=A_i\cdot R_i$， 组成综合评判矩阵 $R=[B_1;\cdots;B_{10}]$

- 最终综合评判结果 $B=A\cdot R$ , 根据最大隶属度原则，取 $B$ 中最大值对应的成功度作为城市 smart growth 的成功度



## 3 O奖论文学习

### 3.1 English

propose feasible plan

To ameliorate this situation

According to the optimization model aforementioned



### 3.2 有用的东西/可学习的东西

- flow chart

- 表格里添加不同浅色背景

- 数据归一化处理方法

- AHP：层次分析法

- 友好的Latex注记方式：[添加脚注](https://www.latexstudio.net/archives/51620.html)

- Entropy Weight Method 熵权法：确定综合评价的权重

  客观赋权法，仅依赖于数据本身的离散性

- K-means clustering Algorithm ：K-均值聚类

  - 把 n 个点（可以是样本的一次观察或一个实例）划分到 k 个聚类中，使得每个点都属于离他最近的均值（此即聚类中心）对应的聚类，以之作为聚类的标准。
  - 应用：（甚妙）文中利用K均值聚类方法，通过求解非线性规划问题，得到衡量城市“smart growth”不同方面程度的量化值（类似“成功度”）

  

- [SVM 和 SVR](https://zhuanlan.zhihu.com/p/33692660) 

- “ grid search algorithm ” 调整模型参数的算法（其实就是穷举）

- Time Series Forecasting

  时间序列预测,机器学习的一个重要领域

- 创新地结合SVM和时间序列预测方法（加权移动平均法），提出对未来的预测模型

- radar diagram 雷达图





### 3.3 O奖论文结构

- 引言、模型假设、符号说明
- 二级模糊综合评价，完成任务一。权重矩阵由层次分析法、“专家”评估法、熵权法获得；使用K-均值聚类方法获得城市“成功度”的量化值
- 使用雷达图、条形图介绍和对比两城市的现有发展规划，完成任务二
- 提出基于smart growth的城市发展规划，使用时间序列分析方法和支持向量机给出预测模型，完成任务三
- 根据不同城市的水平，提出不同的人口增长模型，在此基础上通过雷达图表现预测结果
- 用Matlab画了个三维图（参数1，参数2，误差）作为灵敏度分析

- 优缺点分析





## 2018 ICM D

### 关键词

充电汽车，充电网络



### 建模解题

### Task 1

Is Tesla on track to allow a complete switch to all-electric in the US? If everyone switched to all-electric personal passenger vehicles in the US, how many charging stations would be needed, and how should they be distributed between urban, suburban, and rural areas?

#### 符号说明

- 充电桩数量：$N_c$

- 汽车拥有量: $N$

- 充电汽车占有率：$\alpha$

- 在用电动汽车总数 ：$N_{EV}=\alpha\cdot N $

- 每天汽车总加油量 : $G$

- 每天内汽车总里程 $S=S(G)$

- $N_c=f(P,s,\cdots)$

  

#### 确定充电桩数量

1. 一段时间内总的充电电动汽车数量：

- 电动汽车蓄电池的充电时间是一个受使用者偏好等随机因素影响的随机变量，根据中心极限定理，可认为电动汽车的平均充电时间服从正态分布 $N(\mu,\sigma)$，即不同的充电时间 $t$ 发生的概率为 $\phi(t)$.

- $\mu,\sigma$ 和电动汽车的普及程度 、电动汽车各类型比例、不同类型电动汽车的充电时间有关，可以按两种类型的充电桩分别讨论

- 时间段 $T$ 内，在充电汽车数量：
  $$
  N_{charging}=N_{EV}\int_{T_0}^{T_0+T} \phi(t)dt
  $$

2. 设置充电桩以不改变客户的出行方式为目的，就是假设确保不改变总里程 $S$, 每天充电总需求时间 $T_R=T_R(S)$

3. 设每天每辆汽车平均充电 $m$ 次，每天充电总供给时间 $T_S=N_{charing}\cdot \Delta t \cdot m $

4. 确定 $\mu$: 推荐加油时常

5. 确定 $\sigma$

   

6. 想法二：获得美国充电站数量的历年数据，使用预测方法推出需要的充电站数量。这也可以对上面的模型进行检验。

7. 想法三：根据加油站数量等的历史数据，拟合出加油站数量在成长阶段的增长曲线。然后进行常数变异，拟合充电站的增长曲线。同样可以对上面的模型进行检验。

    

     

#### 设置充电桩位置

1. 要求：距离每个充电桩最近的充电桩在充电后可跑历程范围内 ；同时使用的充电桩消耗的功率不会使电网崩溃

2. 具体化：白天任意时段内确保 $k$ km附近有空闲的目的地充电桩；乡镇需要：乡镇内每天有空闲的目的地充电桩；公路需要：沿途在一次充电里程的后半段内有空闲的加压充电桩

3. 考虑因素：

   - 地域
     - 城市
     - 乡村
     - 城市--乡村过渡带
   - 电动汽车分布

4. 想法：

   - 利用层次分析法获得每个州的交通运输度综合评价得分，根据得分（看作权重）分配充电站数量。$N_i=N\times w_i$

   - 根据各州的电动汽车保有量和交通运输量，在每个充电站里细分提供的充电桩种类和数量

   - 先广覆盖，满足基本需求，再有针对性地根据地域和需求逐步增加数量

   - 借鉴加油站的分布

   - 由于智能充电引导系统的应用，可以假设驾驶员都可以选择最优的充电桩

   - 若有美国电动汽车充电桩的数据，可使用K-means聚类方法确定充电站的位置：“如果我们定位了50个公共充电站，则将应用K-means方法将充电时间窗的位置划分为50个簇，然后将充电站定位在每个集群的质心处。”

   - 电动汽车拥有率～所需充电里程数

     

5. The electrification rate, defined as the ratio of miles PHEVs travel in all electric mode over the total driving miles, is adopted to evaluate different location plans。

6. Time series Simulation Model

    

    

### 电动汽车拥有量预测

- Bass 扩散模型





### O奖论文学习 

#### D82504

### 1. English 

quantify the key factors’ influences

Redefine the concept of urban, suburban and rural areas

establish a functional relationship between the charger density and out chosen factors

in practice

Empirically 以经验为依据地

visualized simulation results

conduct further discussions



### 2. 有用的东西

- Markov method

- Gini coefficient 基尼系数

  判断年收入分配公平程度的指标。在0～1之间。基尼系数越小，年收入分配越平均；基尼系数越大，年收入分配越不平均。

### 3. Learn

- ‘Related Work’ Section
- 写得好：“3.1 Tesla’s Objective”

- use the completed charging network in Manhattan to estimate $c_u$
- divide the urban area to several squares, and consider the distribution of stations in each square.

- 考虑实际情况，在用K-means聚类方法时使用曼哈顿距离（$L_1$）代替传统的欧式距离
- 在对电动汽车市场占有份额建模时，采用逻辑回归模型 Logistic Model





#### D82794

### English 

from a macro perspective

Here we list the symbols and notations used in this paper, as shown in Table 1. 

folk customs 民俗

### D81402

#### 1. English



#### 2. 有用的东西

- 决策策略：Nash Equilibrium

- 经济学概念：帕累托最优

- 传播理论：Bass diffusion model

  适用于耐用消费品的分析预测。







## 论文写作

### 摘要

优秀的内容提要：对建模方法良好组织的精确的描述、获得的基本结果、你的建议。



### 数学模型

- 明确了关键假设，说明详实合理，在建模过程中起到了作用
- 从数学和文字方面对建模动机和理由进行阐述
- 估算和解释模型中的参数值
- 重点分析了题目关键点
- 用到的结果和数据的调查，以及对用到的相关科学术语很好的解释
- 是否利用真是数据验证模型，是否测试了模型的精度和鲁棒性
- 如何利用模型来告知决策者并指导他未来的决策
- 你是否真正了解你的模型。应讨论模型的优缺点：局限性、假设条件的约束及所用方法的局限性。改善模型的方法。

### 信息、视觉、图表

写作规范、明了、适当使用图表。



### 灵敏性分析

- 对参数添加呈正态分布的随机变量干扰

- 添加高斯噪声

- 交叉验证

