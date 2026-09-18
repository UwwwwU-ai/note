# 光镊测力  

***

## 郎之万方程  

***

### 一般形式  
设微粒质量为 ___m___,速度为 ___v___ ,受到的力为$F_{total}$  
$$m\frac{dv}{dt} = F_{total}$$  
作用在粒子上的力一般包括：  
1. __外部势场力__ ：$F_{ext} = -\nabla U(x)$,例如光阱的简谐力、重力、静电力等。
2. __粘滞阻力（耗散力）__ ：粒子在液体中运动时，液体会施加一个与速度方向相反的阻力。在低雷诺数（微观粒子典型情况）下，阻力与速度成正比（Stokes 定律）：$$F_{drag} = -\gamma v$$
3. 随机涨落力：描述液体分子碰撞的净效应，记为 $\xi(t)$。它随时间快速涨落，统计上均值为零。  

将这三部分代入牛顿方程，得到 __一般形式的朗之万方程__ ：
$$\boxed{m\frac{dv}{dt} = -\gamma v - \nabla U(x) + \xi(t)}$$
这是一个 __随机微分方程__：由于 $\xi(t)$ 的存在，每次解出的轨迹都不同，但统计性质是确定的。
***

### 随机力$\xi (t)$的统计性质  
1. __零均值__：
$$\langle \xi(t) \rangle = 0$$
平均而言，碰撞对称地作用于粒子，没有净方向。
2. __时间无关性（白噪声）__：不同时刻的随机力不相关，因为碰撞发生的时间尺度（~$10^{-13}$ s）远小于实验观测时间尺度（~$10^{-6}$ s 以上）。数学上：
$$\langle \xi(t)\xi(t') \rangle = 2\gamma k_B T\, \delta(t-t')$$
其中 $\delta$ 是 Dirac delta 函数，$k_B$ 是玻尔兹曼常数，$T$ 是绝对温度。
3. 高斯分布：中心极限定理保证大量独立碰撞的叠加导致 $\xi(t)$ 在任意时刻服从高斯分布。


这里最关键的是噪声强度 $2\gamma k_B T$，它把两个看似独立的物理量联系了起来：

* 耗散（$\gamma$）——宏观粘滞阻力；
* 涨落（$\delta$-相关噪声）——微观随机碰撞。

这就是涨落-耗散定理（Fluctuation-Dissipation Theorem, FDT）：耗散越强，对应的热涨落也越强。若噪声强度不是这个值，平衡态就会出现问题（例如粒子不能达到麦克斯韦-玻尔兹曼分布）。

***

### 过阻尼简化

***
对于光镊中的微米粒子，我们来估算一下各项的相对大小：

* 粒子直径 $d \sim 1 \; \mu\mathrm{m}$，密度 $\rho \sim 2000 \; \mathrm{kg/m^3}$，质量 $m \sim 10^{-15}\; \mathrm{kg}$；
* 水的粘度 $\eta \sim 10^{-3}\; \mathrm{Pa\cdot s}$，摩擦系数 $\gamma \sim 10^{-8}\; \mathrm{kg/s}$；
* 因此惯性时间尺度（速度弛豫时间）：
$$\tau_m = \frac{m}{\gamma} \sim \frac{10^{-15}}{10^{-8}} = 10^{-7}\; \mathrm{s} = 0.1\; \mu\mathrm{s}$$

* 而光阱的弛豫时间 $\tau_{\text{ot}} = \gamma/\kappa$ 通常在 $10^{-4}$ 到 $10^{-2}\; \mathrm{s}$，比 $\tau_m$ 大 3–5 个数量级。

这意味着粒子的速度在极短时间内（$0.1\; \mu\mathrm{s}$）就被粘滞力耗散掉，实验上无法分辨如此快速的惯性运动。因此，在描述光阱实验的物理时，可以忽略惯性项 $m\, dv/dt$。 

令$m \, dv/dt \sim 0$,一般朗之万方程简化为：
$$0 = -\gamma v - \nabla U(x) + \xi (t)$$  
整理得到速度：
$$\frac{dx}{dt} = -\frac{1}{\gamma}\nabla U(x) + \frac{1}{\gamma}\xi (t)$$  
这就是 __过阻尼朗之万方程__，广泛用于胶体、生物物理和光镊系统。它是一阶微分方程，不再包含速度的惯性记忆。
***

### 光阱的简谐近似

***

