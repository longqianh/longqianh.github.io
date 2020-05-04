---
title: Python 学习笔记
date: 2020-01-28 17:36:38
tags:
categories: 
- Computer Science
- Language Learning
- Python
---

# Python 学习笔记

## pandas library

### Day #1

df = pd.read_csv(' ')

df.head(n)

df.tail(n)

df.nlargest(n,'name')

df.nsmallest(n,'name')

df [Pd['bla bla']=='labalaba']





### Day #2

df.shape

df.columns.tolist( )

df['name'].unique( )

df = df.replace('Orig' , 'New')

df.isnull( )     // Checks if each value in the dato frame is missing

Trick: print(df.isnull().sum())      // return the total amount of missing values for each feature(column)

NaN stands for 'not a number'



**creating columns:**

df['new column name'] = fomula 

e.g. 	df['% Female'] = df['Female'] / df['Total']



df.dtypes

df.select_dtypes(['object'])



**measures of spread or distribution**

df['column name'].mean( )

df['column name'].median( )

df['column name'].mode( )

df.groupby(by='column name').agg('mean') 

 // agg stands for 'aggregate'.  group the data by the 'column name'

df['column name'].max( ) — df['column name'].min( )

df['column name'].std( )    // standard deviation 

df['column name'].var( )    // variance

df.groupby(by='column name').agg('std')



**correlation coefficient**

df.corr( )

df.corr( )['x'] ['y']





### Day #3

#### Bar Chart 条形图

df_top10 = df.nlargest(10,'Total')

df_top10.plot.bar(x='Major Name', y='Total')



#### Histograms 直方图

df.hist(column = '% Female')



#### Boxplot 箱形图 超有用

df.boxplot(column = '% Female', vert=False)



#### Scatterplots 散点图

df.plot.scatter(x='Male', y='Female')

##. . .

#### Simulation 

```python
import random
random.ranint(1,10)

for i in range(1,100):
  print(random.randint(1,10))
```



### Day #4

- generate a dataset of random numbers

```python
import random as rd
arr=[]
for i in range(100):
  value=rd.randint(1,10)
  arr.append({'value':value})
```



- **Monty Hall Game** 

  ```python
  import pandas as pd
  import random
  
  results = []
  for i in range(1000):
    prize = random.randint(1, 3)
    choice = random.randint(1, 3)
    print("We picked door " + str(choice))
  
    # Show a door that is not the winning door:
    if prize != 1 and choice != 1: showdoor = 1
    elif prize != 2 and choice != 2: showdoor = 2
    else: showdoor = 3
    print("We were shown that door " + str(showdoor) + " was a goat")
  
    # We did NOT swap the door:
    if   choice == 1 and showdoor == 2: choice = 3
    elif choice == 1 and showdoor == 3: choice = 2
  
    elif choice == 2 and showdoor == 1: choice = 3
    elif choice == 2 and showdoor == 3: choice = 1
  
    elif choice == 3 and showdoor == 1: choice = 2
    elif choice == 3 and showdoor == 2: choice = 1
      
    print("We DID swap doors.")
  
    # Check if we won:
    if prize == choice:
      print("WE WIN!!!!!!!!!!!!!!!")
      results.append( {"result": 1} )
    else:
      print(" :( ")
      results.append( {"result": 0} )
      
  df = pd.DataFrame(results)
  ```

  









## 其他

enumerate() 函数用于将一个可遍历的数据对象(如列表、元组或字符串)组合为一个索引序列，同时列出数据和数据下标，一般用在 for 循环当中



向量范数

```python
while sum(i**2 for i in f(x)) >= TOL**2:
```



列表一个溢出error的解决

```python
i = [1, 2, 3, 5, 8, 13]
j = [None] * len(i)
#j == [None, None, None, None, None, None]
k = 0

for l in i:
   j[k] = l
   k += 1
```



Python中初始化一个5 x 3每项为0的数组，最好方法是：

```python
multilist = [[0 for col in range(5)] for row in range(3)]
```



np数组索引：

A[i,j]

A[i,:i] i的前一个

A[i,i:] 算上i往后





函数中的参量似乎不是形参



if all(abs(x1[i]-x0[i]) < eps for i in range(n))



[max([abs(m[i][j]) for j in range(n)]) for i in range(n)] 



A.shape[0]和A.shape[1]



print(...,end=' ')



新的Python语法，是不支持的代码对齐中，混用TAB和空格的。所以出现上述错误提示了。



```python
map(func, seq1[, seq2,…])
```


第一个参数接受一个函数名，后面的参数接受一个或多个可迭代的序列，返回的是一个集合。
Python函数编程中的map()函数是将func作用于seq中的每一个元素，并将所有的调用的结果作为一个list返回。如果func为None，作用同zip()。





```python
print(“{:.3f}".format())
```



Matrix product of two arrays:

