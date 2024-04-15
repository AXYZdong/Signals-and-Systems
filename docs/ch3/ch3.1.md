# 前言
==连续系统的频域分析==相关内容。
# 一、信号的正交分解
## 1、信号正交
【定义】在 $(t_1,t_2)$ 区间的两个函数 $\varphi_1(t)$ 和 $\varphi_2(t)$ ，若满足$\int_{t_1}^{t_2}\varphi_1(t)\varphi_2^*(t)dt=0$（两个函数的==内积==为0）

则称 $\varphi_1(t)$ 和 $\varphi_2(t)$ 在 $(t_1,t_2)$ 区间内正交。

说明：实函数正交 $\int_{t_1}^{t_2}\varphi_1(t) \varphi_2(t)dt=0$ （==内积==为0）
## 2、正交函数集
若 $n$ 个函数 $\varphi_1(t), \varphi_2(t),...,	\varphi_n(t)$ 构成一个函数集，当这些函数在区间 $(t_1,t_2)$ 内满足
$$
\int_{t_1}^{t_2}\varphi_i(t)\varphi_j^*(t)dt=
\begin{cases}
0, i \neq j  \\
\\
K_i \neq 0 , i=j
\end{cases}
$$
则称此函数集为在 $(t_1,t_2)$ 区间上的正交函数集。

## 3、完备正交函数集
如果在正交函数集 $\lbrace \varphi_1(t), \varphi_2(t),  ... ,	\varphi_n(t)\rbrace$ 之外，不存在任何函数 $\varphi(t)$ 满足
$$
\int_{t_1}^{t_2}\varphi_1(t)\varphi_2^*(t)dt=0 ,  (i=1,2,...,n)
$$

则称此函数集为完备正交函数集。
## 4、信号的正交分解
### 4.1正交函数的线性组合
设 $n$ 个函数 $\varphi_1(t), \varphi_2(t),...,	\varphi_n(t)$ 在区间 $(t_1,t_2)$ 构成一个正交函数空间。将任意函数 $f(t)$ 用这 $n$ 个正交函数的线性组合来近似表示，可表示为：
$$
f(t) \approx C_1 \varphi_1(t)+ C_2\varphi_2(t)+...+ C_i	\varphi_i(t)+...+C_n \varphi_n(t)= \sum_{j=1}^{n}C_j \varphi_j(t)
$$

说明：存在误差，但是当 $n\to \infty$ 时（完备正交函数集），误差为零。
### 4.2广义傅里叶级数
<font color=red>任意信号 $f(t)$ 可以表示为无穷多个正交函数之和
$$
f(t) = C_1 \varphi_1(t)+ C_2\varphi_2(t)+...+ C_i	\varphi_i(t)+... = \sum_{i=1}^{n}C_i \varphi_i(t)
$$
上式称为信号的正交展开式，也称为 广义的傅里叶级数 。
</font>

实变函数下：$C_i= \frac{ \int_{t_1}^{t_2}f(t)\varphi_i (t)dt }{\int_{t_1}^{t_2}\varphi_i^2(t) dt}= \frac{1}{K_i} \int_{t_1}^{t_2}f(t)\varphi_i (t)dt$
\
复变函数下：$C_i= \frac{ \int_{t_1}^{t_2}f(t)\varphi_i ^*(t)dt }{\int_{t_1}^{t_2}\varphi_i(t) \varphi_i^*(t) dt}= \frac{1}{K_i} \int_{t_1}^{t_2}f(t)\varphi_i ^*(t)dt$

$C_i$ 称为 广义傅里叶系数 。

### 4.3典型完备正交函数集
两组典型的在区间$(t_0,t_0+T)(T=2\pi/ \Omega)$ 上的完备正交函数集

（1）三角函数集 $\lbrace 1, \cos(n\Omega t)  ,\sin(n\Omega t)  ,n=1,2,...\rbrace$

