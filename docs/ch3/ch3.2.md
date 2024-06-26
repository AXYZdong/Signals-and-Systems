# 一图看懂傅里叶变换

![图片来自@胖福的小木屋](https://img-blog.csdnimg.cn/20200322121931397.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =600x)

从时域来看，我们会看到一个近似为矩形的波，而我们知道这个矩形的波可以被差分为一些正弦波的叠加。
而从频域方向来看，我们就看到了每一个正余弦波的幅值，每两个正弦波之间都还有一条直线，那并不是分割线，而是振幅为 0 的正弦波！
也就是说，为了组成特殊的曲线，有些正弦波成分是不需要的。随着叠加的递增，所有正弦波中上升的部分逐渐让原本缓慢增加的曲线不断变陡，而所有正弦波中下降的部分又抵消了上升到最高处时继续上升的部分使其变为水平线。一个矩形就这么叠加而成了。但是要多少个正弦波叠加起来才能形成一个标准 90 度角的矩形波呢？不幸的告诉大家，答案是无穷多个。

# 前言
**连续系统频域分析**中的 信号的频谱与傅里叶变换  

信号的频谱：信号的某种特征量与信号频率变化的关系。

**频谱图**：将幅度和相位分量用**一定高度的直线**表示。

# 一、周期信号的频谱
## 1、周期信号频谱的相关概念

周期信号频谱：周期信号中各次谐波幅值、相位随频率变化关系。

$A_u\sim \omega$	：振幅频谱图

$\varphi _u\sim \omega$	：相位频谱图

三角函数形式分解：$f(t)=\frac{A_0}{2}	+	\sum_{n=1}^{\infty}	A_n	\cos(n	\Omega	t	+	\varphi_n)$

虚指数函数形式分解：$f(t)= 	\sum_{n=-\infty}^{\infty}	F_n	e^{jn	\Omega	t}$

|频谱分类|直流分量|幅度|相位|$n$|
|--|--|--|--|--|
|单边谱|$\frac{A_0}{2}$|$A_n$|$\varphi_n$|$n=0,1,2,...$|
|双边谱|$F_0$|  \|$F_n$\|  |$\varphi_n$|$n=0,	\pm1,	\pm2,...$|

单边谱和双边谱的关系:
$$
\cos(	n	\Omega	t)	=	\frac{1}{2}	(e^{jn	\Omega t}+e^{-jn	\Omega t})\\
F_n=|F_n|	e^{j	\varphi_n}	=	\frac{1}{2}	A_n	e^{j	\varphi_n}\\
|F_n|=	\frac{1}{2}	A_n, \varphi_n=-	\arctan\frac{b_n}a_n{}
$$
\
例：周期信号$f(t)	=	1-	\frac{1}{2}	\cos(\frac{\pi}{4}t-\frac{2\pi}{3})	+	\frac{1}{4}	\sin(\frac{\pi}{3}t-\frac{ \pi}{6})$

求该周期信号的基波周期 $T$ ，基波角频率 $\Omega$ ，平均功率 $P$ ，并画出它的频谱图。

解：
$$
改写f(t)表达式：f(t)=1	+	\frac{1}{2}	\cos(\frac{\pi}{4}t	+	\frac{\pi}{3})	+	\frac{1}{4}	\cos(\frac{\pi}{3}t-\frac{ 2\pi}{3})
$$
$\frac{1}{2}	\cos(\frac{\pi}{4}t +	\frac{\pi}{3}) 周期 T_1=8$
\
$\frac{1}{4}	\cos(\frac{\pi}{3}t-\frac{ 2\pi}{3})周期 T_2=6$

$\therefore f(t) 周期T=24, 基波角频率 \Omega	=	\frac{ 2\pi}{T}	=\frac{ \pi}{12}$
\
$由帕斯瓦尔等式，P=1+\frac{ 1}{2} \cdot(\frac{ 1}{2})^2	+\frac{ 1}{2} \cdot(\frac{ 1}{4})^2	=\frac{ 37}{32}$
\
频谱图：

$\frac{1}{2}	\cos(\frac{\pi}{4}t +	\frac{\pi}{3})$ 是 $f(t)$ 的 $[\pi/4]/[\pi/12]=3$ 次谐波分量；

$\frac{1}{4}	\cos(\frac{\pi}{3}t-\frac{ 2\pi}{3})$ 是 $f(t)$ 的 $[\pi/3]/[\pi/12]=4$ 次谐波分量；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200320214703638.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =700x)
 

