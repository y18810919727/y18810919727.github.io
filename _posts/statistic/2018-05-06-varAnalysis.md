---
layout: default
title: 方差分析 Analysis of Variance
tag: statistics
---
# 方差分析 
## 一元方差分析

|母体|子样|子样平均|
|:---|:-------------------------------|:-------|
|$$x_1$$|$$x_{11}$$,$$x_{12}$$...$$x_{1n_1}$$|$$\bar{x_1}$$|
|.|.|.|
|.|.|.|
|.|.|.|
|$$x_r$$|$$x_{r1}$$,$$x_{r2}$$...$$x_{rn_r}$$|$$\bar{x_r}$$|

### 假设
1. 各水平$$A_j(j=1,2,...,s)$$下的样本$$X_{1,j},X_{2,j},...,X_{n_j,j}$$来自相同的方差$$\sigma ^2 ,均值为\mu _j(j=1,2,...,s)$$的正态总体$$N(\mu _j,\sigma ^2),\mu _j 与\sigma ^2未知$$
2. 不同$$A_j$$下样本独立  

### 基于假设检验方差分析
$$H_0:\mu _1=\mu _2=...=\mu _s$$  
$$H_1:\mu _1,\mu _2,...,\mu _s不全相等$$  
$$n=\sum\limits_{j=1}^{s}n_j,\mu=\frac{1}{n}\sum\limits_{j=1}^{s}n_j\mu _j$$   
$$a_j=\mu _j-\mu , j=1,2,...;s ，代表A_j的效应，水平A_j下总体平均值与总体平均的差异$$  
#### 数学模型
$$x_{ij}=\mu +a_j+\varepsilon _{ij}$$  
$$\varepsilon _{ij}\sim N(0,\sigma ^2),各\varepsilon 独立$$  
$$i=1,2,...,n_j,j=1,2,...,s,$$  
$$\sum\limits_{j=1}^{s}n_ja_j=0$$  
假设检验  
$$H_0:a _1=a _2=...=a _s$$  
$$H_1:a _i \ne 0(i=1,2,...,r) 至少一个成立$$  

#### 离差分析法
$$\bar{x_i}=\dfrac{1}{n}\sum\limits_{j=1}^{n_i}x_{ij},\bar{x}=\dfrac{1}{n}\sum\limits_{i=1}^{r}\sum\limits_{j=1}^{n_i}x_{ij}$$  
$$总离差平方和Q_T=\sum\limits_{i=1}^{r}\sum\limits_{j=1}^{n_i}(x_{ij}-\bar{x})^2$$  
$$组内离差平方和Q_E=\sum\limits_{i=1}^{r}\sum\limits_{j=1}^{n_i}(x_{ij}-\bar{x_{i}})^2$$  
$$组间离差平方和 Q_A=\sum\limits_{i=1}^{r}n_i(\bar{x_i}-\bar{x})$$  
<center>$$Q_T=Q_E+Q_A$$</center>
$$E\dfrac{Q_E}{n-r}=\sigma ^2$$  
$$E\dfrac{Q_A}{r-1}=\sigma ^2+\dfrac{1}{r-1}\sum\limits_{i=1}^{r}n_i\delta_i^2$$  
$$可得E\dfrac{Q_A}{r-1} \ge E\dfrac{Q_E}{n-r}$$
##### 分解定理
$$Q为自由度为n的\chi ^2变量$$  
$$Q=Q_1+Q_2+...+Q_k ,Q_i为X_1,X_2,...X_n的线性组合的平方和(非负定二次型),自由度为f_i$$  
**<center>$$Q_i相互独立且为自由度为f_i的\chi ^2的充要条件为\sum\limits_{:i=1}{k}f_i=n$$</center>**

##### 离差分析表 

|来源 |<center>离差平方和</center>|自由度|均方离差|$$F值$$|  
|:-----|:---------|:-----|:-------|:--|
|组间|$$Q_A=\sum\limits_{i=1}^{r}n_i(\bar{X_i}-\bar{X})^2$$|r-1|$$S_A^2=\dfrac{Q_A}{r-1}$$|$$F=\dfrac{S_A^2}{S_E^2}$$|  
|组内|$$Q_E=\sum\limits_{i=1}^r\sum\limits_{j=1}^{n_r}(X_{ij}-\bar{X_i})^2$$|$$n-r$$|$$S_E^2=\dfrac{Q_E}{n-r}$$||  
|总和|$$Q_E=\sum\limits_{i=1}^r\sum\limits_{j=1}^{n_r}(X_{ij}-\bar{X})^2$$|n-1|||  

若$$F \ge F_a(r-1,n-r)则拒绝假设H_0，认为因素对结果有显著影响$$
##### $$对\mu _i-\mu _k作区间估计$$
$$若H_0不成立对\mu _i-\mu _k作区间估计$$  
$$\bar{X_i}-\bar{X_k} \sim N(\mu _i-\mu _k,(\frac{1}{n_i}+\frac{1}{n_k})\sigma ^2)$$  
$$T=\dfrac{\bar{X}_i-\bar{X}_k-(\mu _i-\mu _k)}{\sqrt{\dfrac{1}{n_i}+\dfrac{1}{n_k}}S_E} \sim t(n-r)$$  
$$\mu _i- \mu _k 的置信概率为1-a的置信区间为$$
<center>$$(\bar{X}_i-\bar{X}_k-t_{\frac{a}{2}}(n-r)\sqrt{\dfrac{1}{n_i}+\dfrac{1}{n_k}}S_E,\bar{X}_i-\bar{X}_k+t_{\frac{a}{2}}(n-r)\sqrt{\dfrac{1}{n_i}+\dfrac{1}{n_k}}S_E)$$</center>

