---
layout: default
title: 线性回归 Linear Regression
tag: statistics
---
# 一元线性回归 
$$x是可控变量，y是依赖于x的随机变量，它们的关系是$$
<center>$$Y=\alpha +\beta x+\varepsilon$$</center>
$$其中\alpha ,\beta是常数，\varepsilon \sim N(0,\sigma ^2)，X和Y之间为一元线性回归，Y \sim N(\alpha +\beta x, \sigma ^2),\beta 为回归系数$$
记$$\eta = EY=\alpha +\beta x$$
### 线性回归解决的问题
1. 用试验值对参数$$\alpha , \beta ,\sigma ^2 作点估计$$
2. 对回归系数$$\beta $$作假设检验
3. 在$$x=x_0处，对Y作区间估计$$
### 对$$\alpha , \beta , \sigma ^2$$估计 (最小二乘法)
离差平方和
<center>$$Q=\sum _{i=1}^n(y_i-\eta _i)^2$$</center>
选择参数$$\alpha , \beta 使Q最小，令Q对两个参数一阶偏导为0$$，
<center>$$\begin{cases}  
		\dfrac{\partial Q}{\partial \alpha}=-2\sum_{i=1}^{n}(y_i-\alpha -\beta)=0 \\
		\dfrac{\partial Q}{\partial \beta}=-2\sum_{i=1}^{n}(y_i-\alpha -\beta) x_i=0&			
	\end{cases}$$</center>
得到$$\hat{\alpha} ,\hat{\beta} $$
<center>$$\begin{cases}  
		\hat{\beta} = \dfrac{\bar{x}\bar{y}-\bar{xy}}{\bar{x}^2-\bar{x^2}} \\
		\hat{\alpha} = \bar{y}-\hat{\beta} \bar{x}&
	\end{cases}$$</center>
**可得$$y=\hat{\alpha} +\hat{\beta} x$$直线始终过$$(\bar{x},\bar{y})$$**
<center>$$\bar{x^2}-\bar{x}^2=\frac{1}{n}\sum_{i=1}^n x_i^2-\bar{x}^2=\frac{1}{n}\sum_{i=1}^n (x_i-\bar{x})^2$$</center>
<center>$$\bar{xy}-\bar{x}\bar{y}=\frac{1}{n}\sum_{i=1}^nx_iy_i-\bar{x}\bar{y}=\frac{1}{n}\sum_{i=1}^n$$</center>
可得$$\hat{\beta}$$另一种表示形式  
<center>$$\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})(y_i-\bar{y})}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$</center>
### $$\sigma ^2 估计$$(矩估计法)
<center>$$\hat{\sigma}^2=\sum\limits_{i=1}^n(y_i-\hat{\alpha}-\hat{\beta}x_i)^2$$</center>
#### 另一种形式:
$$Q_{min}=\sum\limits_{i=1}^n(Y_i-\hat{\eta_i})=\sum\limits_{i=1}^n(Y_i-\hat{Y})^2-\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2$$  
$$\hat{\sigma}^2=\dfrac{1}{n}Q_{min}=\sum\limits_{i=1}^n(Y_i-\hat{\eta_i})$$
$$=\sum\limits_{i=1}^n(Y_i-\hat{Y})^2-\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2$$
### 估计量的分布
$$\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})y_i}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$  
$$Y_1,Y_2,...,Y_n为独立的正态，\hat{\beta}服从正态$$  
$$E\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})EY_i}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$
$$=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})(\alpha +\beta x_i)}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$  
$$=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})\beta x_i}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$
$$=\beta$$  
$$D\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})^2DY_i}{[\sum\limits_{i=1}^n (x_i-\bar{x})^2]^2}$$
$$=\dfrac{\sigma ^2}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$
<center>$$\hat{\beta}\sim N[\beta ,\dfrac{\sigma ^2}{\sum_{i=1}^n (x_i-\bar{x})^2}]$$</center>
$ 123 $