## 2、周期信号频谱的特点
1、离散型：以基频  $\Omega$ 为间隔的若干离散谱线组成
\
2、谐波性：谱线仅含有基频 $\Omega$ 的整数倍分量
\
3、收敛性：整体趋势减小

周期信号频谱的特点简要的概括了一下。

## 3、谱线的结构与波形参数的关系
1、$T$一定，$\tau$变小，此时 $\Omega$ （谱线间隔）不变。两零点之间的谱线数：

$$
\frac{\omega}{\Omega} = \frac{2 \pi}{\tau} /\frac{2\pi}{T},增多
$$
2、$\tau$ 一定， $T$ 增大，间隔 $\Omega$ 减小，频谱变密，幅度减小。

如果周期 $T$  无限增长（ $T\to \infty$ ），周期信号就变成了非周期信号，那么，谱线间隔将趋于零，周期信号的离散频谱就过渡到非周期信号的连续频谱。各频率分量的幅度也趋近于无穷小。

# 二、非周期信号的频谱
## 1、周期信号 $\to$ 非周期信号
频谱函数：$$F_n= \frac{1}{T} \int_{-\frac{2}{T}}^{
\frac{2}{T}} f(t) e^{-j n \Omega t}dt$$

 $T\to \infty$ 时：
 $$
 f(t) 周期信号\to 非周期信号\\
 F_n \to0\\
谱线间隔 \Omega \to 0\\
离散频谱\to  连续频谱 ，频谱幅度\to 0
 $$

## 2、频谱密度函数
频谱函数：$$F_n= \frac{1}{T} \int_{-\frac{2}{T}}^{
\frac{2}{T}} f(t) e^{-j n \Omega t}dt$$
$T\to \infty$ 时：
 $$
 \Omega \to d\omega (无穷小量)\\
 n\Omega \to \omega (离散\to连续)\\
 $$

$$F(j \omega)=\lim_{T\to \infty} \frac{F_n}{1/T}=\lim_{T\to \infty}F_nT	$$	
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$=\lim_{T\to \infty}	\int_{-\frac{2}{T}}^{\frac{2}{T}} f(t) e^{-j n \Omega t}dt$	
	
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$=\int_{-\infty}^{\infty} f(t) e^{-j  \omega t}dt$


## 3、傅里叶变换与反变换
### 3.1傅里叶变换

$$F(j \omega)= \int_{-\infty}^{\infty} f(t) e^{-j  \omega t}dt$$

$F(j \omega)$ 称为 $f(t)$ 的傅里叶变换

$F(j \omega)$ 一般为复数，写成 $F(j \omega)$ = $|F(j \omega)|	e^{j \varphi(\omega)}$
\
$F(j \omega)\sim \omega$	：幅频度谱图，频率 $\omega$ 的偶函数

$\varphi _u\sim \omega$	：相位频谱图，频率 $\omega$ 的奇函数

### 3.2傅里叶反变换
$$f(t)= \frac{1}{2\pi}\int_{-\infty}^{\infty}F(j\omega)e^{j  \omega t}d\omega$$

符号差别：

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020032022200668.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =540x180)

## 4、<font color=red>常用函数的傅里叶变换</font>
<font color=red>$$e^{-	\alpha t}\epsilon(t) \longleftrightarrow	\frac{1}{\alpha+j	\omega}$$
$$e^{-	\alpha |t|}  \longleftrightarrow	\frac{2\alpha}{\alpha ^2+ 	\omega ^2}
$$
$$g_\tau(t)	 \longleftrightarrow \tau Sa(\frac{\omega \tau}{2})
$$
$$ \delta(t)	\longleftrightarrow 1	
$$
 $$\delta'(t)	 \longleftrightarrow	j	\omega
$$
 $$1	 \longleftrightarrow2\pi \delta(\omega)
$$
$$ sgn(t)	 \longleftrightarrow	\frac{2}{	j	\omega}
$$
$$ \epsilon(t)	 \longleftrightarrow	\pi \delta(\omega)	+	\frac{1}{	j	\omega}
$$</font>



# 总结
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200327140842124.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =300x)
时域里面原函数 $\longrightarrow$ 频域里面相函数
频域里面相函数 $\longrightarrow$ 时域里面原函数

周期信号 $\to$ 傅里叶级数 $\to$ 频谱

非周期信号 $\to$ 傅里叶变换 $\to$ 频谱

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。
