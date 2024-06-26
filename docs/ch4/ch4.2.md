# 前言
==连续系统s域分析相关内容==
# 一、线性性质
若 :
$\mathcal{L}[f_1(t)]=F_1(s) , Re[s]>\sigma_1$ 

$\mathcal{L}[f_2(t)]=F_2(s) , Re[s]>\sigma_2$

则：$\mathcal{L}[a_1f_1(t)+a_2f_2(t)]=a_1F_1(t)+a_2F_2(t),Re[s]>max(\sigma_1,\sigma_2)$

><strong><font color=black>例：$\mathcal{L}[\delta(t)+\epsilon(t)]=1+1/s,\sigma>0$
# 二、尺度变换
若 :
$\mathcal{L}[f(t)]=F (s) , Re[s]>\sigma_0,且有实数 a>0$ 

则：
$$
\mathcal{L}[f(at)]=\frac{1}{a}F(\frac{s}{a}),Re[s]>a\sigma_0
$$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200412154939805.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =400x)
# 三、时移特性
若 :
$\mathcal{L}[f(t)]=F (s) , Re[s]>\sigma_0,且有实常数 t_0>0$ 

则：
$$
\mathcal{L}[f(t-t_0)\epsilon(t-t_0)]=e^{-st_0}F(s),Re[s]>\sigma_0
$$
例： $\mathcal{L}[f(at-t_0)\epsilon(at-t_0)]=?$

><strong><font color=black>先时移，再尺度变换，可得：$$\mathcal{L}[f(at-t_0)\epsilon(at-t_0)]=\frac{1}{a}e^{-\frac{s}{a}t_0}F(\frac{s}{a})$$

# 四、复频移特性
若 :
$\mathcal{L}[f(t)]=F (s) , Re[s]>\sigma_0,且有复常数 s_a=\sigma_a+j\omega_a$ 

则：
$$
 \mathcal{L}[f(t)e^{s_a t}] =F(s-s_a),Re[s]>\sigma_0+\sigma_a
$$

例：因果信号 $f(t)$ 的象函数 $$F(s)=\frac{s}{s^2+1}$$

问：$\mathcal{L}[e^{-t}f(3t-2)]=?$
><strong><font color=black>先时移，再尺度变换，最后复频移
>$$\mathcal{L}[f(t)]=\frac{s}{s^2+1}\implies\mathcal{L}[f(t-2)]=\frac{s}{s^2+1}\cdot e^{-2s}$$
>$$\mathcal{L}[f(3t-2)]=\frac{1}{3}\cdot\frac{s/3}{(s/3)^2+1}\cdot e^{-2(s/3)}=\frac{s }{s ^2+9}\cdot e^{-\frac{2s}{3}}$$
>$$\mathcal{L}[e^{-t}f(3t-2)]==\frac{s+1 }{(s+1) ^2+9}\cdot e^{-\frac{2(s+1)}{3}}$$
# <font color=red>五、时域的微分特性
<font color=red>若 :
$\mathcal{L}[f(t)]=F (s) , Re[s]>\sigma_0$ 

