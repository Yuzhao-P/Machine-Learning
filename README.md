# Chapter 0 README

本仓库上传机器学习实验相关代码以及报告，该文档还整理了实验相关的知识点。

# Chapter 1 KNN(K-Nearest Neighbors)——K最近邻算法

## 一、概述

第一次实验的内容是手搓KNN算法实现手写体识别，那么什么是KNN算法呢？这里附上一个B站视频链接：[什么是KNN（K近邻算法）？【知多少】_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Ma411F7Y4/?spm_id_from=333.1007.0.0&vd_source=f93db370c1345fea000ed5a0599bc6f2)，另一个：[【五分钟机器学习】环境会影响你的决策：K近邻算法（KNN)_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV13K411H7Zs/?spm_id_from=autoNext&vd_source=f93db370c1345fea000ed5a0599bc6f2)

再来一个链接手搓KNN：[04手写KNN分类算法_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV12F41177Mz/?spm_id_from=333.880.my_history.page.click&vd_source=f93db370c1345fea000ed5a0599bc6f2)

KNN是一种分类算法，“物以类聚，人以群分”，KNN算法的分类将这一句话的思想贯彻到了极致，其核心就是根据环境来对未知的对象进行分类。

**KNN算法**	给定一个训练数据集，对于一个新的输入，在训练的数据集中找到与输入实例最近邻的K个实例，如果这K个实例中的多数 都属于某一类，那么就把该输入划分到这一类中。

用比较通俗的话语来说就是你最好的朋友是什么样的人，你就是什么样的人，“近朱者赤，近墨者黑”。

> 题外话：我一直觉得这句话有一定道理，但是并不全对，毕竟那么多古理看起来相互矛盾甚至自成悖论；这个算法也一样，在一些场合下是有效的，但它不是万能的。

## 二、KNN算法三要素

**KNN算法三要素：**

- **距离**
- **K值**
- **分类决策**

我们接下来对这三个要素进行进一步的分析~【参考链接：[详细的KNN算法原理步骤_knn算法的原理和步骤-CSDN博客](https://blog.csdn.net/weixin_43179522/article/details/105665528)】

### （一）距离

KNN算法中的第一步是要找到与输入实例最近邻的K个实例，那么这就意味着我们要给出衡量“最近邻”的依据，在这里就是我们所说的“距离”啦！对于距离的衡量方法并不唯一，我们以二维空间为例进行说明：

- 欧氏距离：$d(x,y)=\sqrt{(x_1-x_2)^2+(y_1-y_2)^2}$
- 曼哈顿距离：$d(x,y)=|x_1-x_2|+|y_1-y_2|$
- 上确界距离：对象属性间的最大距离$d(x,y)=\max{(|x_1-x_2|,|y_1-y_2|)}$
- 闵式距离：$d_{12}=\sqrt[p]{\sum\limits_{k=1}^n{|x_{1k}-x_{2k}|^p}}$

> 参考链接：[距离度量 —— 闵可夫斯基距离(Minkowski Distance)_繁依Fanyi的博客-CSDN博客](https://blog.csdn.net/qq_21484461/article/details/125357968)

### （二）K值

K值的选择是KNN算法的关键，可以说这决定了最终的分类结果，在实际应用中，K值一般会选取较小的数，如1,3,5等。通常会采用**交叉验证法**来选去最优的K值。

> 交叉验证即比较不同K值时交叉验证的平均误差，选择平均误差最小的K值。

### （三）分类决策

- 投票表决——通常用于分类问题
- 加权投票——通常用于回归问题

## 三、留一法

> 令K折交叉检验方法的K等于数据集大小，即只留**一个数据样本**作为测试集，其余都为训练集，计算平均准确率。

> 参考链接：
>
> - [留一法交叉验证 Leave-One-Out Cross Validation_留一交叉验证_白水baishui的博客-CSDN博客](https://blog.csdn.net/baishuiniyaonulia/article/details/122052893)
>
> - [8种交叉验证类型的深入解释和可视化介绍 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/257808534)
> - [数据集划分方法(留出法、交叉验证)_留出法iris代码-CSDN博客](https://blog.csdn.net/qq_43468807/article/details/105757122)

## 四、其他的一些参考链接

[numpy数组旋转、排序操作笔记_numpy 数组旋转-CSDN博客](https://blog.csdn.net/xmxoxo/article/details/108843984)

[Pytorch进阶教程(2)---手把手实现CNN分类网络_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1W24y1d7tF/?spm_id_from=333.337.search-card.all.click&vd_source=f93db370c1345fea000ed5a0599bc6f2)

https://github.com/Lavita666/Pytorch-NeuralNetworks
