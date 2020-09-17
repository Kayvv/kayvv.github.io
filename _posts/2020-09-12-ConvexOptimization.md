---
layout:     post
title:      凸优化
subtitle:   贪心学院机器学习高阶训练营
date:       2020-09-12
author:     Kay
catalog: true
tags:

    - Machine Learning
---

AI问题 = 模型 Objective + 优化 Optimization
任何一个优化问题，都可以写成如下形式：
$$
\begin{align*}
&\min f_0 (x)\\
s.t.\space\space\space\space f_i(x)&≤0,  i={1,…, K}\\
 g_j(x)&=0,       j={1,…, L}
\end{align*}
$$

x满足一定条件（定义域），满足条件的x叫可行解（Feasible Solution）。

让条件满足的可行解里让目标函数最小化的x值，条件一般写成两种不同的情况。

也有没有条件的优化问题。

## 优化的分类

拿到一个问题先要通过4个放面来判断它的类别：

1. Convex Or Non-convex

   - Convex Optimization有确定的Global Optimal，而Non-Convex只能找到Better Local Optimal。

   - Non-Convex的问题通常有3种解决方法：

     1. 简单蛮力法（Brute Force）。

     2. Relax成Convex的形式。

     3. 通过算法找到更好的Local Optimal。

2. Continuous Or Discrete

   - 大多数问题都是连续问题，离散问题较少。

3. Constrained Or Unconstrained 

   - 带条件的优化，条件一般放入Objective中。
   - 对偶。

4. Smooth Or Non-smooth

   - 对于Non-smooth可以用L1正则使他平滑。
   - Sub-Gradient

## 凸优化 Convex Optimization
判断问题本身的性质：是不是凸优化？

通过Objective的定义域和值域来判断。

定义域本身需要满足凸集（Convex Set）。

### 凸集 Convex Set

**定义**：
	假设对于任意x,y∈C并且任意参数，α∈[0,1], 我们有αx+(1-α)y ∈C , 则集合为凸集。

​	a = 0.4, αx+(1-α)y = 0.4x+0.6y,这样的式子被称为Convex Combination。

**定理**：
	两个凸集的交集也是凸集(intersection of convex set is convex)

### 凸函数 Convex Function
**定义**：

​	函数的定义域domf为凸集，对于定义域里任意x,y，函数满足
$$
f(\theta x+(1-\theta)y)≤\theta f(x)+(1-\theta)f(y)
$$
**First Order Convexity Condition**：

​	假设：
$$
f:  R^n→R
$$
​	是可导的（differentiable)，则f为凸函数，的当且仅当：
$$
f(y)≥f(x)+∇(x)^T (y-x)
$$
​	对于任意 $ x,y∈domf $

**Second Order Convexity Condition**：

​	假设$f:  R^n→R$是两次可导的（twice differentiable)，则f 为凸函数，当且仅当：
​	$∇^2 f(x)≥0$
​	对于任意$x,y∈domf$

## 常见的优化问题 Optimization Problem
优化问题的5个步骤：
1. 找到变量，Decision Valuable
2. 确定模型，Objective
3. 要满足的条件，Constraint
4. 判断问题类型 
5. 解决问题，Solver

### 运输问题 Transportation Problem

线性规划（Linear Programming）

stochastic programming

### 股票组合优化 Portfolio optimization

二次规划（Quadratic Programming）

### 集合覆盖问题 Set Cover Set

## 需要补课的基础知识

* 范数
* 数据结构和算法
  * Hash
  * Tree Structure
  * Sorty (Priority Queue） 
  * DP，Greedy
  * 计算复杂度 Computational Complexity （MIT 4th Chapter），NP-Hard
  * 堆
* 

## 学习资料

- cvxopt.org
- Matrix Cookbook