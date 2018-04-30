---
layout: default
title: optimizer in machine learning 
tag: ml 
---
## 随机梯度下降:**Stochastic gradient descent**
shortened to **SGD**  
also known as **incremental gradient descent**,  
a stochastc approximation of the **gradient descent**
for **minimizing an objective function**  
$$Q_i$$ is the value of the loss function at $$i$$-th example  
$$Q(w)$$ is the empirical risk  
$$w:=w-\eta \nabla Q(w) = w-\eta \sum_{i=1}^{n} {\nabla Q_i(w)/n} $$

### Algorithm
	    
* Choose an initial vector of parameters w and learing rate $$\eta$$  
* Repeat:  
	* Randomly shuffle examples in the training set.
	* For i =1,2,...,n,do:
		* $$w:=w-\eta \nabla Q_i(w)  $$
* until minimum is obtained

	    
### note
A compromise between computing the true gradient and the gradient at a single example is to compute the gradient more than one training example**mini-batch**a at each-step  

## 动量方法:momentum method
### reference
> 
 Rumelhart, David E.; Hinton, Geoffrey E.; Williams, Ronald J. (8 October 1986). "Learning representations by back-propagating errors". Nature. 323 (6088): 533–536. doi:10.1038/323533a0.

Determines the next update as **a linear combination of the gradient and the previous update**  
$$\Delta w :=\alpha\Delta w - \nabla Q_i(w)$$ 
$$w:=w-\eta \nabla Q(w)$$  
**$$\eta$$** is a step size (sometimes called the learning rate in machine learning

## AdaGrad

Increases the learning rate for more sparse parameters and decreases.  
perform well where data is sparse and sparse parameters are more informative  
###  Algorithm
A base learning rate $$\eta$$, multiplied with the elements of a vector $${G_{j,j}}$$ which is the diagonal of the outer product matrix.    

$$G = \sum_{\tau=1}^{t}g_\tau g_\tau ^T$$  
where $$g_\tau = \nabla Q_i(w)$$, iteration $$\tau$$  
$$G_{j,j} = \sum_{\tau=1}^{t}{g_{\tau,j}^2}$$    
This vector is updated after every iteration
$$w:=w-\eta diag(G)^{-\frac{1}{2}} \circ g$$  
written as per-parameter updates,  
$$w_j:=w_j-\frac{\eta}{\sqrt{G_{j,j}}}g_j$$  
Each $$G_{i,i}$$ gives rise to a scaling factor for the learning rate that applies to a single parameter $$w_i$$.  
$$\sqrt{G_i}=\sqrt{\sum_{\tau=1}^{t}g_{\tau}^{2}}$$ is the $$l_2$$ norm of previous derivatives, extreme parameters updates get dampened.    
parameters that get few or small updates receive higher learning rates.  
## RMSProp  (for Root Mean Square Propagation  )

Divide the learning rate for a weight by a **running average** of the magnitudes of **recent gradients for that weight**.  
$$v(w,t):=\gamma v(w,t-1)+(1-\gamma)(\nabla Q_i(w))^2$$  
$$\gamma$$ is the forgetting factor.  
parameters are updated as,  
$$w:=w-\frac{\eta}{\sqrt{v(w,t)}}\nabla Q_i(w)$$  
Capable to work with mini-batches as well opposed to only full-batches.  
## Adam  (short for adaptive Moment estimation)  
update to RMSProp optimizer.   
In this optimization, running **averages of** both the **gradients** and **second moments of gradients** are used.   
$$m_w^{t+1}:=\beta_1m_w^{(t)}+(1-\beta _1)\nabla _wL^{(t)}$$
$$v_w^{t+1}:=\beta_2v_w^{(t)}+(1-\beta _2)(\nabla _wL^{(t)})^2$$  
$$\hat{m}_w=\frac{m_w^{t+1}}{1-\beta_1^t}$$
$$\hat{v}_w=\frac{v_w^{(t+1)}}{1-\beta_2^t}$$  
$$w^{(t+1)}:=w^{(t)}-\eta \frac{\hat{m}_w}{\sqrt{\hat{v}_w}+\epsilon}$$  
$$\beta_1^t$$ and $$\beta_2^t$$  denote the power t of  $$\beta_1$$,$$\beta_2$$.  
$$\beta_1$$,$$\beta_2$$ are the forgetting factors.  
$$\epsilon$$ is a small number used to prevent division by 0.  
Good default settings for machine learing problems ar  
$$\eta = 0.001,\beta_1=0.9,\beta_2=0.999$$ and $$\epsilon=10^{-8}$$


