>Author：AXYZdong
>自动化专业 工科男
>有一点思考，有一点想法，有一点理性！

@[TOC]
# 一、信号
## 1、概念
信号：物质的运动形式或状态的变化。
表示：信号常用时间函数（或序列）表示。该函数的图像称为信号的波形。
## 2、分类
|分类标准|信号类别|
|--|--|
|以自变量取值分类|连续信号、离散信号|
|以信号的起始时刻分类|因果信号、非因果信号|
|以$f(t)$取值分类|周期信号、非周期信号|
|以确立与随机分类|确定信号、随机信号|
|以$f(t)$为实函数或复函数分类|实信号、复信号|
|以能量是否有限分类|能量有限信号、能量无限信号|
## 3、周期信号和非周期信号
### 3.1、基本概念
周期信号（period signal）是定义在 (-$\infty$,+$\infty$)区间，每隔一定时间$T$(或整数$N$),按相同规律重复变化的信号。

连续周期信号$f(t)$满足：
$f(t)=f(t+mT),m=0,\pm1,\pm2,...$

离散周期信号$f(k)$满足：
$f(k)=f(k+mN),m=0,\pm1,\pm2,...$

满足上述关系的最小$T$（或整数$N$）称为该信号的周期。不具有周期性的信号称为非周期信号。
### 3.2、周期$T$求法
举两个例子，通过例子来说明具体求法。
<strong>（1）$f_1(t)=\sin2t + \cos3t$        （2）$f_2(t)=\cos2t + \sin \pi t$

解：<font color=red> 两个周期信号$x(t),y(t)$的周期分别为$T_1,T_2$,若其周期之比$\frac{T_1}{T_2}$为有理数，则其和信号$x(t)+y(t)$仍然是周期信号，其周期为$T_1$和$T_2$的最小公倍数。</font>

（1）$\sin2t,T_1=\frac{2\pi}{2}=\pi$ 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\cos3t,T_2=\frac{2\pi}{3}$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\frac{T_1}{T_2}=\frac{3}{ 2}$为有理数，$f_1(t)$为周期信号，周期$2\pi$

（2）$\cos2t,T_1=\frac{2\pi}{2}=\pi$ 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\sin \pi t,T_2=\frac{2\pi}{\pi}=2$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\frac{T_1}{T_2}=\frac{\pi}{ 2}$为无理数，$f_2(t)$为非周期信号

<strong>总结：①连续的正弦信号一定是周期信号
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;②正弦序列不一定是周期序列
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;③ 两连续周期信号之和不一定是周期信号
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;④两周期序列之和一定是周期序列
# 二、系统
## 1、概念
系统（system）：由若干个相互联系、相互作用的单元组成的具有一定功能的整体。
例：收音机系统

![在这里插入图片描述](https://img-blog.csdnimg.cn/202003081659002.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
表示：图示、方程（微分方程、差分方程）。
## 2、分类
按系统处理信号的形式分类

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200308170155528.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
## 3、线性系统
### 3.1概念
线性(linearity property)：均匀性、叠加性。
线性系统：指具有线性特性的系统
系统的线性特性：
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\underrightarrow{f_1(t)}$ $H$ $\underrightarrow{y_1(t)}$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\underrightarrow{f_2(t)}$ $H$ $\underrightarrow{y_2(t)}$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$\underrightarrow{\alpha _1f_1(t)+\alpha _2f_2(t)}$ $H$ $\underrightarrow{\alpha _1y_1(t)+\alpha _2y_2(t)}$
### 3.2线性系统的判断方法
<font color=red> 先线性运算，再经系统 = 先经系统，再线性运算</font>

$$
        \left.
        \begin{array}{l}
        \text{$\underrightarrow{f_1(t)}$ $C_1$ $\underrightarrow{C_1f_1(t)}$}\\
        \text{$\underrightarrow{f_2(t)}$ $C_2$ $\underrightarrow{C_2f_2(t)}$} 
        \end{array}
        \right\}
        \to C_1f_1(t)+C_2f_2(t)  
        \to	H	
        \to	H	\lbrace	C_1f_1(t)+C_2f_2(t)	\rbrace
$$
$$
        \left.
        \begin{array}{l}
        \text{$\underrightarrow{f_1(t)}$ $H$ $\underrightarrow{	H	\lbrace f_1(t)		\rbrace }$}\\
        \text{$\underrightarrow{f_2(t)}$ $H$ $\underrightarrow{	H	\lbrace f_2(t)		\rbrace}$} 
        \end{array}
        \right\}
        \to H	\lbrace f_1(t)		\rbrace+H	\lbrace f_2(t)		\rbrace  
        \to	C
        \to 	C_1H	\lbrace f_1(t)		\rbrace	+	C_2H	\lbrace f_2(t)		\rbrace  
$$
若$H	\lbrace	C_1f_1(t)+C_2f_2(t)	\rbrace = C_1H	\lbrace f_1(t)		\rbrace	+	C_2H	\lbrace f_2(t)		\rbrace$

则系统$H$为线性系统

<strong>例：判断方程所描述的系统的线性

$y(k)+(k-1)y(k-1)=f(k)$

