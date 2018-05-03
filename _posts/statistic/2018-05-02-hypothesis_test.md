---
layout: default 
title: 假设检验 hypothesis test 
tag: statistics
---
# 数理统计公式整理
## 假设检验
### 母体方差已知检验母体平均数
检验正态母体平均数，假定母体$$X$$分布为$$N(\mu,\delta^2)$$，且$$\delta^2=\delta_0^2$$已知。母体上做  
<center>$$假设H_0:\mu=\mu_0 (\mu_0已知)$$</center>
给定$$\alpha$$($$\alpha$$是小概率)得$$\mu_{\frac{a}{2}}$$，抽样后平均值$$\bar{x}$$，若  
<center> $$|\bar{x}-\mu_0|\ge\mu_{\frac{a}{2}}\frac{\delta_0}{\sqrt{n}}$$ </center>  
则拒绝假设$$H_0$$，不能认为母体平均值为$$\mu_0$$
* * *
### 检验正太母体平均数(方差未知)——t检验
假定母体$$X$$分布为$$N(\mu,\delta^2)$$，且$$\delta^2=\delta_0^2$$未知。母体上做  
<center> $$假设H_0:\mu=\mu_0(\mu_0已知)$$ </center>
用$$\bar{X}$$做检验,建立统计量  
<center>$$T=\frac{\bar{X}-\mu_0}{\frac{S^*}{\sqrt{n}}}$$</center>
$$服从自由度为n-1的t分布$$  
<center>$$ |\bar{x}-\mu_0|\ge t_\frac{a}{2}(n-1)\frac{s^*}{\sqrt{n}}$$ </center>
拒绝$$H_0$$

* * *
### 对$$\delta^2检验$$
构造检验统计量:  
<center>$$\chi ^2=\frac{(n-1)s^{*2}}{\delta_0^2}$$</center>
$$服从\chi ^2(n-1)$$  
拒绝域:  
<center>$$(n-1)\frac{s^{*2}}{\delta_0^2}\leq \chi _{1-\frac{a}{2}}^2(n-1) 或 (n-1)\frac{s^{*2}}{\delta_0^2}\ge \chi _{\frac{a}{2}}^2(n-1)$$</center>

* * *
### 正太总体均值差检验
$$\bar{x},\bar{y},s_1^2,s_2^2$$分别为总体的均值和方差
#### $$\sigma _1^2=\sigma _2^2=\sigma^2未知(t检验)$$
$$H_0:\mu _1-\mu _2=\delta, H_1: \mu _1-\mu _2\ne \delta $$
$$\delta为常数，显著水平为\alpha$$
<center>$$\frac{(\bar{X}-\bar{Y})-\delta}{s_w*\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}\sim t(n_1+n_2-2)$$</center>
<center>$$ s_w=\frac{(n_1-1)s_1^2+(n_2-1)s_2^2}{(n_1+n_2-2))}$$</center>
$$P(拒绝H_0|H_0为真)=P_{\mu _1-\mu _2=\delta}(|\frac{\bar{x}-\bar{y}-\delta }{s_w \sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}|\ge t_{\frac {a}{2}} (n_1+n_2-2))=\alpha$$  
拒绝域为<center>$$\vert \frac{\bar{x}-\bar{y}-\delta }{s_w \sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}\vert \ge t_{\frac {a}{2}} (n_1+n_2-2))$$</center>
$$H_1为u_1-u_2> \delta时$$
拒绝域为<center>$$\frac{\bar{x}-\bar{y}-\delta }{s_w \sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}> t_{a} (n_1+n_2-2))$$</center>
$$H_1为u_1-u_2< \delta时$$
拒绝域为<center>$$\frac{\bar{x}-\bar{y}-\delta }{s_w \sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}\leq -t_{a} (n_1+n_2-2))$$</center>

#### 当$$\sigma _1^2 ,\sigma _2^2已知时(U检验)$$
统计量<center>$$\frac{(\bar{X}-\bar{Y})-\delta}{\sqrt{\frac{\sigma _1^2}{n_1}+\frac{\sigma _2^2}{n_2}}}\sim N(0,1)$$</center>  
拒绝域<center>$$P(拒绝H_0|H_0为真)=P_{\mu _1-\mu _2=\delta}(\vert \frac{(\bar{X}-\bar{Y})-\delta}{\sqrt{\frac{\sigma _1^2}{n_1}+\frac{\sigma _2^2}{n_2}}} \vert \ge k)=\alpha $$</center>

<center> $$\frac{(\bar{X}-\bar{Y})-\delta}{\sqrt{\frac{\sigma _1^2}{n_1}+\frac{\sigma _2^2}{n_2}}}  \ge z_{\frac{a}{2}} 或  \frac{(\bar{X}-\bar{Y})-\delta}{\sqrt{\frac{\sigma _1^2}{n_1}+\frac{\sigma _2^2}{n_2}}}  \le -z_{\frac{a}{2}}$$ </center>
* * *
### 成对数据检验
$$n对相互独立的观察结果:$$  
$$(X_1,Y_1),(X_2,Y_2),...,(X_n,Y_n)$$  
令$$D_1=X_1-Y_1,D_2=X_2-Y_2,...,D_n=X_n-Y_n$$
$$D_i\sim N(\mu_D,\sigma _D^2)$$ 样本均值$$\bar{d},s_D^2$$  
三种假设检验
1. $$H_0 : \mu _D=0,H_1 :\mu_D \ne 0$$  <center>$$t=|\frac{\bar{d}}{\frac{S_D}{\sqrt{n}}}|\ge t_{\frac{a}{2}}(n-1)$$</center>  
2. $$H_0 : \mu _D=0,H_1 :\mu_D > 0$$  <center>$$t=\frac{\bar{d}}{\frac{S_D}{\sqrt{n}}}\ge t_a(n-1)$$</center>
3. $$H_0 : \mu _D=0,H_1 :\mu_D < 0$$  <center>$$t=\frac{\bar{d}}{\frac{S_D}{\sqrt{n}}}\le -t_a(n-1)$$</center>
<center></center>
* * *
### 两个正太总体方差检验(F检验)
$$\mu_1 ,\mu_2 ,\sigma _1^2,\sigma _2^2 未知$$  
假设$$H_0:\sigma _1^2=\sigma _2^2 ,H_1:\sigma _1^2 \ne \sigma _2^2$$  
构造统计量 $$F=\frac{s_1^2/\sigma _1^2}{s_2^2/\sigma_ 2^2} \sim F(n_1-1,n_2-1)$$  
显著性水平为$$\alpha$$下，拒绝域为:  
$$\frac{s_1^2}{s_2^2}\le F_{1-\frac{a}{2}}(n_1-1,n_2-1)$$ 或
$$\frac{s_1^2}{s_2^2}\ge F_{\frac{a}{2}}(n_1-1,n_2-1)$$
![img1]({{"/images/2018-05-02-hypothesis_test/screen1.png"}})

