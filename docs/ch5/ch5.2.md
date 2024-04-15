# 前言
==离散系统 z 域分析相关内容==

# 一、线性性质
若
 $f_1(k)  \longleftrightarrow F_1(z),\alpha_1<|z|<\beta_1$

$f_2(k)  \longleftrightarrow F_2(z),\alpha_2<|z|<\beta_2$

对于任意常数 $a_1,a_2$ ，则：

$a_1f_1(k)+a_2f_2(k)  \longleftrightarrow a_1F_1(z)+a_2F_2(z)$ ，收敛域至少是 $F_1(z)和 F_2(z)$ 收敛域的相交部分。

例：
><font color=black>$$2\delta(k)+3\epsilon(k)\longleftrightarrow2+\frac{3z}{z-1},|z|>1$$
# 二、移位特性
移位特性分单边和双边
**双边**：
若
 $f (k)  \longleftrightarrow F (z),\alpha <|z|<\beta$ ,且对**整数** $m>0$ ,则：

$f(k\pm m) \longleftrightarrow z^{\pm m}F(z),,\alpha <|z|<\beta$

**单边**：
若
 $f (k)  \longleftrightarrow F (z),|z|<\alpha$ ,且对**整数** $m>0$ ,则：
$$f(k-m)\longleftrightarrow z^{-m}F(z)+\sum_{k=0}^{m-1}f(k-m)z^{-k}$$

><font color=red size=3>$$f(k-1)\longleftrightarrow z^{-1}F(z)+f(-1)$$
>$$f(k-2)\longleftrightarrow z^{-2}F(z)+f(-2)+z^{-1}f(-1)$$

><font color=red size=3>$$f(k+1)\longleftrightarrow zF(z)-zf(0)$$
>$$f(k+2)\longleftrightarrow z^{2}F(z)-z^2f(0)-zf(1)$$

# 三、尺度变换
若
 $f (k)  \longleftrightarrow F (z),\alpha <|z|<\beta$ ,且有**常数** $a\ne 0$ ,则：

$$a^kF(k) \longleftrightarrow F(\frac{z}{a}),\alpha|a| <|z|<\beta|a|$$

例：$\cos(\beta k)\epsilon(k)$
><font color=black>$$\cos(\beta k)=\frac12(e^{j\beta k}+e^{-j\beta k})$$
$$\cos(\beta k)\epsilon(k)\longleftrightarrow\frac{0.5}{z-e^{j\beta}}+\frac{0.5}{z-e^{-j\beta}}$$
# 四、卷积定理
若
 $f_1(k)  \longleftrightarrow F_1(z),\alpha_1<|z|<\beta_1$

$f_2(k)  \longleftrightarrow F_2(z),\alpha_2<|z|<\beta_2$

则：
$f_1(k)*f_2(k)\longleftrightarrow F_1(z)F_2(z)$
# 五、z 域微分
若
 $f (k)  \longleftrightarrow F (z),\alpha <|z|<\beta$
 则：
 $$kf(k)\longleftrightarrow -z\frac{d}{dz}F(z)，\alpha <|z|<\beta$$
例：
><font color=black>$$k\epsilon(k) \longleftrightarrow-z\frac{d}{dz}(\frac{z}{z-1})=\frac{z}{(z-1)^2}$$
# 六、z 域积分
若
 $f (k)  \longleftrightarrow F (z),\alpha <|z|<\beta$ ,且对**整数** $m,k+m>0$ ,则：

$$\frac{f(k)}{k+m}\longleftrightarrow z^m\int_{z}^{+\infty}\frac{F(\eta)}{\eta^{m+1}}d\eta,\alpha <|z|<\beta$$

例：求序列 $\frac{1}{k+1}\epsilon(k)$ 的 $z$ 变换

><font color=black>$$\frac{1}{k+1}\epsilon(k)\longleftrightarrow z\int_{z}^{+\infty}\frac{\eta/\eta-1}{\eta^2}d\eta= z\int_{z}^{+\infty}\frac{ 1}{\eta(\eta-1)}d\eta=z\ln(\frac{z}{z-1})$$

# 七、z 域反转
若
 $f (k)  \longleftrightarrow F (z),\alpha <|z|<\beta$ 
则:
$f(-k)\longleftrightarrow F(z^{-1}),\frac1\beta <|z|<\frac1\alpha$
# 八、部分和
若
 $f (k)  \longleftrightarrow F (z),\alpha <|z|<\beta$ 
则:
$$\sum _{i=-\infty}^{k}f(i)\longleftrightarrow \frac{z}{z-1}F(z),max(\alpha,1)<|z|<\beta$$
# 总结
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503184207708.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
图片来自百度百科。

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。