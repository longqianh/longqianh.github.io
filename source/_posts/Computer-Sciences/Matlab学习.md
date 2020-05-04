---
title: Matlab学习
date: 2020-03-03 16:40:36
categories: 
- Computer Science
- Language Learning
- Matlab
---



## Matlab 学习笔记

- 函数必须以end结尾。将其保存为.m 文件，即可在其他程 序中以文件名（注意不是函数名，文件名和函数名可以不同）调用该函数。

  

- 关系运算

  ```matlab
  a~=b%不等于
  a>=b%大于等于
  a<=b%小于等于
  ```

  

- 复数

  ```matlab
  a=1+2i
  z=real(a)%实部
  z=imag(a)%虚部
  z=angle(a)%辐角
  z=abs(a)%模
  z=conj(a)%共轭
  ```



- 向量操作

  ```matlab
  a=rand(1,3)
  b=rand(1,3)
  c=dot(a,b)%内积
  d=cross(a,b)%叉乘
  l=length(a)%向量长度
  median(a)%中位数
  std(a)%标准差
  s=sort(a)%排序
  %还有 min max 等
  
  ```

  

- 矩阵操作

```matlab
a=rand(5,3)
b=rand(5,3)
b=b'%转置
c=a*b%矩阵乘法
d=a.*b%逐元素相乘
m=b^3%幂
m=b.^3%点幂
size(b)%矩阵大小
b=reshape(1,15)
b=flipud(b)%上下翻转 up and down
b=fliplr(b)%左右翻转 left and right
e=diag(b)%取出b的对角元素

left_division=a/b% b*inv(a)
right_division=a\b% inv(a)*b
%X=A\B是方程A*X=B的解，X=A\B是方程X*A=B的解 
%记忆：朝向哪 逆在哪
```



- 绘图

  ```matlab
  x=linspace(1,10,100)
  y1=sin(x)
  y2=cos(x)
  y3=tan(x)
  plot(x,y1,'blue',x,y2,'LineWidth',2,'color','red')
  %要在同一图中画出多条曲线，只需将坐标依次放入plot函数即可
  axis([0 4*pi -1.2 1.2])%设置坐标轴范围
  xlim([1 2])%单独控制
  xlabel('x'); ylabel('y');
  legend('sin(x)','cos(x)');
  title('Sine and Cosine Functions');
  %title里可以使用latex语法
  %如 ：title('$y_1=\sin(4\pi t+\pi /3)$','interpreter','latex')
  % 注明解释器为latex即可
  
  %绘制子图
  subplot(2,2,1); plot(x,y1);
  subplot(2,2,2); plot(x,y2);
  subplot(2,2,3); plot(x,y3);
  ```

  

- 信号处理

  ```matlab
  %噪声
  snr=10; %Signal‐to‐noise ratio in dB.
  yn=awgn(y,snr,'measured'); % Add white Gaussian noise. 白噪声
  
  %函数
  k1=-3; k2=3; k=k1:k2; n=0;
  step=stepfun(t,t0)%t是向量形式的变量,t0表示延迟 阶跃函数
  delta=+(k==n) % 冲激函数
  stem(k,delta,'filled')% 离散函数绘制 stem为绘制杆状图
  
  %rectpuls和tripuls函数产生指定宽度和高度的矩形和三角脉冲。
  ```

  

- 其他技巧

  - nargin, nargout 的使用 

  