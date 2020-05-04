---
title: 监督学习
tags: notes
categories: 
  - Computer Science
  - Machine Learning
---
# Supvised Learning

## 1.Linear Regression

output hypotheses function:	$$h(x)= \theta^Tx$$

$x$  is the input vector: $$x=(x_1,x_2,\cdots,x_n)^T$$

$\theta$  is the parameter vector:	$$\theta=(\theta_1,\theta_2,\cdots,\theta_n)^T$$

$y$  is the training output 

$X$ is the training input matrix:   $$X= (x^{(1)},x^{(2)},\cdots,x^{(m)})$$

$Y$ is the training output matrix:	$$Y=(y^{(1)},y^{(2)},\cdots,y^{(m)})$$

$\\ $ 

### LMS algorithm 

- cost function:	
  $$
  J(\theta)=\frac{1}{2}\parallel{\theta^T X-Y}\parallel^2\\
          or : J(\theta)=\frac{1}{2}\sum\limits_{i=1}^{m}(h(x^{(i)})-y^{(i)})^2
          \notag
  $$

 use **matrix derivative** to minimize $J$	 

-  gradient descent :	

$$
\theta_j := \theta_j-\alpha \frac{\partial}{\partial\theta_j}J(\theta)
\notag
$$



 <!--more-->

- Newton's method:	
  $$
  \theta:=\theta-H^{-1}\nabla_\theta l(\theta)\notag
  $$
  where $H$ is the Hessian: $$\displaystyle H_{ij}=\frac{\partial^2l(\theta)}{\partial\theta_i\partial\theta_j}$$

​      



### Locally Weighted Linear Regression

cost function:   $$\displaystyle J(\theta)=\sum\limits_i w^{(i)}(y^{(i)}-\theta^T x^{(i)})^2$$

weight $w$ :  	$$w^{(i)}=exp(-(x^{(i)}-x)^2/2\tau^2)$$





## 2. Generalized Linear Models (GLM)

- ### The exponential family

$$p(y;\eta)=b(y)\exp(\eta^T T(y)-a(\eta))$$

  where $\eta$  is the canonical parameter

- #### Bernoulli distribution

- #### Gaussian distribution

- #### Possion distribution

- #### Logistic Regression

  $$h(x)=g(\theta^T x)=1/(1+e^{-\theta^T x})$$

  

 To get the parameters, assume :

$$P(y=1| x;\theta)=h(x)$$

  $$P(y=0|x;\theta)=1-h(x)$$

  then:

  $$L(\theta)=p(\vec{y}|X;\theta)$$

$$ =\prod\limits_{i=1}^m p(y^{(i)}|x^{(i)};\theta)$$   $$=\prod\limits_{i=1}^m (h(x^{(i)})^{y^{(i)}})(1-h(x^{(i)}))^{1-y^{(i)}}$$


  to maximize the likelihood, we can use gradient descent again.

  

- #### Softmax Regression

  Multi-output $\vec{y}$

  $p(y=i|x;\theta)=\frac{e^\eta_i}{\sum_{j=1}^k e^{\eta_j}}$

  


  ### ✨Common method

  **Step 1**  :	Assume a distribution

  **Step 2** :	 Fit the GLM and get  $\eta$  as well as mean $E(y;\eta)$

  in GLM, $\eta$  is assumed as $\theta^T x$

  $h(x)=E(y;\eta)=E(y|x;\theta)$

  **Step 3**	:  Estimate the parameter

  Maximize  the likelihood function $L(\theta)=p(y|x)$ and get $\theta$





## 3. Generative Learning algorithms

- #### Gaussian discriminant analysis   [多元高斯分布](https://zhuanlan.zhihu.com/p/58987388)

- #### Naive Bayes		[朴素贝叶斯](https://zhuanlan.zhihu.com/p/25493221)
  

  