```python
numpy.matmul(*x1*, *x2*, */*, *out=None*, ***, *casting='same_kind'*, *order='K'*, *dtype=None*, *subok=True*[, *signature*, *extobj*]) *= *
```







```python
D = np.diag(np.diag(A)) # A的对角元构成的矩阵
L = np.tri(*np.shape(A),-1) * (-A)  # A的下三角元的相反数构成的矩阵L
U = D - L -A #A的上三角元的相反数构成的元素
M = np.linalg.inv(D-L)  #求（D-L）的逆
 
```





```python
numpy.tri(N, M=None, k=0, dtype=<class 'float'>)[source]
/*An array with ones at and below the given diagonal and zeros elsewhere.*/
/*k : int, optional
The sub-diagonal at and below which the array is filled. k = 0 is the main diagonal, while k < 0 is below it, and k > 0 is above. The default is 0.*/
np.tri(3, 5, 2, dtype=int)
array([[1, 1, 1, 0, 0],
       [1, 1, 1, 1, 0],
       [1, 1, 1, 1, 1]])
```





```python
list(enumerate('abc', 1)) 
[(1, 'a'), (2, 'b'), (3, 'c')]
```





```python
#三元运算
[on_true] if [expression] else [on_false]
x, y = 50, 25
small = x if x < y else y
```



```
xk = x.copy()
```





```python
a = [i/100.0 for i in range(10, 50)]

numpy.arange(0.1, 0.5, 0.01)
```





```python
x = np.linspace(-10,10,500)
y = f(x)
plt.plot(x,y,color="orange",label="$x^2 + 10 * sin(x) + 1$",linewidth=2)
```

获取横纵坐标的简洁写法

plot里面可以用latex！





```python
res = minimize_scalar(f, bounds = (-5, 0), method = 'bounded')
print "(-5, 0)", res.x
```

获取极值以及对应的坐标



```python
#支持中文显示
from pylab import *
mpl.rcParams['font.sans-serif'] = ['SimHei']
 
#创建数据
x = np.linspace(-5, 5, 100)
y1 = np.sin(x)
y2 = np.cos(x)
 
#创建figure窗口
plt.figure(num=3, figsize=(8, 5))
#画曲线1
plt.plot(x, y1)
#画曲线2
plt.plot(x, y2, color='blue', linewidth=5.0, linestyle='--')
#设置坐标轴范围
plt.xlim((-5, 5))
plt.ylim((-2, 2))
#设置坐标轴名称
plt.xlabel('xxxxxxxxxxx')
plt.ylabel('yyyyyyyyyyy')
#设置坐标轴刻度
my_x_ticks = np.arange(-5, 5, 0.5)
my_y_ticks = np.arange(-2, 2, 0.3)
plt.xticks(my_x_ticks)
plt.yticks(my_y_ticks)
 
#显示出所有设置
plt.show()

```



python添加元素

```python
p_arr = np.concatenate((p_arr,[p_])) # 先将p_变成list形式进行拼接，注意输入为一个tuple
p_arr = np.append(p_arr,p_) #直接向p_arr里添加p_
#注意一定不要忘记用赋值覆盖原p_arr不然不会变
```





Np.cos 自变量是弧度

卡西欧计算器cos自变量是角度





当函数要接受元组或者字典参数时，它分别使用*和**前缀。

如果使用**前缀，多余的参数会被认为是字典.







## 绘制三维图

```python 
fig = plt.figure()
ax = Axes3D(fig)
X = np.meshgrid(X)
Y = np.meshgrid(Y)
Z = f(X,Y)
ax.plot_surface(X,Y,Z,cmap=plt.get_cmap('rainbow'))
```





## 聚类分析 

### 1. K-均值聚类

划分式聚类方法。

已知要分点聚类数，随机生成类数个质心，从质心出发逐渐分类

- 生成 KMeans 类
- 使用 KMeans 中的 fit_predict 函数直接得聚类后各点对应的类标签

```python
from sklearn.datasets import make_blobs
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# 生成n_samples个点对,data[1]是每个成员的整数标签(类别)
data = make_blobs(n_samples=500, n_features=2, centers=8,
                  cluster_std=1.6, random_state=50)
points = data[0]
fig1 = plt.figure()  # 生成画布
fig1 = plt.scatter(points[:, 0], points[:, 1], c=data[1],
                   cmap='viridis')
plt.title('before')
plt.xlim(-15, 15)
plt.ylim(-15, 15)

# create kmeans object
kmeans = KMeans(n_clusters=8)

# print location of clusters learned by kmeans object
# print(kmeans.cluster_centers_)

km_res = kmeans.fit_predict(points)

fig2 = plt.figure()
fig2 = plt.scatter(points[:, 0], points[:, 1], c=km_res,
                   cmap='viridis')  # c:color 按data[1]给每个点对应的颜色
plt.title('after')
plt.xlim(-15, 15)
plt.ylim(-15, 15)
plt.show()
```



