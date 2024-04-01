>Author：AXYZdong
>自动化专业 工科男
>有一点思考，有一点想法，有一点理性！
>CSDN@AXYZdong

@[TOC]
# 前言
**连续系统的S域分析**
# 一、从傅里叶变换到拉普拉斯变换
傅里叶变换要满足Dirichlet（狄利克雷）条件中的绝对可积，对于某些增长信号，如 $e^{at}(a>0)$ ,它就不存在傅里叶变换。

引入一个衰减因子 $e^{-\sigma t}（\sigma 为任意实数）$ ，使它与 $f(t)$ 相乘，于是 $e^{-\sigma t}f(t)$ 得以收敛。

$$
F_{b}(s)=\int _{-\infty}^{\infty} f(t) e^{-st}dt \tag1
$$
$$
f(t)=\frac{1}{2\pi j}\int_{\sigma-\infty}^{\sigma+\infty} F(s)e^{st  }ds \tag2
$$
$(1)$ 双边拉氏变换，$F_b(s)$ ：象函数

$(2)$ 双边拉氏逆变换，$f(t)$ ：原函数

# 二、拉氏变换收敛域
使 $f(t)$ 拉氏变换存在的 $\sigma$ 取值范围称为 $F(s)$ 的收敛域

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200410175346126.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =450x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200410175428522.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =450x)
<center><sup><sup>取值范围不同，变换的结果也不同</sup></sup><center>

# 三、单边拉氏变换
带有初始时刻的信号，双边拉氏变换就转化成单边拉氏变换。
$$
F_{b}(s)=\int _{0_-}^{\infty} f(t) e^{-st}dt 
$$
$$
f(t)=[\frac{1}{2\pi j}\int_{\sigma-\infty}^{\sigma+\infty} F(s)e^{st  }ds] \cdot\epsilon(t)
$$
# 四、常见函数的拉氏变换
1、$$\delta(t)  \longleftrightarrow 1, \sigma>-\infty$$

2、$$\epsilon(t) 或 1 \longleftrightarrow \frac{1}{s},\sigma>0$$

3、指数函数
$$e^{-s_0 t} \longleftrightarrow  \frac{1}{s+s_0}, \sigma>-Re[s_0]$$

4、三角函数
$$
\cos\omega_0t   \longleftrightarrow \frac{s}{s^2+w_0^2}
$$
$$
\sin\omega_0t   \longleftrightarrow \frac{\omega_0}{s^2+w_0^2}
$$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200410181415254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
# 总结
拉普拉斯变换与傅里叶变换的基本差别在于:

傅氏变换将时域函数 $f(t)$ 变换为频域函数$F(\omega)$ ，或作相反变换，时域中的变量 $t$ 和频域中的变量 $\omega$ 都是实数；而拉氏变换是将时间函数 $f(t)$ 变换为复变函数 $F(s)$ ，或作相反变换，这时，时域变量 $t$ 虽是实数, $F(s)$的变量 $s$ 却是复数，与 $\omega$ 相比较，变量 $s$ 可称为“复频率”。

傅里叶变换建立了时域和频域间的联系，而拉氏变换则建立了时域与复频域( $s$ 域)间的联系。
<br>

「你可能还想看」系列文章：
[【信号与系统】笔记合集，你确定不收藏吗？我已经收藏了](https://axyzdong.blog.csdn.net/article/details/105909575)

 <strong> <font color=red><strong>看完就赞，养成习惯 ^ _ ^ <3 <3 <3</font>
 码字不易，大家的支持就是我坚持下去的动力。点赞后不要忘了<font color=red>关注</font>我哦！

><font color=blue><strong>笔记记得可能有点粗糙，如有错误之处，还请批评指正 ^ _ ^</font>
