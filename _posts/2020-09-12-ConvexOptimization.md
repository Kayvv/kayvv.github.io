---
layout:     post
title:      凸优化
subtitle:   贪心学院机器学习高阶训练营
date:       2020-08-28
author:     Kay
catalog: true
tags:
    - Machine Learning
---

AI问题 = 模型Objective +优化Optimization

任何一个优化问题，都可以写成如下形式：

$$Minimize f_0 (x)$$
$$s.t.    f_i (x)≤0,  i={1,…, K}$$
$$g_j (x)=0,       j={1,…, L}$$

拿到一个问题先要通过4个反面来判断它的类别：
1. Convex Or Non-convex
2. Continuous Or Discrete
3. Constrained Or Unconstrained
4. Smooth Or Non-smooth

# 凸优化 Convex Optimization
定义域，值域。
定义域

## 凸集 Convex Set

定义：
假设对于任意x,y∈C并且任意参数，α∈[0,1], 我们有αx+(1-α)y ∈C , 则集合为凸集
定理：
两个凸集的交集也是凸集(intersection of convex set is convex)

## 凸函数 Convex Function
### 凸函数定义：
 函数的定义域domf为凸集，对于定义域里任意x,y，函数满足
f(θx+(1-θ)y)≤θf(x)+(1-θ)f(y)

### First Order Convexity Condition：
假设$f:  R^n→R$是可导的（differentiable)，则f为凸函数，的当且仅当：
$f(y)≥f(x)+∇(x)^T (y-x)$
对于任意x,y∈domf

### Second Order Convexity Condition：
假设$f:  R^n→R$是两次可导的（twice differentiable)，则f 为凸函数，当且仅当：
$∇^2 f(x)≥0$
对于任意x,y∈domf

# 常见的优化问题 Optimization Problem
优化问题的5个步骤：
1. 找到变量，Decision Valuable
2. 确定模型，Objective
3. 要满足的条件，Constraint
4. 判断问题类型 
5. 解决问题，Solver

## 运输问题 Transportation Problem

## 股票组合优化 Portfolio optimization

## 集合覆盖问题 Set Cover Set

# 需要补课的基础知识

* 范数
* 数据结构和算法
  * Hash
  * Tree Structure
  * Sorty (Priority Queue） 
  * DP，Greedy
  * 计算复杂度 Computational Complexity （MIT 4th Chapter），NP-Hard
  * 堆
* 

# 学习资料