<font color=red>则：$$\mathcal{L}[f'(t)]=sF(s)-f(0_{-})$$
$$
\mathcal{L}[f''(t)]=s^2F(s)-sf(0_{-})-f'(0_{-})
$$
$$
\mathcal{L}[f^{(n)}(t)]=s^nF(s)-\Sigma_{m=0}^{n-1}s^{n-1-m}f^{(m)}(0_{-})
$$

若： $f(t)$ 为因果信号，则 $\mathcal{L}[f^{(n)}(t)]=s^nF(s)$
>因果信号时间轴从零开始，$f(0_{-})=0$

<font color=red>例：（1）$\mathcal{L}[\delta^{(n)}(t)]=?$ （2）$\mathcal{L}[\frac{d}{dt}[\epsilon(t)\cos2t]]=?$ （3）$\mathcal{L}[\frac{d}{dt}[ \cos2t]]=?$

><strong><font color=black>（1）$\mathcal{L}[\delta^{(n)}(t)]=s^n$
>（2）$\epsilon(t)\cos2t$ 含有 $\epsilon(t)$ ，为因果信号，利用公式，可得：$$\mathcal{L}[\frac{d}{dt}[\epsilon(t)\cos2t]]=s\cdot\frac{s}{s^2+4}，(\mathcal{L}[\cos2t]=\frac{s}{s^2+4})$$
>（3）$\cos2t$ 非因果信号，利用公式，可得：$$\mathcal{L}[\frac{d}{dt}[ \cos2t]]=sF(s)-f(0{-})=s\cdot\frac{s}{s^2+4}-1，\lbrace F(s)=\mathcal{L}[\cos2t]=\frac{s}{s^2+4}\rbrace$$

# 六、时域的积分特性
若 :
$\mathcal{L}[f(t)]=F (s) , Re[s]>\sigma_0$ 

则：
$$\mathcal{L}[\int _{0}^{t}f(\tau)d\tau]=\frac{F (s)}{s}+\frac{f^{(-1)}(0_{-})}{s}  $$

例：$\mathcal{L}[t^2\epsilon(t)]=?$

><strong><font color=black>（1）$$\mathcal{L}[t\epsilon(t)]= \mathcal{L}[\int _{0}^{t}\epsilon(\tau)d\tau]=\frac{1}{s}\cdot \frac{1}{s}=\frac{1}{s^2}，(\mathcal{L[\epsilon(t)]=\frac{1}{s}})$$
>（2）$$\mathcal{L}[t^2\epsilon(t)]= 2\mathcal{L}[\int _{0}^{t}\tau \epsilon(\tau)d\tau]=2\cdot\frac{1}{s}\cdot\frac{1}{s^2}=\frac{2}{s^3}$$


# 七、卷积定理
时域：若因果函数

 $\mathcal{L}[f_1(t)]=F_1(s),Re[s]>\sigma_1$

 $\mathcal{L}[f_2(t)]=F_2(s),Re[s]>\sigma_2$
 
则：$\mathcal{L}[f_1(t)*f_2(t)]=F_1(s)F_2(s)$

s域卷积定理：
$$\mathcal{L}[f_1(t)\cdot f_2(t)]=\frac{1}{2\pi j}\int_{\sigma-j\infty}^{\sigma+j\infty}F_1(\eta)F_2(s-\eta)d\eta$$

# 八、s域的微分与积分
若 :
$\mathcal{L}[f(t)]=F (s) , Re[s]>\sigma_0$ 

则：
$$\mathcal{L}[(-t)f(t)]=\frac{dF(s)}{ds}，\mathcal{L}[(-t)^nf(t)]=\frac{d^nF(s)}{ds^n}$$
$$\mathcal{L}[\frac{f(t)}{t}]=\int_{s}^{\infty}F(\eta)d\eta$$

例：$\mathcal{L}[t^2e^{-2t}\epsilon(t)]=?$

><strong><font color=black>$$\mathcal{L}[ e^{-2t}\epsilon(t)]=\frac{1}{s+2}\implies \mathcal{L}[t^2 e^{-2t}\epsilon(t)]=\frac{d^2}{ds^2}(\frac{1}{s+2})=\frac{2}{(s+2)^3}$$
# 九、初值定理和中值定理
初值： $$f(0_{+})=\lim_{t\to 0_{}+}f(t)=\lim_{s\to \infty}sF(s)$$
终值：若 $f(t)$ 当 $t\to \infty$ 时存在 ，且 $\mathcal{L}[f(t)]=F (s),Re[s]>\sigma_0,\sigma_0<0$
则：$$f(\infty)=\lim_{s\to 0}sF(s)$$

# 总结：
==拉普拉斯变换的性质== 和 ==傅里叶变换的性质== 注意区别

**性质很重要！！！性质很重要！！！性质很重要！！！**
<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。