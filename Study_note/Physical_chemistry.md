[TOC]

# 物理化学

## 化学热力学基础

### 热力学的能量守恒原理

热力学由“热”和“力”组成，其中“力”其实指的是“功”。“热”为能量转化的一种形式，即热能；”功“我们一般是说做了多少“功”，因此，“功”也是能量，但是它是指除了热能以外的能量形式。因此热力学是研究热能与其它形式能之间的转化关系的一门学科。

#### 基本概念

1. 体系与环境

   - System：将所研究的对象称之为体系或系统；
   - Surrounding：与体系有关的其余部分称为环境；
   - Open system：体系与环境之间既有能量交换又有物质交换称为敞开体系；
   - Closed system：体系与环境之间只有能量交换称为封闭体系；
   - Isolated system：体系与环境之间无能量和物质交换称为孤立体系；即体系+环境=孤立体系。

   **注意：**体系的选择是人为划分的；最常用的体系为封闭体系。

2. 体系的性质

   - Property of system：用于确定体系的各种宏观物理量称为体系的性质或者状态性质；

     - Extensive properties：广度性质的数值与体系中的物质的量成正比，具有加和性；

       如：力，面积，质量，体积，热熔等。

     - Intensive properties：强度性质通常是由两个广度性质之比构成。

       如：压力（力与面积的比值），温度，浓度，密度等。

3. 状态与状态函数

   - State：体系的物理性质和化学性质的综合表现称为体系的状态；

     如：物质的量，温度，压力，体积等。

   - State function：体系性质的数值与体系状态保持着一种函数关系称为状态函数；状态函数的改变只决定于体系的始态和终态，与路径无关；并且在数学上，状态函数具有全微分的性质：

     如气体的性质$p$,$V$,$T$之间可以写成下面函数关系：
     $$
     V= V(p,T)
     $$
     则：

     $$
     \mathrm{d} V=(\frac{\partial V}{\partial T})_p\mathrm{d}T+(\frac{\partial V}{\partial p})_T\mathrm{d}p
     $$

     由状态1到状态2的体积改变量为：
     $$
     \Delta V = \int_{V_1}^{V_2}\mathrm{d}V=V_2-V1
     $$
     状态函数沿闭合回路的积分为0，即：
     $$
     \begin{align*}
     \oint\mathrm{d}V&=\oint(\frac{\partial V}{\partial T})_p\mathrm{d}T+(\frac{\partial V}{\partial p})_T\mathrm{d}p\\
     &=\iint \left[\begin{matrix}\frac{\partial}{\partial T}&\frac{\partial}{\partial p}\\\left(\frac{\partial V}{\partial T}\right)_p&\left(\frac{\partial V}{\partial p}\right)_T\end{matrix}\right]\mathrm{d}T\mathrm{d}p\\
     &=\iint\left(\frac{\partial^2V}{\partial T\partial p}-\frac{\partial^2V}{\partial T\partial p}\right)\mathrm{d}T\mathrm{d}p\\
     &=0
     \end{align*}
     $$

4. gog过程和途径

   - Process：当体系的状态发生变化时，把状态变化的经过称为过程；
   - Path：完成变化的具体步骤称为途径。

   热力学常用的过程有：

   1. 等温过程
   2. 等压过程
   3. 绝热过程；例如炸弹开始爆炸的一瞬间，快速燃烧等。
   4. 等体过程

5. 热和功

   体系的状态发生改变时，通常会伴随着体系与环境进行能量的交换，其中能量的交换形式主要有两种：

   1. Heat：由于体系与环境有温度差所引起的能量流动；

      体系状态发生变化时表现为吸热（$Q>0$）和放热（$Q<0$），这里记住是以体系自身为参考对象，例如体系吸收了热量，所以体系的$Q>0$；

   2. Work：除了由于温度差造成了能量流动外的能量；

      主流规定是：体系对环境做功，$W<0$，环境对体系做功，$W>0$；这里同样是以体系自身为参考对象，例如体系朝着环境做了功，所以体系就少了一部分能量，因此$W<0$；

      功的形式可以分为两种：

      - Volume work
      - Novolume work

   由于热和功都是体系状态发生改变时与环境交换的能量，因此热和功不是状态函数！而是过程量。这种过程量我们不能用全微分表示，而用半微分表示，记为$\delta Q$和$\mathrm{\delta} W$。

#### 热力学第一定律

1. 能量守恒

   能量守恒定律在热力学体系中的应用称为热力学第一定律（First law of thermodynamics）。

2. 热力学能和热力学第一定律的数学形式

   热力学能旧称内能，是一种广度量，具有加和性，但其绝对值目前无法确定。

   体系由状态$\mathrm{I}$到状态$\mathrm{II}$，热力学能的改变量$\Delta U$等于体系从环境吸收的热量与环境对体系做的功的加和，即
   $$
   \Delta U = U_2-U_1=Q+W
   $$
   或者
   $$
   \mathrm{d}U=\delta Q+\delta W
   $$


### 可逆过程与最大功

#### 功与过程的关系

若体系**反抗外压**$p_e$体积改变了$\mathrm{d}V$，则体积功为：
$$
\begin{align*}
\delta W&=\vec{F}\cdot \mathrm{d}\vec{x}=p_eS\cdot\mathrm{d}x\cdot\cos\pi\\
&=-p_e\cdot\mathrm{d}Sx\\
&=-p_e\mathrm{d}V
\end{align*}
$$
或
$$
W=\int_{V_1}^{V_2}-p_e\mathrm{d}V
$$
根据表达式，我们可以知道：

若体系的$\mathrm{d}V>0$，则$\mathrm{d}W<0$，即体系要想增大自身的体积，就要牺牲自身的功为代价，反之亦然。

下面我们来计算上面那个积分的具体值是多少，我们考虑一个膨胀过程，这个体系的体积一点点的增大，假设体系的内压为$p$且比$p_e$大一个一阶无穷小量$\mathrm{d}p$，即$p_e=p-dp$，并且由理想气体的状态方程我们可以知道：
$$
\begin{align*}
W&=\int_{V_1}^{V_2}-p_e\mathrm{d}V=-\int_{V_1}^{V_2}(p-\mathrm{d}p)\mathrm{d}V\\
&=-\int_{V_1}^{V_2}p\mathrm{d}V+\int_{V_1}^{V_2}\mathrm{d}p\mathrm{d}V=-\int_{V_1}^{V_2}\frac{nRT}{V}\mathrm{d}V\\
&=-nRT\ln{\frac{V_2}{V_1}}
\end{align*}
$$
