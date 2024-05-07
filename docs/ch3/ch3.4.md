# 前言
**连续系统的频域分析** 最后一部分内容。

# 一、系统的频域分析
## 1、系统函数（信号传输的纽带与桥梁）
时域、频域分析对应关系

$f(t) \longrightarrow h(t) \longrightarrow y(t)=f(t)*h(t)$

$F(\omega) \longrightarrow H(j\omega) \longrightarrow Y(\omega)=F(\omega)H(j\omega)$

系统函数定义为：
$$
H(j\omega)=\frac{Y(\omega)}{F(\omega)}
$$
$H(j\omega)$ 即系统的频率特性

变换对：
$$H(j \omega)= \int_{-\infty}^{\infty} h(t) e^{-j  \omega t}dt$$

$$h(t)= \frac{1}{2\pi}\int_{-\infty}^{\infty} H(j\omega) e^{j  \omega t}d\omega$$

<font color=red>例：某LTI系统的 $H(j\omega)$ 和 $\theta(\omega)$ 如图，若 $f(t)=2+4\cos(5t)+4\cos(10t)$ ，求系统的响应。</font>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200403175356286.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =300x )<center><sup><sup>$H(j\omega)$ 和 $\theta(\omega)$ 图像</sup></sup>

解：
$f(t) 的基波角频率 \Omega = 5rad/s\\
f(t)=2+4\cos(\Omega t)+4\cos(2\Omega t)\\
H(0)=1,H(j\omega)=0.5e^{-j0.5\pi},H(j2\Omega)=0\\
y(t)=2+4\times0.5\cos(\Omega t-0.5\pi)=2 + 2\sin(5t)$

## 2、无失真传输条件

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200328165559976.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =450x)

时域条件：$y(t) =Kf(t-t_0)$

频域条件:  $Y(\omega)=KF(\omega) e^{-j\omega t_0}$

系统函数：$H(j\omega)=\frac{Y(\omega)}{F(\omega)}=Ke^{-j\omega t_0}$

# 二、取样定理
## 1、取样信号

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200328170709624.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70 =600x)

## 2、取样定理
若 $f(t)$ 为带宽有限的连续信号，其频谱的最高频率为 $f_m$ , 则以取样间隔 $T\leq \frac{1}{2f_m}$ 对 $f(t)$ 均匀取样所得的 $f_s(t)$ 将包含原信号 $f(t)$ 的全部信息。因而可以从 $f_s(t)$ 完全恢复信号。

## 3、取样定理的意义

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200328171426945.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)

1、连续信号离散化，为 **信号的数字处理** 奠定基础。
2、信号的时分复用，为 **多路信号的传输** 提供理论基础。

# 三、章节小测验
老师刚给的形成性评价作业题，发布之前顺便也加到博客上。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200403233430439.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_50,color_DFFFFF,t_70#pic_center)
<center><sup><sup>四个小题目</sup></sup><center>


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200403233641698.JPG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_120,color_FFFFFF,t_70#pic_center)
<center><sup><sup>我的解答过程</sup></sup><center>

# 总结
**连续系统的频域分析** 这部分内容结束。

<font color=red>**周期信号**	、**非周期信号** 、**傅里叶级数** 、**信号的频谱** 、**傅里叶变换** 、**常用的傅里叶变换对** 、 **傅里叶变换的性质**、**LTI系统的频域分析**</font>
<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