解：
$$
f_1(k)	\to y_1(k) ,f_2(k)	\to y_2(k)\\
f_1(k)+f_2(k)=y_1(k)+y_2(k)+(k-1) \lbrace y_1(k-1)+y_2(k-1)	\rbrace\\
f_1(k)+f_2(k)	\to y_1(k) + y_2(k)\\
f_1(k)+f_2(k)=y_1(k)+y_2(k)+(k-1) \lbrace y_1(k-1)+y_2(k-1)	\rbrace\\
$$
故：方程所描述的系统是线性系统。
## 4、时不变系统
### 4.1概念
时不变系统：一个系统，在零初始条件下，其输出响应与输入信号施加于系统的时间起点无关，这样的系统称为时不变系统。

时不变性：系统具有上述的性质称为时不变性。
### 4.2判断方法
<font color=red> 先时移，再经系统 = 先经系统，再时移</font>

$$
 f(t)\to 时移\tau
 \to f(t-\tau)
\to H
\to H	\lbrace  f(t-\tau)		\rbrace \\
$$
$$
\underrightarrow{f(t)}   H	\to	H	\lbrace f_1(t)		\rbrace
\underrightarrow{令y(t)=H	\lbrace f_1(t)		\rbrace}
\to 时移\tau
\to y(t-\tau)\\
$$
若：$H	\lbrace  f(t-\tau)		\rbrace 	=	y(t-\tau)$，则系统$H$是时不变系统。

## 5、线性时不变系统（Linear and Time-invariant System）
线性时不变系统：系统既是线性的，又是时不变的；或系统的方程为线性常系数微分方程。

# 三、常用的基本信号
## 1、单位阶跃信号（unit step signal）
$$
        \epsilon(t) =
        \begin{cases}
        1,  & \text{t>0} \\
        0, & \text{t<0}
        \end{cases}
$$
时移$t_0$
$$
        \epsilon(t-t_0) =
        \begin{cases}
        1,  & t>t_0\\
        0, & t<t_0
        \end{cases}
$$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200308190140732.png#pic_center)
## 2、矩形脉冲信号（门函数）
$$
        g_\tau(t) =
        \begin{cases}
        1,  & (|t|<\frac{\tau}{2})\\
        0, & (|t|>\frac{\tau}{2})
        \end{cases}
$$

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020030819061149.png#pic_center)
## 3、斜坡信号（ramp signal）
$$
        r(t) =
        \begin{cases}
        0,  & t<0 \\
        t, &  t \geq 0
        \end{cases}\\ 
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$=t\epsilon(t)$       

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200308191413817.png#pic_center)
## 4、取样函数（sampling function）
$$S_a(t)=\frac{\sin t}{t} (-\infty <t<+\infty)$$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200308192732671.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
><strong><font color=black>①偶函数 
② 当$t=0$时，$S_a(t)=1$为最大值
③ 曲线呈衰减振荡
>④ $$\int_0^\infty {S_a(t)} \,{\rm d}t=\frac{\pi}{2} , \int_ {-\infty}^{\infty} {S_a(t)} \,{\rm d}t=\pi$$
>
 取样函数常用形式 $\sin c(t)=\frac{\sin \pi t}{\pi t}=S_a(\pi t)$
 ## 5、单位冲激函数（unit impulse function）
 视作矩形脉冲的极限


p;&nbsp;&nbsp; ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200308193347337.png#pic_center)
$$
        \delta(t) =
        \begin{cases}
        \infty,  &  t=0 \\
        0, & t \neq0
        \end{cases}
$$
$$ \int_ {-\infty}^\infty {\delta(t)} \,{\rm d}t=1$$
延时冲激：$A\delta(t-t_0)$

冲激偶：$\delta \prime(t)=\frac{d\delta(t)}{dt}$

<strong>性质：1、偶函数：$\delta(t)=\delta(-t)$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2、取样性：
<font color=red>
$$
f(t)\cdot \delta(t)=f(0)\cdot \delta(t)\\
f(t)\cdot \delta(t-t_0)=f(t_0)\cdot \delta(t-t_0)\\
$$
$$ 
\int_ {-\infty}^\infty {f(t)\cdot \delta(t)} \,{\rm d}t=f(0)\\
\int_ {-\infty}^\infty {f(t)\cdot \delta(t-t_0)} \,{\rm d}t=f(t_0)\\
$$
</font>
$\delta(t)$与$\epsilon(t)$的关系：
$$ \int_ {-\infty}^t {\delta(\tau)} \,{\rm d}\tau=\epsilon(t)$$
$$\frac{d\epsilon(t)}{dt}=\delta(t)$$

<em>利用该性质可对不连续函数求导。

<br>

「你可能还想看」系列文章：
[【信号与系统】笔记合集，你确定不收藏吗？我已经收藏了](https://axyzdong.blog.csdn.net/article/details/105909575)

\
<strong> <font color=red><strong>看完就赞，养成习惯，尊重别人的劳动是一种美德！！！^ _ ^ <3 <3 <3</font>
 码字不易，大家的支持就是我坚持下去的动力。点赞后不要忘了👉<font color=red>关注</font>👈我哦！
 更多精彩内容请前往 [AXYZdong的博客](https://blog.csdn.net/qq_43328313)

<hr><p>如果以上内容有任何错误或者不准确的地方，欢迎在下面👇留个言。或者你有更好的想法，欢迎一起交流学习~~~</p> 