### 2. 层次分析聚类

层次化聚类方法。

从每个点各为一类开始，“归并”。

步骤：

- 生成距离矩阵：pdist函数
- 进行层次聚类，使用ward提出的离差平方和方法效果较好： linkage函数。 注：返回的Z的第一列和第二列代表聚集的两类的序列号，第三列代表第一列和第二列序号所代表的集群在聚集时的距离(与层次聚类图的高度相等)，第四列代表聚集时所包含的原始数据的个数
- 绘制树状图 dendrogram 函数 

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import scipy
import scipy.cluster.hierarchy as sch


# 生成待聚类的数据点,这里生成了20个点,每个点4维:
points = scipy.randn(20, 4)

# 生成点与点之间的距离矩阵,这里用的欧氏距离:
disMat = sch.distance.pdist(points, 'euclidean')
# 进行层次聚类:
Z = sch.linkage(disMat, method='ward')
# 将层级聚类结果以树状图表示出来并保存为plot_dendrogram.png
P = sch.dendrogram(Z)
plt.savefig('plot_dendrogram.png')

# 根据linkage matrix Z得到聚类结果:
cluster = sch.fcluster(Z, t=4, criterion='maxclust')#t表示最大聚类簇数
print("Original cluster by hierarchy clustering:\n", cluster)

plt.show()
```





### 3. 应用

首先使用变量聚类法找出相关度较低的“主变量”（主要指标），删除主变量之外的次变量，然后根据主变量使用样本聚类分析法进行样本分类。





## 主成分分析 PCA

Principle Component Analysis. 将相关度很高的向量转化为相关度较低的向量。

Python 实现：

直接调库：**sklearn.decomposition.PCA** （类）

参数：

- n_component : 想要将到的维数；或者规定主成分的累计贡献率阀值（percentage）
- whiten: 是否白化，即归一化
- explained_variance_ : 代表降维后的各主成分的方差值。方差值越大，则说明越是重要的主成分。
- explained_variance_ratio_ : 代表降维后的各主成分的方差值占总方差值的比例(累计贡献率)
- Y = fit_transform(X) 利用主成分分析方法对数据降维，返回对X降维后的矩阵: X.shape=(n_samples,n_features); Y.shape=(n_samples,n_components)
- fit(X) 利用主成分分析法对X降维和变换，X已经改变
- transform(X) 返回 n_samples$\times$ n_components 的切掉后面的矩阵

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA

x = np.array([[1, 2], [1, 4], [5, 8]])
pca = PCA(n_components=0.9)
y = pca.fit_transform(x)
print("累计贡献率：", pca.explained_variance_ratio_)
print("变换后的x", y)
#or:
#pca.fit(x)
#y=pca.transform(x)
```



（numpy练习）

```python
import numpy as np

# 归一化
def stdData(dataMat):
    meanVal = np.mean(dataMat, axis=0)  # 按列求均值，即求各个特征的均值
    _, n = dataMat.shape
    stdval = np.std(dataMat, axis=0)
    newData = (dataMat - meanVal)
    for i in range(n):
        newData[:, i] /= stdval[i]
    return newData


def percentage2n(eigVals, percentage):
    sortEig = np.sort(eigVals)  # 升序
    sortEig = sortEig[-1::-1]  # 逆转，即降序
    arraySum = sum(sortEig)
    tmpSum = 0
    num = 0
    contribute = []  # 信息贡献率
    for i in sortEig:
        contribute.append(i / arraySum)
    contribute = np.array(contribute)
    for i in sortEig:
        tmpSum += i
        num += 1
        if tmpSum >= arraySum * percentage:
            return num, contribute

#主成分分析
def PCA(dataMat, percentage=0.9):
    newData = stdData(dataMat)
    corMat = np.corrcoef(newData, rowvar=0)
    # 求特征值和特征向量,特征向量是按列放的，即一列代表一个特征向量
    eigVals, eigVects = np.linalg.eig(np.mat(corMat))
    eigValIndice = np.argsort(eigVals)  # 对特征值从小到大排序
    n, contribute = percentage2n(eigVals, percentage)  # 达到累积贡献率百分比的n,默认90%
    n_eigValIndice = eigValIndice[-1:-(n + 1):-1]  # 最大的n个特征值的下标
    n_eigVect = eigVects[:, n_eigValIndice]  # 最大的n个特征值对应的特征向量
    lowDDataMat = newData[:,:n] * n_eigVect  # 低维特征空间的数据
    contribute = contribute[:n]
    score = np.float(contribute * lowDDataMat)  # 基于主成分分析的综合评价得分
    return lowDDataMat, score


x = np.array([[1, 2], [1, 4], [5, 8]])
print(PCA(x))
```