$$F_{trap} = -\kappa x$$
$$U(x) = \frac{1}{2}\kappa x^2$$
其中 $\kappa$ 就是光阱刚度（trap stiffness），单位通常是 $\mathrm{pN/\mu m}$。这个近似在小位移范围内成立，对于大多数校准实验是足够的。  

***

### 光阱中的过阻尼郎之万方程（一维）

***

$$\frac{dx}{dt} = -\frac{\kappa}{\gamma}x + \sqrt{2D}W(t)$$
* 弛豫时间（陷阱的特征时间）：
$$\tau_{OT} = \frac{\gamma}{\kappa}$$
它表示粒子受到扰动后回到平衡位置的典型时间尺度。  
* 扩散常数：
$$D=\frac{k_BT}{\gamma}$$
这是由涨落-耗散定理得到的爱因斯坦关系。
* 白噪声 $W(t)$：满足
$$\langle W(t) \rangle = 0,\qquad \langle W(t)W(t') \rangle = \delta (t-t')$$
即标准的“数学白噪声”，其强度吸收在系数 $\sqrt{2D}$ 中。
因此，方程也可以写成：
$$\boxed{\frac{dx}{dt} = -\frac{x}{\tau_{\text{ot}}} + \sqrt{2D}\, W(t)}$$
这个方程在数学上属于 Ornstein-Uhlenbeck（OU）过程，是光镊校准的理论核心。

***

### 离散化

***
#### 1、直接离散化

实际模拟过阻尼朗之万方程时，需要将其离散化。最常用的是 Euler–Maruyama 方法：
$$x_{n+1} = x_n - \frac{\kappa}{\gamma} x_n \Delta t + \sqrt{2D\Delta t}\, w_n$$
其中 $w_n$ 是零均值、单位方差的独立高斯随机数。注意噪声项乘的是 $\sqrt{\Delta t}$，这是白噪声积分的结果。
模拟时建议选择时间步长 $\Delta t$ 远小于 $\tau_{\text{ot}}$，以保证精度。对于光镊，$\tau_{\text{ot}}$ 典型为毫秒量级，$\Delta t$ 宜在 $\mu\mathrm{s}$ 量级。

> __为什么不直接离散化，而是对$W(t)$积分后离散化__  
> 
> $W(t)$的方差是无穷大，无法通过编程表示
> $$Var(W) = \langle [W(t)-\langle W(t) \rangle]^2 \rangle = \langle W(t)^2 \rangle = \delta(0) = \infty$$  
>

> __$w_n$的来历__  
> 
> 定义标准 Wiener 过程（布朗运动）$B_t$ 如下：
> $$B_t = \int_{0}^{t}W(s)ds$$
> 考虑时间间隔 $[t, t+\Delta t]$ 上的增量：
$$\Delta B = B_{t+\Delta t} - B_t = \int_t^{t+\Delta t} W(s)\, ds$$
其均值为零：
$$\langle \Delta B \rangle = \int_t^{t+\Delta t} \langle W(s) \rangle\, ds = 0$$
其方差为：
$$\langle (\Delta B)^2 \rangle = \left\langle \int_t^{t+\Delta t} \int_t^{t+\Delta t} W(s) W(u)\, ds\, du \right\rangle$$
利用 $\langle W(s) W(u) \rangle = \delta(s-u)$，交换积分与平均：
$$\langle (\Delta B)^2 \rangle = \int_t^{t+\Delta t} \int_t^{t+\Delta t} \delta(s-u)\, ds\, du$$
先对 $u$ 积分（或对 $s$ 积分），δ函数会挑选出 $u=s$ 的点，结果是对 $s$ 从 $t$ 到 $t+\Delta t$ 积分 1：
$$\langle (\Delta B)^2 \rangle = \int_t^{t+\Delta t} ds = \Delta t$$
因此，Wiener 过程的增量 $\Delta B$ 服从均值为零、方差为 $\Delta t$ 的正态分布。即：
$$\Delta B \sim \mathcal{N}(0, \Delta t)$$
> 我们可以将其写为：
$$\Delta B = \sqrt{\Delta t}\, \varepsilon$$
其中 $\varepsilon \sim \mathcal{N}(0,1)$ 是标准正态随机变量。正是这个 $\sqrt{\Delta t}$ 因子保证了 $\Delta B$ 的方差为 $\Delta t$（因为 $\text{Var}(\sqrt{\Delta t}\,\varepsilon) = \Delta t \cdot \text{Var}(\varepsilon) = \Delta t$。
>
>现在我们回到朗之万方程：
$$\frac{dx}{dt} = a(x) + b(x) W(t)$$
其中 $a(x)=-\frac{\kappa}{\gamma}x$ 是漂移项，$b(x)=\sqrt{2D}$ 是噪声强度（这里为常数，但一般可为位置函数）。
这种含白噪声的微分方程通常被称为随机微分方程 (SDE)。其严格的数学形式应写成积分形式：
$$dx = a(x)\, dt + b(x)\, dB_t$$
其中 $dB_t$ 是 Wiener 过程的增量。这是因为白噪声 $W(t)$ 实际上是 $B_t$ 的“导数”（在分布意义下），所以 $W(t)dt$ 对应于 $dB_t$。
在数值求解时，我们采用最简单的 Euler–Maruyama 离散化：设时间步长为 $\Delta t$，则
$$x_{n+1} = x_n + a(x_n) \Delta t + b(x_n) \Delta B_n$$
其中 $\Delta B_n = B_{t_{n+1}} - B_{t_n} \sim \mathcal{N}(0, \Delta t)$。
如果我们用 $\sqrt{\Delta t}\,\varepsilon_n$ 代替 $\Delta B_n$（$\varepsilon_n \sim \mathcal{N}(0,1)$），就得到：
$$x_{n+1} = x_n + a(x_n) \Delta t + b(x_n) \sqrt{\Delta t}\, \varepsilon_n$$
对于我们的例子 $a(x)=-\frac{\kappa}{\gamma}x$，$b(x)=\sqrt{2D}$，于是：
$$x_{n+1} = x_n - \frac{\kappa}{\gamma} x_n \Delta t + \sqrt{2D} \sqrt{\Delta t}\, \varepsilon_n$$
即
$$x_{n+1} = x_n - \frac{\kappa}{\gamma} x_n \Delta t + \sqrt{2D\Delta t}\, \varepsilon_n$$

