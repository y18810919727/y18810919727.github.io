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
$$由于\sigma ^2=D\varepsilon =E\varepsilon ^2 故可用\dfrac{1}{n}\sum\limits_{i=1}^{n}\varepsilon_i^2$$
<center>$$\hat{\sigma}^2=\sum\limits_{i=1}^n(y_i-\hat{\alpha}-\hat{\beta}x_i)^2$$</center>
#### 另一种形式:
$$Q_{min}=\sum\limits_{i=1}^n(Y_i-\hat{\eta_i})=\sum\limits_{i=1}^n(Y_i-\hat{Y})^2-\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2$$  
$$\hat{\sigma}^2=\dfrac{1}{n}Q_{min}=\sum\limits_{i=1}^n(Y_i-\hat{\eta_i})$$
$$=\sum\limits_{i=1}^n(Y_i-\hat{Y})^2-\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2$$
### 估计量的分布
#### $$\hat{\beta}$$分布
$$\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})y_i}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$  
$$Y_1,Y_2,...,Y_n为独立的正态，\hat{\beta}服从正态$$  
$$E\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})EY_i}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$
$$=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})(\alpha +\beta x_i)}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$  
$$=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})\beta x_i}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$
$$=\beta$$  
$$D\hat{\beta}=\dfrac{\sum\limits_{i=1}^n(x_i-\bar{x})^2DY_i}{[\sum\limits_{i=1}^n (x_i-\bar{x})^2]^2}$$
$$=\dfrac{\sigma ^2}{\sum\limits_{i=1}^n (x_i-\bar{x})^2}$$
<center>$$可得\hat{\beta} 分布,\hat{\beta}\sim N[\beta ,\dfrac{\sigma ^2}{\sum_{i=1}^n (x_i-\bar{x})^2}]$$</center>
#### $$ \sigma ^2估计$$
$$\hat{\sigma }^2=\dfrac{1}{n}\sum\limits_{i=1}^n(Y_i-\hat{Y})^2-\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2$$  
$$E[\sum\limits_{i=1}^n(Y_i-\hat{Y})^2]$$
$$=E[\sum\limits_{i=1}^n(\alpha +\beta x_i+\varepsilon _i-\alpha-\beta \bar{x}-\bar{\varepsilon})^2]$$
$$=E[\sum\limits_{i=1}^n[\beta (x_i-\bar{x})+(\varepsilon _i-\bar{\varepsilon})]^2]$$  
$$=\beta ^2\sum\limits_{i=1}^n (x_i-\bar{x})^2+E[\sum\limits_{i=1}^n(\varepsilon _i-\bar{\varepsilon})^2]$$  
$$=\beta ^2\sum\limits_{i=1}^n (x_i-\bar{x})^2+(n-1)\sigma ^2$$  
又  
$$E[\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2]=[D\hat{\beta}+(E\hat{\beta})^2]\sum\limits_{i=1}{n}(x_i-\bar{x})^2$$  
$$=[\dfrac{\sigma ^2}{\sum_\limits{i=1}^n (x_i-\bar{x})^2}+\beta ^2]\sum\limits_{i=1}^{n}(x_i-\bar{x})^2$$  
$$=\sigma ^2+\beta ^2\sum\limits_{i=1}^{n}(x_i-\bar{x})^2$$  
<center>$$故E\hat{\sigma }^2=\dfrac{n-2}{n}\sigma ^2$$</center>
$$记\hat{\sigma }^{*2}=\dfrac{1}{n-2}Q_{min}$$  
则$$E\hat{\sigma }^{*2}=\sigma ^2，\hat{\sigma }^{*2}为\sigma ^2的无偏估计$$  
$$\hat{\sigma }^{*2}=\dfrac{1}{n-2}\sum\limits_{i=1}^n(Y_i-\hat{Y})^2-\hat{\beta}^2\sum\limits_{i=1}^n(x_i-\bar{x})^2$$  
$$\hat{\sigma }^{*2}=\dfrac{1}{n-2}Q_{min}=\dfrac{1}{n-2}\sum\limits_{i=1}^n(Y_i-\hat{\alpha}-\hat{\beta}x_i)^2$$  
可得如下定理:  
$$\dfrac{1}{\sigma ^2}Q_{min}服从n-2自由度的\chi ^2分布$$
### 假设检验
#### 假设检验$$\beta$$
假设$$H_0:\beta =\beta _0$$
利用$$\hat{\beta} 做统计量，检验\beta 是否为\beta _0$$  
统计量$$T=\dfrac{\hat{\beta}-\beta _0}{\hat{\sigma} ^*}\sqrt{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2} \sim t(n-2)$$  
若$$|T|\ge t_\frac{a}{2} (n-2)拒绝H_0$$
##### 检验$$x和y$$是否有线性关系
假设 $$H_0:\beta =0$$  
检验该回归是否显著  
$$根据显著水平计算T=\dfrac{\hat{\beta}}{\hat{\sigma} ^*}\sqrt{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2}$$  
若$$|T|\ge t_\frac{a}{2} (n-2)说明回归显著$$
### 预测
给定$$x_0，对Y_0=\alpha +\beta x_0+\varepsilon _0 做区间估计$$  
$$因为\alpha , \beta 未知，只能用\hat{\alpha} ,\hat{\beta}来做区间估计$$  
$$记\hat{\eta }_0=\hat{\alpha}+\hat{\beta}x_0$$  
<center>$$考察Y_0-\hat{\eta}_0的分布$$</center>  
$$其中Y_0=\alpha+\beta x_0 +\varepsilon _0 服从N(0,\sigma ^2)$$  
$$\hat{\alpha}, \hat{\beta} 服从正态，所以\eta _0 也服从正态,Y_0-\eta _0 服从正态$$  
$$E(Y_0-\eta _0)=0$$  
$$D(Y_0-\hat{\eta}_0)= \sigma _2+D[\hat{\alpha}+\hat{\beta}x_0]$$  
$$=[1+\frac{1}{n}+\dfrac{(x_0-\bar{x})^2}{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2}]\sigma ^2$$  
$$故U=\dfrac{Y_0-\hat{\alpha}-\hat{\beta}x_0}{\sqrt{1+\frac{1}{n}+\dfrac{(x_0-\bar{x})^2}{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2}}\sigma } \sim N(0,1)$$  
$$\dfrac{(n-2)\hat{\sigma }^{*2}}{\sigma ^2} \sim \chi ^2(n-2)$$
<center>$$所以T=\dfrac{Y_0-\hat{\alpha}-\hat{\beta}x_0}{\sqrt{1+\frac{1}{n}+\dfrac{(x_0-\bar{x})^2}{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2}}\hat{\sigma} ^* } \sim t(n-2)$$</center>
**$$Y_0$$的置信区间为**
<center>$$\lgroup \hat{\alpha}+\hat{\beta}x_0-t_{\frac{a}{2}}(n-2)\sqrt{1+\dfrac{1}{n}+\dfrac{(x_0-\bar{x})^2}{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2}}\hat{\sigma} ^* ,\hat{\alpha}+\hat{\beta}x_0+t_{\frac{a}{2}}(n-2)\sqrt{1+\dfrac{1}{n}+\dfrac{(x_0-\bar{x})^2}{\sum\limits_{i=1}^{n}(x_i-\bar{x})^2}}\hat{\sigma} ^* \rgroup$$</center>
### 可线性化的一元非线性化回归
#### 双曲线
$$\frac{1}{y}=a +\frac{b}{x}$$  
$$u=\frac{1}{x},v=\frac{1}{y}$$  
得$$v=a+bu$$，估计$$\hat{a},\hat{b}$$  
$$得\frac{1}{y}=\hat{a}+\frac{\hat{b}}{x}$$  
#### 幂函数曲线
$$y=ax^b$$  
两边取对数$$logy=loga+blogx$$
$$u=logx,v=logy,A=loga得v=A+bu$$  
$$估计\hat{A},\hat{b},\hat{a}=10^{\hat{A}}得\hat{a}$$
#### 倒指数曲线
$$y=ae^{\frac{b}{x}}$$  
$$lny=lna+\frac{b}{x}$$
$$做代换u=\frac{1}{x},v=lny,A=lna$$  
$$得直线v=A+bu,估计\hat{A},\hat{b},\hat{a}=e^{\hat{A}}$$
