# 前言
拉普拉斯逆变换求解方法：

（1）根据定义，复变函数积分（比较困难）

（2）部分分式分解（==常用==）

（3）留数定理
# 部分分式分解
若象函数 $F(s)$ 是 $s$ 的有理分式，可写为：
$$F(s)=\frac{b_ms^m+b_{m-1}s^{m-1}+...+b_1s+b_0}{s^n+a_{n-1}s^{n-1}+...+a_1s+a_0}$$

若 $m \ge n$ （假分式），可用多项式除法将象函数 $F(s)$ 分结尾有理多项式 $P(s)$ 与有理真分式之和。

$$F(s)=P(s)+\frac{B_0(s)}{A(s)}$$
# 有理真分式的情形
若 $F(s)$ 是 $s$ 实系数有理真分式（$m<n$），则可写为：
$$F(s)=\frac{B (s)}{A(s)}=\frac{b_ms^m+b_{m-1}s^{m-1}+...+b_1s+b_0}{s^n+a_{n-1}s^{n-1}+...+a_1s+a_0}$$

 $A(s)$ 称为特征多项式，方程 $A(s)=0$ 称为特征方程，它的根称为特征根，也称为 $F(s)$ 的固有频率。 $n$ 个特征根 $p_i$ 称为 $F(s)$ 的极点。
## 1、极点为实数，无重根
 例：$$F(s)=\frac{2s+1}{s(s+2)(s+3)}$$
><strong><font color=black>解：令：$$F(s)=\frac{k_1}{s}+\frac{k_2}{s+2}+\frac{k_3}{s+3}$$
$k_1=sF(s)|_{s=0}=1/6,\\k_2=(s+2)F(s)|_{s=-2}=3/2\\k_3=(s+3F(s)|_{s=-3}=-5/3$
故：$$F(s)=\frac{ 1}{6s}+\frac{3}{2(s+2)}+\frac{-5}{3(s+3)}$$
$F(s)$ 拉式反变换为 $$f(t)=( \frac{ 1}{6}+\frac{3}{2}e^{-2t}-\frac{5}{3}e^{-3t})\epsilon(t)$$

## 2、包含共轭复数极点
 例：$$F(s)=\frac{s^2+3}{ (s+2)(s^2+2s+5)}$$
><strong><font color=black>解：$$F(s)=\frac{s^2+3}{(s+1+j2)(s+1-j2)(s+2)}$$
>令：$$F(s)=\frac{k_1}{s+1-j2}+\frac{k_2}{s+1+j2}+\frac{k_3}{s+2}$$
$$p_{1,2}=-\alpha\pm j\beta,(\alpha=1,\beta=2)$$
$$k_1=(s+1-j2)F(s)|_{s={-1+j2}}=\frac{-1+j2}{5}$$
$$即：k_{1,2}=A\pm jB,(A=-\frac{1}{5},B=\frac{2}{5})$$
$$k_1=(s+2)F(s)|_{s=-2}=\frac{7}{5}$$
故：$$F(s)=\frac{\frac{-1+j2}{5}}{s+1-j2}+\frac{\frac{-1-j2}{5}}{s+1+j2}+\frac{\frac{7}{5}}{s+2}$$
$F(s)$ 拉式反变换为 $$f(t)=\lbrace 2e^{-t}[-\frac{1}{5}\cos(2t)-\frac{2}{5}\sin(2t)]+\frac{7}{5}e^{-2t}\rbrace \epsilon(t)$$

## 3、有多重极点
例：$$F(s)=\frac{s-2}{s(s-1)^2}$$
><strong><font color=black>解：令：$$F(s)=\frac{k_{11}}{(s-1)^2}+\frac{k_{12}}{(s-1) }+\frac{k_2}{s}$$
令：$$F_1(s)=(s-1)^2F(s)=\frac{s-2}{s}$$
$k_{11}=F_1(s)|_{s=1}=-1,k_{12}=\frac{d}{ds}F_1(s)=\frac{s-(s-2)}{s^2}|_{s=1}=2,k_2=sF(s)|_{s=0}=-2$
故：$$F(s)=\frac{-1}{(s-1)^2}+\frac{2}{(s-1) }+\frac{-2}{s}$$
$F(s)$ 拉式反变换为 $$f(t)=(-te^t+2e^t-2)\epsilon(t)$$


# 总结
部分分式分解还是比较常用的，注意分解步骤，计算时仔细一点。常用的拉氏变换要记得。

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

