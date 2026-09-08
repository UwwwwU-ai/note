> # 理论力学

***

## 分析力学

***

### 基本概念
* ___系统___  
    有相互联系的质点的集合  
* ___位形___  
    系统内所有质点位置的集合  
* ___约束___  
    限制位形变化的任何事物  
* ___自由度___  
    确定一个系统运动状态所必须的，能够独立变化的物理量的个数  
    自由度 = 3$n$ - 完整约束的个数 - 不可积分的微分约束的个数
* ___广义坐标___ $q$  
    能够 __唯一__ 确定系统位形的 __独立__ 坐标  
    广义坐标的个数（$s$）:$s = 3n - $完整约束的个数
* ___广义速度___ $\dot{q}$

***

### 约束的分类  
* ___不可解约束___  
   $$f(\vec{r_1},...,\vec{r_n};\dot{\vec{r_1}},...,\dot{\vec{r_n}};t) = 0$$
* ___可解约束___  
   $$f(\vec{r_1},...,\vec{r_n};\dot{\vec{r_1}},...,\dot{\vec{r_n}};t) \geq 0$$

* ___几何约束___  
   $$f(\vec{r_1},...,\vec{r_n};t) = 0$$  
   限制位置，微分后限制速度，微分后变成微分约束
* ___微分约束___  
   $$f(\vec{r_1},...,\vec{r_n};\dot{\vec{r_1}},...,\dot{\vec{r_n}};t) = 0$$  
  * 可积分 
  * 不可积分  

* ___完整约束___  
   几何约束、可积分的微分约束
* ___不完整约束___  
   其他约束

* __稳定约束__
$$\frac{\partial{f}}{\partial{t}} = 0$$
* __不稳定约束__
$$\frac{\partial{f}}{\partial{t}} \neq 0$$  

***

### 虚功原理

__实位移__：实际的位移$dt$  
__虚位移__：假定$t$不变（$\delta t = 0$），约束允许的位移$\delta t$
> 虚位移不止一个，是任何可能允许的位移

__虚功__：
$$\delta W = \sum_{i=1}^{n}(\vec{F_i} - \vec{R_i}) \cdot \delta \vec{r_i}$$  
__理想约束__：
$$\sum_{i=1}^{n} \vec{R_i} \cdot \delta \vec{r_i} = 0$$  
__虚功原理__：  
系统维持平衡的充要条件是：$$\sum_{i=1}^{n} \vec{F_i} \cdot \delta \vec{r_i} = 0$$  
广义坐标下可写为：
$$Q_{\alpha} = \sum_{i=1}^{n} \vec{F_i} \cdot \frac{\partial \vec{r_i}}{\partial q_{\alpha}} = 0 \qquad \vec{r_i} = x_i \vec{i} + y_i \vec{j} + z_i \vec{k}$$
保守力下可写为：
$$\vec{F_i}=-\nabla _iV=-(\frac{\partial V}{\partial x_i}\vec{i}+\frac{\partial V}{\partial y_i}\vec{j}+\frac{\partial V}{\partial z_i}\vec{k})$$
$$Q_a = -\frac{\partial V}{\partial q_{\alpha}}$$
