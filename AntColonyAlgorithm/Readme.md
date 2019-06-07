## 基本原理

* 蚂蚁$k$根据各个城市间链接路径上的信息素浓度决定其下一个访问城市，设$P_{ij}^k(t)$表示$t$时刻蚂蚁$k$从城市$i$转移到矩阵$j$的概率，其计算公式为
\begin{eqnarray*}
P_{ij}^k=
  \begin{cases}
    \frac{[\tau_{ij}(t)]^{\alpha}\cdot[\eta_{ij}(t)]^{\beta}}{\sum_{s\in allow_k}[\tau_{is}(t)]^{\alpha}\cdot[\eta_{is}(t)]^{\beta}}\!&s\in allow_k \\
    0\!& s\notin allow_k
  \end{cases}
\end{eqnarray*}

 计算完城市间的转移概率后，采用与遗传算法中一样的轮盘赌方法选择下一个待访问的城市。

* 当所有的蚂蚁完成一次循环后，各个城市间链接路径上的信息素浓度需进行更新，计算公式为
\begin{eqnarray*}
  \begin{cases}
    \tau_{ij}(t+1)=(1-\rho)\tau_{ij}(t)+\Delta\tau_{ij} \\
    \Delta\tau_{ij} = \sum_{k=1}^{n}\delta\tau_{ij}^k
  \end{cases}
\end{eqnarray*}

 其中，$\Delta\tau_{ij}^k$表示第$k$只蚂蚁在城市$i$与城市$j$连接路径上释放的信息素浓度；$\Delta\tau_{ij}$表示所有蚂蚁在城市$i$与城市$j$连接路径上释放的信息素浓度之和。
* 蚂蚁释放信息素的模型
 \begin{eqnarray*}
\Delta\tau_{ij}^k=
  \begin{cases}
    Q/L_k,&\mathrm{第k只蚂蚁从城市i访问城市j} \\
    0,&\mathrm{其他}
  \end{cases}
\end{eqnarray*}


## 效果图
![](https://github.com/wolfbrother/HeuristicApproach/blob/master/AntColonyAlgorithm/_pic1.png?raw=true)
![](https://github.com/wolfbrother/HeuristicApproach/blob/master/AntColonyAlgorithm/_pic2.png?raw=true)
