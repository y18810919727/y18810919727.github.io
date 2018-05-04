---
layout: default
title: 独立性检验 chi square test
tag: statistics
---
# 独立性检验
## 列连表
两个以上变量交叉分类的频数分布表
![img1]({{"/images/2018-05-02-chiSquareTest/union_table.png"}})
## ppt下载
[ppt download](/download/goodnessOfFit.pdf)
边缘分布(行边缘$$r_1,r_2$$、列边缘$$c_1,c_2$$)，条件分布与条件频数
## 检验方法
1. 假设$$H_0$$:行列独立，根据列分布计算理论条件频数$$e_{ij}$$
2. 检验统计量$$\chi ^2=\sum_{i=1}^{r}\sum_{j=1}^{c}\frac{(f_{ij}-e_{ij})^2}{e_{ij}} \sim \chi ^2((r-1)(c-1))$$
3. 若$$\chi ^2\ge \chi _\alpha ^2$$，拒绝$$H_0$$

