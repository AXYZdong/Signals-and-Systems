# 前言
==连续系统的频域分析==相关内容。
# 一、傅里叶变换的性质

## 1、线性性质
若	$f_1(t)\longleftrightarrow	F_1(j\omega),f_2(t)\longleftrightarrow	F_2(j\omega)$
\
则：$af_1(t)+bf_2(t)\longleftrightarrow	aF_1(j\omega)+	b F_2(j\omega)$
## 2、奇偶性
若	$f(t)\longleftrightarrow	F(j\omega)$ ，则：$f(-t)\longleftrightarrow	F(-j\omega)$

若：为 $f(t)$ 实偶函数，则 $F(j\omega)$ 为实偶函数

若：为 $f(t)$ 实奇函数，则 $F(j\omega)$ 为虚奇函数
## 3、对称性
若	$f(t)\longleftrightarrow	F(j\omega)$  ， 则： $F(jt)\longleftrightarrow	2\pi f( -\omega)$

例：$$f(t)	=	\frac{1}{1+t^2}	\longleftrightarrow	F(j\omega)=?$$

解：$\because	e^{-\alpha|t|}	\longleftrightarrow \frac{2	\alpha}{\alpha^2+\omega^2}$

当	$\alpha	=1时， e^ {-|t|}	\longleftrightarrow \frac{2	 }{1+\omega^2}$

$\frac{2	 }{1+ t^2}	\longleftrightarrow 2\pi e^ {-|\omega|}$

$\frac{1	 }{1+ t^2}	\longleftrightarrow  \pi e^ {-|\omega|}$
## 4、尺度变换特性
若	$f(t)\longleftrightarrow	F(j\omega)$  , 则：$f(at)\longleftrightarrow \frac{1}{|a|}	F(j	\frac{\omega}{a})	,a 为非零实数$ 

当	$0<a<1$	时 ，时域扩展，频带压缩

当	$a>1$	时 ，时域压缩，频带扩展
## 5、时移特性
若	$f(t)\longleftrightarrow	F(j\omega)$ ，	则：$f(t	\pm	t_0)\longleftrightarrow	e^{\pm	j	\omega t_0}	F(j\omega),t_0为实常数$

若 $F(j\omega)=|F(j\omega)|	e^{ 	j	\varphi(\omega)  }$，则$f(t	\pm	t_0)\longleftrightarrow	|F(j\omega)|	e^{ 	j	[ \varphi(\omega) \pm \omega t_0 ] }$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200323205438562.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_50,color_FFFFFF,t_70  =500x350)
## 6、频移特性
若	$f(t)\longleftrightarrow	F(j\omega)$ ，	则：$e^{-	j	\omega t_0} f(t)\longleftrightarrow		F[j(\omega	+\omega_0)]$

若	$f(t)\longleftrightarrow	F(j\omega)$ ，	则：$e^{+	j	\omega t_0} f(t)\longleftrightarrow		F[j(\omega	-\omega_0)]$

<font color=red> 注意变换对两边的正负号</font>
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200323210118361.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_50,color_FFFFFF,t_70 =500x350)
## 7、卷积定理
若	$f_1(t)\longleftrightarrow	F_1(j\omega),f_2(t)\longleftrightarrow	F_2(j\omega)$ , 则
\
时域：$f_1(t)*f_2(t)\longleftrightarrow	F_1(j\omega)	\cdot	F_2(j\omega)$

频域： $f_1(t)\cdot	f_2(t)\longleftrightarrow	\frac{1}{2\pi} F_1(j\omega)	*	F_2(j\omega)$

## 8、时域微积分特性
若	$f(t)\longleftrightarrow	F(j\omega)$ 

微分： $f^{(n)}(t)	\longleftrightarrow	(j	\omega)^{(n)} F(j\omega)$

积分： $\int_{-\infty}^{t} f(x)dx	\longleftrightarrow	\pi	F(0)\cdot	\delta(\omega)	+	\frac{F(j\omega)}{j\omega},其中 F(0)=F(j\omega)|_{\omega=0}	=\int _{-\infty}^{ \infty}f(t)dt$
## 9、频域微积分特性
若	$f(t)\longleftrightarrow	F(j\omega)$ 

微分： $(-jt)^n f (t)	\longleftrightarrow  F^{(n)}(j\omega)$

积分： $\pi	f(0)\cdot	\delta(t)	+	\frac{f(t)}{-jt}		\longleftrightarrow	\int_{-\infty}^{\omega} F(jx)dx,其中 f(0)=\frac{1}{2\pi}\int _{-\infty}^{\infty}F(j\omega)d\omega$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200323212923519.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_50,color_FFFFFF,t_70 =500x300)
# 二、能量谱
帕斯瓦尔方程：

$$
E=	\int _{-\infty}^{\infty}	|f(t)|^2dt=	\frac{1}{2\pi}	\int _{-\infty}^{\infty}	|F(j \omega)|^2d\omega
$$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200323115541714.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_50,color_FFFFFF,t_70  =400x300)
# 三、周期信号的傅立叶变换
## 1、正余弦信号的傅里叶变换
$1\longleftrightarrow 2\pi \delta(\omega)$

$e^{j\omega_0 t}\longleftrightarrow 2\pi \delta(\omega -\omega_0)$

$e^{-j\omega_0 t}\longleftrightarrow 2\pi \delta(\omega +\omega_0)$

利用频移特性

$\cos(\omega_0t) =\frac{1}{2}(e^{j\omega_0 t} +e^{-j\omega_0 t})	\longleftrightarrow	\pi [\delta(\omega +\omega_0)+	\delta(\omega -\omega_0)]$

$\sin(\omega_0t) =\frac{1}{2j}(e^{j\omega_0 t} -e^{-j\omega_0 t})	\longleftrightarrow	j\pi [\delta(\omega +\omega_0)-	\delta(\omega -\omega_0)]$

## 2、一般周期信号的傅里叶变换
将一般周期信号表示为 三角形式 或者 指数形式 ，当然 指数形式 比较方便，下边的变换对就是先将 一般周期信号 分解成 指数形式 ，再利用频移特性

$f(t)=\sum_{n=-\infty}^{\infty} F_n e^{j n \omega_0 t}	\longleftrightarrow  F(j\omega)=2\pi \sum_{n=-\infty}^{\infty}F_n \delta(\omega-n\omega_0)$

# 总结
傅里叶变换的性质比较多，通过这些性质可以简便的求出某个信号的傅里叶变换，降低了用定义来求的复杂程度。
<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。
