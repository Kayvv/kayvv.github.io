---
layout:     post
title:      快速排序的三种写法
subtitle:   贪心学院机器学习初级训练营
date:       2020-10-15
author:     Kay
catalog: true
tags:
    - Python
- 算法
---



## 快速排序
```python
def quick_sort(sort_list,start_index,end_index):
    print(sort_list)
    #如果角标左侧小于右侧则开始排序，否则退出（递归的‘归’），忘写就会死循环。
    
    #我之前以为有下面的i<j就不用判断了，但那是不对的，两码事。
    
    if start_index < end_index:
        
        #基准值从左侧取第一个，这个很重要，关系到下面指针移动的顺序
        
        basic, i, j = sort_list[start_index],start_index,end_index
        while i < j:#保证左侧的index一定比右侧的小
            
            #先移动右侧的指针，因为基准值在左侧，当左右指针重合时，跟基准值交换位置的值应该小于基准值
            
            while i < j and sort_list[j] >= basic:
                #这里的i<j不能省略，因为循环里上一次j-1后有可能等于i
                
                j -= 1 
            while i < j and sort_list[i] <= basic:
                #这里的i<j不能省略，因为前面j-1后有可能等于i
                
                i += 1
            sort_list[i], sort_list[j] = sort_list[j], sort_list[i]
        #将基准值换到i，j汇合点
        
        sort_list[start_index], sort_list[i] = sort_list[i],sort_list[start_index]
        #左边递归
        
        quick_sort(sort_list, start_index, i-1)
        #右边递归
        
        quick_sort(sort_list, i+1, end_index)
```



一个基准值，左右两指针，右边遇到比基准值小的停下，左边遇到比基准值大的停下，两指针都停下时的两个数交换位置，两个指针会和的时候和基准值换位置，然后左右递归。



```python
def quick_sort2(l):
    if l == []:
        return []
    basic = l[0]
    less = quick_sort2([i for i in l[1:] if i <= basic])
    more = quick_sort2([i for i in l[1:] if i > basic])
    return less + [basic] + more
```

比较简单易懂的写法，但是时间和空间复杂度都是上一种方法的两倍多（？我不确定我没具体算）。



```python
def quick_sort3(l):
    if l == []:return []
    return quick_sort3([i for i in l[1:] if i <= l[0]]) + [l[0]] + quick_sort3([i for i in l[1:] if i > l[0]])
```

就是强行把上一种方法写到一排里，除了显示python很简洁（装X）以外并没有什么用。



## 学习资料

