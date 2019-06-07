## 遗传算法的基本概念
这是基于 进化论 而启发出来的一种很特别的 机器学习 技巧。  我最近渐渐明白到它可能是破解 strong AI 的关键。  Ben Goertzel 和我见面的谈话中也特别注重这一方向。  原来 Alan Turing 很早就看到 进化 和 machine learning 之间有明显关系，而现时机器学习的一个很有名的研究者 Leslie Valiant 也在新书 (English version) 中谈论这课题。

机器学习的目的就是要在浩瀚的 假设空间 (hypothesis space) 中寻找那些能正确地解释现实的语句。  例如婴孩可能用「有胡子就是爸爸」 来解释身边出现的人。

问题是假设空间太大，我们如同「在禾秆推里找一只针」，单靠 brute force 不是办法。

进化算法就是在很大的空间里 寻找某个 最佳答案 (optimal solution) 的一个很强的技巧。 它把需要寻找的 candidates 模拟成一个「人口」population，任由这些 candidates 在某个人工的环境下竞争， 然后，每次选取得分最高的一小撮样本，让它们「交配」，即 基因重组 (genetic recombination)，那样产生新一批的  candidates， 如此逐步推向越来越优秀的 solutions。

举个例子，研究者用进化算法进化出一些电子电路，例如用于音响的滤波器 (filter) ，其 performance 甚至比人手设计的还要优越。  而且，那电路很不规则而且难理解，人们不知道它是如何运作的，有些部分甚至有多馀的组件存在。  那是因为进化的过程中，有时一些表面上没用的「器官」在组合之后或许变有用，所以进化的结果也常保留很多「废物 junk」。

具体的算法怎样？


* 初始时，预备一个 population，可以是随机产生的。
* 对每个 candidate 进行 估值 (evaluation)，即是让这个 candidate 在人工的世界里生存。  例如我们测试它在所需的功能的表现如何。  那计分的方法叫 objective function 「目的函数」。
* 选取表现最好的 N 个 candidates，进行 变种 mutation 或 重组 recombination。  变种是作用在单个 candidate 上的，重组则需要一对 candidates。  那就涉及到我们怎样将设计空间的元素表示为「基因」，于是有所谓 表述 (representation) 的问题。  这编码是要由研究者设计的。
* 在评分的时候，可以容许那些 candidates 在环境中互相合作亦同时竞争，那叫 cooperative evolution。   我觉得 Genifer 有需要用这方法，因为在知识库中的每个知识片段，是要和其他知识互相作用，那逻辑系统才能推导出有意思的结果。  


## 待求解的问题
寻找最优解的函数表达式为
$$
f(x,y)=-20e^{-0.2\sqrt{\frac{x^2+y^2}{2}}}-e^{\frac{\cos2\pi x+\cos2\pi y}{2}}+20+e
$$

该函数的最小值为
$$f(0,0)=0$$

##一个变量的二进制串位数的确定

包括断点的区间$[a,b]$，精度$p$，共有$N$个数，则$N=\lceil\frac{a-b}{p}\rceil+1$。用$m$表示二进制位数，分析：

当$N=4$时，$m=2$，

当$N=5$时，$m=3$。

观察得 $2^{m-1}<N\leq 2^m$,故有$\log_2 N\leq m< \log_2(N+1)$,
在程序中可表示为$$ m = \lceil\log_2 N\rceil = \left\lceil\log_2 (\lceil\frac{a-b}{p}\rceil+1)\right\rceil $$ 

## 效果图
![](https://github.com/wolfbrother/HeuristicApproach/blob/master/GeneticAlgorithm/_pic1.png?raw=true)


