---
layout:     post
title:      Reading Log of "The stages of event extraction"
subtitle:   The stages of event extraction论文解读
date:       2019-01-16
author:     Kay
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - Blog 
    - Paper 
    - Event Extraction
---

### 摘要
本文提出了一种简单的模块化方法，将事件抽取分割成了几个小的sub-task以便于将各种机器学习方法运用
在这些子任务上，也可以更好地评估各个子任务对总体性能的影响。

### 事件检测流程
将事件抽取分解为一系列分类（Classification）子任务。每一个子任务可以用一个机器学习分类器（Classifier）来解决。

1. Anchor标识：在文本中找到事件的Anchor（事件的基石）并给它们标注一个事件类型。
2. 参数标识： 找到每个事件所对应的事件主体，时间，数值。
3. 属性分配： 确定每个事件所提及的情态、极性、通用性和时态属性的值。
4. 事件共指：确定哪些被检测出的事件所提及的是同一事件。

In principle, these four sub-tasks are highly interdependent,
but for the approach described here,
we do not model all these dependencies. Anchor
identification is treated as an independent task. Argument
finding and attribute assignment are each
dependent only on the results of anchor identification,
while event coreference depends on the results
of all of the other three sub-tasks.

### Anchor标识

#### 任务结构
将Anchor标识看作一个词分类任务（Word Classification Task）。

首先，一个binary classifier来判断这个词是不是anchor。被判断为“是”的词将被传入另一个multi-class classifier来
判断它属于哪一个事件类型。

#### Event Anchor的特征


### 参数标识

### 属性分配

### 事件共指
————————————————————————————————————————————————————

事件抽取的经典论文，非常详细地将事件抽取分为了几个小的sub-task，
是初入事件抽取领域的必读论文。

想着一天读完它的我真的是太天真了。
