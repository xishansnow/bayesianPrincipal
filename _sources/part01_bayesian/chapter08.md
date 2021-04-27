# 第八章 JAGS

本章介绍在实际应用中，我们将用来产生贝叶斯后验分布的精确近似的方法。这类方法被称为马尔可夫链蒙特卡罗(MCMC)，原因将在本章后面解释。正是MCMC算法和软件，以及快速的计算机硬件，使我们能够对现实应用进行贝叶斯数据分析，而这在30年前实际上是不可能的。

本章解释了MCMC方法的一些基本思想，在使用使MCMC方法易于应用的复杂软件之前，理解这些基本思想是至关重要的。在这一章中，我们继续推论潜在的概率θ，在给定一组观察到的抛硬币的情况下，硬币正面朝上。在第六章中，我们考虑了这样一种情况：先验分布由与似然函数共轭的函数指定，从而产生可解析求解的后验分布。在第五章中，我们考虑了这样一种情况：先验是在跨越θ值范围的密集点网格上指定的，因此后验是通过对离散值求和来数值生成的。

但在某些情况下，上述两种方法都不起作用。我们已经认识到这样一种可能性，即我们先前对θ的信念不能用贝塔分布或任何产生可解析解的后验函数的函数来充分表示。网格近似是解决这种情况的一种方法。当我们只有一个有限范围的参数时，网格近似是一个有用的过程。但是如果我们有几个参数呢？尽管到目前为止，我们只处理涉及单个参数的模型，但更典型的是，正如我们将在后面章节中看到的那样，具有涉及多个参数的模型。在这些情况下，具有合理点数的栅格无法跨越参数空间。例如，假设有一个有六个参数的模型。因此，参数空间是涉及参数值的所有组合的联合分布的六维空间。如果我们为每个有1,000个值的参数设置一个梳子，那么6维参数空间有1,0006=1,000,000,000,000,000,000,000个参数值组合，这对于任何计算机来说都太多了。在预测网格近似不起作用的情况下，我们探索了一种新的方法，称为马尔可夫链蒙特卡罗，简称MCMC。在本章中，我们将MCMC应用于估计单个参数的简单情况。在实际研究中，你可能不想将MCMC应用于这种简单的单参数模型，而是采用数学分析或网格近似。但是，在单参数的背景下了解MCMC是非常有用的。

本章介绍的方法假定先验分布由易于计算的函数指定。这仅仅意味着，如果您为θ指定一个值，则p(θ)的值很容易确定，尤其是由计算机确定。该方法还假设可以针对D和θ的任何指定值计算似然函数p(D|θ)的值。(实际上，该方法真正需要的只是可以很容易地计算出乘法常数的先验和可能性。)。换言之，该方法不需要计算贝叶斯规则分母中的困难积分。

该方法为我们产生的是后验分布p(θ|D)的近似值，其形式是从该分布中采样的大量θ值。这堆有代表性的θ值可以用来估计后验分布的中心趋势、其最高密度区间等。后验分布是通过随机产生大量的值来估计的，因此，通过类比赌场游戏中的随机事件，这种方法被称为蒙特卡罗方法。

## 7.1 用大样本逼近分布



## 7.2 大都会（METROPOLIS）算法的一个例子



## 7.3 更一般的Metropolis算法



## 7.4 吉布斯抽样：估计两种硬币偏差



## 7.5 MCMC代表性、准确性和效率



## 7.6 总结

在关注了MCMC的树之后，让我们重新透视一下贝叶斯推理的森林。回想一下，贝叶斯分析的首要目标是确定数据描述性模型中参数值的可信度。贝叶斯规则为参数值的后验分布提供了一个精确的数学公式。但确切的形式需要计算一个积分，而对于现实中复杂的模型来说，这可能是很难处理的。因此，我们使用MCMC方法来逼近后验分布，以达到任意高的精度。由于MCMC算法的最新发展，巧妙地将其应用于复杂模型的软件，以及运行它们的硬件速度令人难以置信地快，我们现在可以使用MCMC方法来分析现实中的复杂模型，而这在几十年前是不可能的。

本章重点解释MCMC的概念，并通过简单的示例说明这些概念。(用于实际应用的软件将在下一章中介绍。)。本章介绍了一个简单的大都会算法案例，该算法伪装成政客在邻近岛屿上跳跃。在离散参数值情况下，建立了一些基本的数学直觉。然后应用Metropolis算法的一种更一般的形式来估计连续参数，即硬币中的偏差。然后介绍了Gibbs抽样方法，并将其应用于两枚硬币偏差的估计。Metropolis和Gibbs方法是MCMC采样器的两种类型。还有许多其他内容没有在本章中讨论。所有的MCMC方法在无限长的时间内都收敛于后验分布的精确表示，但它们在为有限次运行中的不同模型生成代表性样本的效率上有所不同。

在第7.5节中，本章最后讨论了用于评估MCMC链是否代表后验分布以及是否足够准确的诊断学和启发式方法。图7.10和7.11显示了MCMC链的直观和数字表示，包括轨迹图、密度图、自相关图和Gelman-Rubin统计量图，以及两个数字指标ESS和MCSE。

在接下来的章节中，我们将使用为复杂模型自动设置MCMC采样器的软件。我们将不需要手动调整Metropolis采样器中的建议分布。我们将不需要推导吉布斯采样器的条件分布。我们将不需要计算出应该应用各种采样算法中的哪一个。但我们需要评估MCMC采样器的输出，并决定其是否具有足够的代表性和准确性。因此，从这一章中保留MCMC做什么的概念以及如何评估它的细节是至关重要的。

## 7.7 习题