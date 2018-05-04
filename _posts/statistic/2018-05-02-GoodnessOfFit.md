---
layout: default
title: 拟合优度 Goodness of Fit
tag: statistics
---
# 拟合优度
## Introduction
$$使用\chi ^2对总体分布进行检验，根据样本的经验分布和所假设的理论分布之间的吻合程度来决定是否接受原假设，是一种非参数检验$$  
在$$用 \chi ^2检验法检验假设H_0$$时，分布类型已知，但参数未知，需要先用极大似然估计法估计参数，然后检验
## 步骤
1. 取值范围分成$$k$$个小区间，记做$$A_1,A_2,...A_k$$
2. 把样本落入第$$i$$个区间的样本个数几位$$f_i$$，称作**实测频数**，实测频数之和应为$$n$$
3. 计算总体落入每个$$A_i$$的概率$$p_i$$,$$np_i$$为落入A_i的**理论频数**  
$$f_i-np_i$$为理论分布与经验分布之间的差异  
<center>$$当n\to \infty 时,\chi ^2=\sum_{i=1}^{k}\frac{(f_i-np_i)^2}{np_i} \sim \chi ^2(k-1)$$</center>
如果理论分布$$F(x)有r$$个未知参数需要估计，则自由度为$$(k-r-1)$$
<center>$$得拒绝域为\chi ^2 >\chi _{\alpha}^2(k-1)(不需要估计参数)$$</center>
<center>$$拒绝域:\chi ^2 >\chi _{\alpha}^2(k-r-1)(需要估计r个参数)$$</center>
### tips 
该定理在$$n$$足够大时推导出的，要求，n足够大，一般不小于50，$$np_i$$不小于5，否则可适当合并区间
## 正太总体
1. 先极大似然法估计均值和标准差  
2. 对于连续概率分布，使$$np_i$$至少为5的法则划分区间 
![img1]({{"/images/2018-05-02-hypothesis_test/normalGoodness.png"}})  

## ppt下载
[ppt download](/download/goodnessOfFit.pdf)