（2）虚指数函数集 $\lbrace e^{jn\Omega t}   ,n=0, \pm 1,\pm 2,...\rbrace$
# 二、傅里叶级数
$Dirichlet$条件
在一个周期内：（1）如果间断点存在，则间断点的数目应是有限个
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（2）极大值和极小值的数目应是有限个
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（3）信号满足绝对可积
## 1、三角形式
<strong> 直流分量 + $n(n \to \infty)$个正交函数的线性组合。
说明：这里的正交函数属于完备正交函数集（三角函数集）</font>

<font color=red>周期信号 $f(t)$ 其周期为 $T$ 角频率 $\Omega= \frac{2 \pi}{T}$ 当满足 $Dirichlet$ 条件时，它可以分解成如下三角级数：
$$
f(t)= \frac{a_0}{2} + \sum_{n=1}^{\infty}a_n \cos(n\Omega t) +\sum_{n=1}^{\infty} b_n \sin(n\Omega t)
$$
$a_n,b_n$ 称为傅里叶系数
\
$a_n= \frac{2}{T} \int_{-\frac{T}{2}}^{
\frac{T}{2}} f(t) \cos(n\Omega t)dt$
\
$b_n= \frac{2}{T} \int_{-\frac{T}{2}}^{
\frac{T}{2}} f(t) \sin(n\Omega t)dt$
</font>
同频率项合成：$f(t)= \frac{A_0}{2} + \sum_{n=1}^{\infty}A_n \cos(n\Omega t +\varphi_n)$
\
式中：$A_0=a_0,A_n=\sqrt{a_n^2+b_n^2}, \varphi_n=-\arctan \frac{b_n}{a_n}$
\
$a_n=A_n\cos \varphi _n , b_n=-A_n\sin \varphi _n,n=1,2,...$
\
$\frac{A_0}{2}$ ：直流分量；
\
$A_1 \cos(\Omega t +\varphi _1)$：基波或一次谐波
\
$A_n \cos(n\Omega t +\varphi _n)$：$n$ 次谐波
## 2、波形的对称性与谐波特性
|对称条件|展开式中所包含成分|$a_n$|$b_n$|
|--|--|--|--|
|偶函数|直流项$+$余弦项|$\frac{4}{T} \int_0^{\frac{T}{2}} f(t) \cos(n\Omega t)dt$|$0$|
|奇函数|正弦项|0|$\frac{4}{T} \int_0^{\frac{T}{2}} f(t) \sin(n\Omega t)dt$|$0$|
|偶谐函数$f(t)=f(t \pm \frac{T}{2})$|只含偶次谐波|$\frac{4}{T} \int_0^{\frac{T}{2}} f(t) \cos(n\Omega t)dt$|$\frac{4}{T} \int_0^{\frac{T}{2}} f(t) \sin(n\Omega t)dt$|
|奇谐函数$f(t)=-f(t \pm \frac{T}{2})$|只含奇次谐波|$\frac{4}{T} \int_0^{\frac{T}{2}} f(t) \cos(n\Omega t)dt$|$\frac{4}{T} \int_0^{\frac{T}{2}} f(t) \sin(n\Omega t)dt$|
## 3、指数形式
$$
f(t)=\sum_{n=-\infty}^{\infty} F_n e^{j n \Omega t}
$$
 \
 复傅里叶系数$F_n= \frac{1}{T} \int_{-\frac{2}{T}}^{
\frac{2}{T}} f(t) e^{-j n \Omega t}dt$

## 4、周期信号的功率——Parseval等式
平均功率：
$$
\frac{1}{T} \int_{0}^{T}	f^2(t) 	dt	=(\frac{A_0}{2})^2	+\sum_{n=1}^{\infty}	\frac{1}{2}	A_n^2	=\sum	_{n=-\infty}^{\infty}	|F_n|	^	2	
$$
# 总结
中学学过 ==矢量的正交分解== ，类比，==信号也可以正交分解==，任意信号 $f(t)$ 可以表示为无穷多个正交函数之和，完备的 ==正交函数集== 为 ==傅里叶级数== 埋下了伏笔。乍一看傅里叶级数一串儿公式，刚开始可能不理解，如果从信号的正交分解来看，就不难理解了。

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。
 
