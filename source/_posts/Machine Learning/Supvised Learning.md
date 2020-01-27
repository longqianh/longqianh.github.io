---
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

- ### LMS algorithm 

cost function:	$$J(\theta)=\frac{1}{2}\parallel{\theta^T X-Y}\parallel^2$$
 or : $$J(\theta)=\frac{1}{2}\sum\limits_{i=1}^{m}(h(x^{(i)})-y^{(i)})^2$$

(1) use **matrix derivative** to minimize $J$	 

(2) gradient descent :	$$\theta_j := \theta_j-\alpha \frac{\partial}{\partial\theta_j}J(\theta)$$

 <!--more-->

i.e. 

```python
Repeat until convetgence {
 	for every j:
  	theta += alpha* sum_i_from_to_m {(y[i]-h(X[i]))*X[i][j]}
}
```

 

(3) Newton's method:	
								 $$\theta:=\theta-{l'(\theta)}/{l''(\theta)}$$

​				 or:	$$\theta:=\theta-H^{-1}\nabla_\theta l(\theta)$$ 

where $H$ is the Hessian: $$H_{ij}=\frac{\partial^2l(\theta)}{\partial\theta_i\partial\theta_j}$$





- ### Locally weighted linear regression

cost function:   $$J(\theta)=\sum_i w^{(i)}(y^{(i)}-\theta^T x^{(i)})^2$$

weight $w$ :  	$$w^{(i)}=exp(-(x^{(i)}-x)^2/2\tau^2)$$



realize with Matlab:

```python
function [X, y] = load_data

X = load('data/x.dat')
y = load('data/y.dat')



function y = lwlr(X_train, y_train, x, tau)

m = size(X_train,1);
n = size(X_train,2);
theta = zeros(n,1);

% compute weights
w = exp(-sum((X_train - repmat(x', m, 1)).^2, 2) / (2*tau*tau));

% #repmat# 
% #sum(,2) is to sum the row#

% perform Newton's method
g = ones(n,1);
while (norm(g) > 1e-6)
  h = 1 ./ (1 + exp(-X_train * theta));
  g = X_train' * (w.*(y_train - h)) - 1e-4*theta;
  H = -X_train' * diag(w.*h.*(1-h)) * X_train - 1e-4*eye(n);
  theta = theta - H \ g; %'\' is left matrix divide lo
end

% return predicted y
y = double(x'*theta > 0);



function plot_lwlr(X, y, tau, res)

x = zeros(2,1);
for i=1:res,
  for j=1:res,
    x(1) = 2*(i-1)/(res-1) - 1;
    x(2) = 2*(j-1)/(res-1) - 1;
    pred(j,i) = lwlr(X, y, x, tau);
  end
end

figure(1);
clf; % Clear current figure
axis off;
hold on;
imagesc(pred, [-0.4 1.3]);
plot((res/2)*(1+X(y==0,1))+0.5, (res/2)*(1+X(y==0,2))+0.5, 'ko');
plot((res/2)*(1+X(y==1,1))+0.5, (res/2)*(1+X(y==1,2))+0.5, 'kx');
axis equal; %设置屏幕高宽比，使得每个坐标轴的具有均匀的刻度间隔x
axis square; %将坐标轴设置为正方形
text(res/2 - res/7, res + res/20, ['tau = ' num2str(tau)], 'FontSize', 18);



```



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
  

  