#### 2、精确离散

$$x_{n+1} = cx_n +\sigma \epsilon _n$$
其中$c = e^{-\Delta t/\tau}$，$\sigma ^2 = \frac{k_BT}{k}(1 - c^2)$，$\epsilon _n \sim N(0,1)$
>$$\frac{dx}{dt} = -\frac{\kappa}{\gamma}x + \sqrt{2D}W(t)$$
>
>同样按照上面的处理，定义：
$$B_t = \int _0^t W_sds$$
>
>可得：
$$dx = -\frac{xdt}{\tau} + \sqrt{2D} W_s dt$$
其中，$\tau = \frac{\gamma}{k}$
>即：
$$dx = -\frac{x}{\tau}dt + \sqrt{2D} dB_t$$
>设 $a = 1/\tau$，让上式左右同乘 $e^{at}$，则方程可变为：
$$d(e^{at}x) = e^{at}\sqrt{2D}dB_t$$
>两边积分得：
$$e^{a(t+\Delta t)}x_{t+\Delta t}-e^{at}x_t = \int_t^{t + \Delta t}e^{as}\sqrt{2D}dB_s$$
>即：
$$x_{t+\Delta t} = e^{-a\Delta t}x_t + \sqrt{2D} \int_t^{t + \Delta t}e^{-a(t+\Delta t-s)}dB_s$$
>令 $\eta = \sqrt{2D} \int_t^{t + \Delta t}e^{-a(t+\Delta t-s)}dB_s$，易得 $\eta$ 服从零均值正态分布，所以接下来要求解 $Var(\eta)$
>
>$$
\begin{aligned}
Var(\eta) = \; & <(\eta -<\eta>)^2> = <\eta^2> \\
& = 2D \int_t^{t+\Delta t} \int_t^{t+\Delta t}e^{-a(t + \Delta t - s)}e^{-a(t + \Delta t - u)} \delta(s-u)\, ds\, du \\
& = 2D\int_t^{t+\Delta t}e^{-2a(t + \Delta t - s)} ds \\
& = 2D \int _0^{\Delta t}e^{-2am}dm \\
& = 2D\frac{1-e^{-2a\Delta t}}{2a} \\
& = D\tau (1-e^{2\Delta t/\tau}) \\
& = \frac{k_BT}{k}(1-c^2)
\end{aligned}
$$
>
>所以$$x_{n+1} = cx_n +\sigma \epsilon _n$$
其中 $c = e^{-\Delta t/\tau}$，$\sigma ^2 = \frac{k_BT}{k}(1 - c^2)$，$\epsilon _n \sim N(0,1)$

