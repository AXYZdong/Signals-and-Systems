# 前言
==离散系统 z 域分析相关内容==
# 一、从拉氏变换到z变换
对连续信号进行均匀冲激取样后，就得到离散信号：

><font color=black>$$
f_s(t)=f(t)\delta_T(t)=\sum_{k=-\infty}^{\infty}f(kT)\delta(t-kT)
$$

两边取双边拉氏变换得：
><font color=black>$$
F_{sb}(s)=\sum^{\infty}_{k=-\infty}f(kT)e^{-kTs}
$$

令：$z=e^{sT}$，上式成为复变量z的函数
><font color=black>$$
F(z)=\sum^{\infty}_{k=-\infty}f(k)e^{-k} \tag 1
$$
$$
F(z)=\sum^{\infty}_{k=0}f(k)e^{-k} \tag 2
$$

**（1）式成为序列 $f(k)$ 的双边z变换
（2）式成为序列 $f(k)$ 的单边边z变换**

==注：若 $f(k)$ 为因果序列，则单边、双边z变换相等。==
# 二、收敛域
z变换定义为一无穷幂级数之和，显然只有当该幂级数收敛，即：
><font color=black>$$
\sum_{k=-\infty}^{\infty}|f(k)z^{-k}|<\infty
$$

时，z变换才存在。
## 1、收敛域定义
对于序列 $f(k)$ 满足 $$\sum_{k=-\infty}^{\infty}|f(k)z^{-k}|<\infty$$
所有z值组成的集合称为z变换 $F(z)$ 的收敛域。

## 2、例题
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200428165822537.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200428165832408.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200428165841230.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
## 3、序列收敛域的几种情况
（1）有限长序列，其双边z变换在整个平面；

（2）因果序列，其z变换的收敛域为某个圆外区域；

（3）反因果序列，其z变换的收敛域为某个圆内区域；

（4）双边序列，其z变换的收敛域为环状区域；
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200428171356206.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)

# 三、常用序列z变换
><font color=red>1、$$\delta(k) \longleftrightarrow 1,|z|>0$$
>2、$$\epsilon(k)	\longleftrightarrow	\frac{z}{z-1},|z|>1$$
>3、$$-\epsilon(-k-1)	\longleftrightarrow	\frac{z}{z-1},|z|<1$$
>4、$$a^k\epsilon(k)	\longleftrightarrow	\frac{z}{z-a},|z|>a$$
>5、$$k\epsilon(k)	\longleftrightarrow	\frac{z}{(z-1)^2},|z|>1$$

# 总结
><font color=black>Z变换（英文：z-transformation）可将时域信号（即：离散时间序列）变换为在复频域的表达式。它在离散时间信号处理中的地位，如同拉普拉斯变换在连续时间信号处理中的地位。离散时间信号的Z变换是分析线性时不变离散时间系统问题的重要工具，在数字信号处理、计算机控制系统等领域有着广泛的应用。

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。