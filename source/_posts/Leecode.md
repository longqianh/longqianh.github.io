---
title: Leecode
date: 2020-03-02 01:08:57
tags:
categories:
- Computer
---

# Leecode 题目整理

### 三数之和

排序+**双指针**

```python
nums.sort()
for i in range(n):
  if i>0 and nums[i] == nums[i - 1]:	continue
  l = i + 1
  r = n - 1
  while(l < r):
    if nums[i] + nums[l] + nums[r] == 0:
      ans.append([nums[i], nums[l], nums[r]])
      while l<r and nums[r]==nums[r-1]:	r=r-1
      while l<r and nums[l]==nums[l+1]:	l=l+1
      r=r-1
      l=l+1
    elif nums[i] + nums[l] + nums[r] > 0:	r = r - 1
    else: l = l + 1
```





### 两数之和

**carry** 用得很妙, 模拟进位

```python
def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
  ans=ListNode(0)
  head=ans
  carry=0
  while l1 or l2:
  	x=l1.val if l1 else 0
  	y=l2.val if l2 else 0
  	s=x+y+carry
  	carry=s//10
  	ans.next=ListNode(s%10)
  	ans=ans.next
  	if l1:
  		l1=l1.next
  	if l2:
  		l2=l2.next
  	if carry:
  		ans.next=ListNode(carry)
  return head.next
```





## 队列

```python
#简易版本
queue=[]
queue.append(data) #入队
queue.pop(0)	#出队

#双向队列
import collections
que=collectione.deque()
que.append() 
que.appendleft()
que.insert(i,x)#在第i个位置插入x
que.popleft()
que.pop()
que.remove(val)#移除查找到的第一个val
que.count(x)#计算que中元素等于x的个数
que.rotate(n)#向右循环移动n步 
que.clear()
```







### 墙与门

BFS

满足条件=>处理=>放入队列

```python
used=[]#走过的标记不再走
rooms[tmpk][tmpt] = rooms[i][j] + 1 #step是上一个的加1
```





### 岛屿数量

BFS ：

写个bfs函数，注意每到一个点要mark。

对所有可遍历点bfs（同步更新可遍历点）, 每使用一次就找到了一个模块, cnt++。



**并查集（未）**



```python
def bfs(i, j):
 queue = deque()
 queue.appendleft((i, j))
 grid[i][j] = "0"
 while queue:
   i, j = queue.pop()
   for x, y in [[-1, 0], [1, 0], [0, -1], [0, 1]]:
    tmp_i = i + x
    tmp_j = j + y
   if 0 <= tmp_i < row and 0 <= tmp_j < col and grid[tmp_i][tmp_j] == "1":
   	grid[tmp_i][tmp_j] = "0"
    queue.appendleft((tmp_i, tmp_j))

 for i in range(row):
   for j in range(col):
     if grid[i][j] == "1":
       bfs(i, j)
       cnt += 1
      
```



### 打开转盘锁

yield 的使用











## 栈

```python
stack=[]
stack.append()
stack.pop()
stack[-1]#取出栈顶元素
```



### 最小栈

使用两个栈，一个作为**辅助栈**。





