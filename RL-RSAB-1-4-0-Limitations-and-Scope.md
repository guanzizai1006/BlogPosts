---
title: \[强化学习\] 1.4.0 “进化方法”（Evolutionary Method）和 “决策梯度方法” (Policy Gradient Methods) 概论
categories:
    - Reinforcement Learning
    - RL-An Introduction
keywords:
    - Evolutionary Method
    - 进化方法
    - Policy Gradient Methods
    - 决策梯度方法
toc: true
date: 2018-09-20 12:59:01
---

**Abstract:**  本文介绍强化学习中的一些局限（limitation）和机遇（scope），介绍进化方法和决策梯度方法的区别和优劣
**Keywords:** Evolutionary Method，进化方法，Policy Gradient Methods，决策梯度方法


<!--more-->



# “进化方法” 和 “决策梯度方法” 概论
进化方法是我在学习“强化学习”这本书之前认为的在人工智能中必然要有的一个部分，但是本书给了我一盆冷水，本书作者认为进化算法对强化学习的作用不太明显，或者说缺点更多，不适合用作强化学习的方法。
但是我认为AI如果能达成，一定是模拟人或者动物的智慧形成过程的，即使进化方法不是学习技能（learn skills in individual lifetime）的主要方法，但是其对智慧的长期形成一定有非常重要影响，不能因为进化方法不适合强化学习的某些任务就彻底否定他，相反我们要注意他们的结合。
本书在讲述强化学习的过程中主要是围绕 Estimating Value Function展开的，但是Estimating Value Function在强化学习中不是必须的，Estimating Value Function前一篇介绍过https://face2ai.com/RL-RSAB-1-3-Elements-of-RL/。

## 进化方法(Evolution Method)

在wiki上有进化的详细解释，如果有对进化算法不了解的同学可以大概看看或者自己google 。如果用概括性的语言描述一下，大概是这个样子的：

> 进化方法，或者遗传算法是模拟生物繁殖时候基因交换，基因变异等过程来对某个Agent进行优化的方法

举个例子：我们有一个任务M，我们模拟用10000个随机生成的Agent去完成任务，这些agnet是第一代，其中只有100个完成了；那么我们重新组合这100个的“基因”（按照各种设计的方法）产生10000个新的Agent，这些Agent就是第二代，去完成任务M，有200个成功了，继续进行第三代，第四代，直到找到一组或者多组稳定的“基因”能成功完成任务，这个过程就是进化方法，其主要过程在于组合基因和淘汰不满足对象。
类似的进化过程，进化算法，以及模拟退火等优化方法都是类似的套路。

这类方法是没有 Estimating Value Function 的

这就是本文的一个关键结论。

通过我们上面例子的描述可以发现，我们的进化算法只有“生”和“死”，比如产生新的agent是生，淘汰agent则是死，agent的全部能力全部来自遗传，这从人类进化的角度来看是不对，我们并不是靠生孩子进化到如此的，每个agent在有生之年不多研究进去，我们的人类才进化到现在的文明，作者也是这个观点，而且其对agent的有生之年的学习过程（agent自我完善policy的过程，人和动物完善自己的skill的过程）更加关注。
但是进化方法也是有些作用的，在某些强化学习问题中，进化方法也是可以使用的，一般这种问题有以下特点：

1. Policy的搜索空间很小
2. Policy的搜索空间是结构化的，比较易于搜索
3. 时间充足，比如这个训练程序可以跑一个世纪


还有一种特殊的情况，就是在agent不能准确感知环境(Environment)的状态(State)的时候，进化方法很有用处.
这个也可以跟生物进化联系起来，在最初的地球，没有生物，有机物出现，第一个有机体出现，他们有任何感知能力，只能通过遗传，变异这种方式获得适应环境的生物，在变异出器官组织后，才能对环境进行感知互动，进化自己的policy

本书（本系列博客）主要重点在于agent在和环境interact的时候的“学习”，而进化方法就没这个过程，并且在interaction的过程中的细节，是agent进化的一个重要信息来源，这些细节信息使用起来会使得policy 的搜索更加高效，
所以我们可以总结一下进化方法在强化学习过程中的几个缺点：

- 忽视太多强化学习问题背后的结构信息
- 舍弃了搜索policy过程中其实是一个函数，来对应state和action（进化算法没有这个）
- 忽略了agent的lifetime的policy选择和他所处的环境和状态等信息。


虽然agent当前的state可能是错误的，就是agent可能是判断错误了（偶尔会出现这种问题），但是这并不影响这些信息（state，action等）对学习过程的帮助。

“进化方法”和“学习过程”（主要指agent自我修正调整policy的过程）在自然过程中有很多相同的特征，但是其目前看来确实不适合强化学习问题，所以本书（本系列博客）中的强化学习方法一般不包括进化方法

## 决策梯度方法(Policy Gradient Method)

这里有一个类似进化方法的学习方法，我们会在后面经常用到，这也是一个非常简单的方法，可以解决一些小的问题，叫做 “决策梯度方法”（Policy Gradient Method）
这种方法的特点是agent中的参数是有限的，换句话说，这个空间是离散且有限的，注意离散和不连续是两回事，有限的离散的空间参数个数是固定的，这样的话搜索空间会被缩小到很小，并且存在理论上的最优解，这种方法在有限的参数空间调整自己的policy来获得更好的reward，这个调整过程有点像进化算法的组合那一步，但是不同的是，这里的调整要根据agent和state之间的action来调整，而进化方法的调整方法是不关心这些信息的，所以他们有类似，但是又大不同。
决策梯度方法和其他的强化学习方法没有什么严格的定义区别，所以没有必要过于计较区分算法的归类。

## Conclusion

本文介绍了进化方法和强化学习之间的一些关系，以及决策梯度方法之间的一些知识，注意进化方法是没有Estimating Value Function 的，这是问题的关键。

## References

Sutton R S, Barto A G. Reinforcement learning: An introduction[J]. 2011.





原文地址1：[https://www.face2ai.com/RL-RSAB-1-4-0-Limitations-and-Scope](https://www.face2ai.com/RL-RSAB-1-4-0-Limitations-and-Scope)转载请标明出处
