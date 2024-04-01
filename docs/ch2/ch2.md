>Author：AXYZdong
>自动化专业 工科男
>有一点思考，有一点想法，有一点理性！

@[TOC]
# 前言
以下内容是关于==连续系统的时域分析==，重点难点，考试常考，考前复习。

# 一、系统的微分方程及其响应
## 1、LTI系统的微分方程
描述线性时不变（LTI）系统的输入--输出特性的是==常系数线性微分方程==

时域分析方法：从系统的模型（微分方程）出发，在时域研究输入信号通过系统响应后的变化规律，是研究系统时域特性的重要方法。

对于电系统，建立其微分方程的依据：
$$
KCL:\sum i(t)=0\\
KVL: \sum u(t)=0\\
VCR:U_R(t)=R \cdot i(t),u_L(t)=L\cdot \frac{di(t)}{dt},i_C(t)=C \cdot \frac{du(t)}{dt}
$$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200311191921975.png#pic_center)
对于图（a）中RC电路
$$
RC \cdot  \frac{du_C(t)}{dt} +u_C(t)=u_S(t)\\
即:u ' _C(t) + \frac{1}{RC} \cdot u_C(t) =  \frac{1}{RC} \cdot u_S(t)
$$
对于图（b）中RL电路
$$
 \frac{L \cdot di_L(t)}{R \cdot dt} +i_L(t)=i_S(t)\\
即:i ' _L(t) + \frac{R}{L} \cdot i_L(t) =  \frac{R}{L} \cdot i_S(t)
$$
以上可以总结出一般形式：==$y '(t)+ay(t)=\chi(t)$==
## 2、系统的响应
### 2.1、零输入响应（储能响应）
从观察的初始时刻起不再施加输入信号，仅由该时刻系统本身的起始储能状态引起的响应称为零输入响应（ZIR）
### 2.2、零状态响应（受激响应）
当系统的储能状态为零时，由外加激励信号（输入）产生的响应称为零状态响应（ZSR）

对于一阶系统方程
$$
y '(t)+ay(t)=\chi(t)
$$
零状态响应：
$$
y_{ZS}(t)=\rm e^{-at} \int_{0-}^t \chi(t) e^{a \tau} d \tau,(t \geq0)
$$
### 2.3、完全响应

<font color =red>$$
y(t)=y_{ZI}(t)+y_{ZS}(t),[全响应=零输入+零状态]
$$</font>

### 2.4、例一($y ''(t) + 6y '(t) + 8y(t) =f(t),t>0$)
已知某二阶线性连续时间系统的动态方程：
$$
y''(t) + 6y'(t) + 8y(t) =f(t),t>0\\
初始条件：y({0_-})=1,y' ({0_-})=2,求系统的零输入响应
$$
解：

$系统的特征方程：s^2+6s+8=0,特征根：s_1=-2，s_2=-4 \\
故系统的零输入响应：y_X(t)=k_1e^{-2t} + k_2e^{-4t},t>0 \\
y_X({0_+})=y_X({0_-}) = y_X({0}) =		k_1+k_2=1\\
y'(0)=y_X'({0_-}) = -2k_1-4k_2=2\\
 y_X({0})和y'(0)代入 可解出：k_1=3，k_2=-2$

可得零输入响应：$y_X(t)=3e^{-2t}-2e^{-4t},t \ge0$
### 2.5、例二($y ''(t) + 3y'(t) + 2y(t) =2f'(t)+6f(t),t>0$)
$$
y ''(t) + 3y'(t) + 2y(t) =2f'(t)+6f(t),t>0\\
初始条件：y({0_-})=2,y \prime ({0_-})=0,f(t)= \epsilon(t), \\
求系统的零输入响应和零状态响应\\
$$
解：
$(1)零输入响应y_X(t)激励为0，故y_X(t)满足$

$y _X''(t) + 3y_X'(t) + 2y_X(t) =0\\
系统的特征方程：s^2+3s+2=0,特征根：s_1=-2，s_2=-1 \\
故系统的零输入响应：y_X(t)=k_1e^{-2t} + k_2e^{-t},t>0 \\
y_X({0_+})=y_X({0_-}) = y_X({0}) =2\\
y'(0)=y_X'({0_-}) = 0\\
y_X({0})和y'(0)代入 可解出：k_1=4，k_2=-2$

可得零输入响应：$y_X(t)=4e^{-t}-2e^{-2t},t >0$

$(2)零状态响应y_f(t)满足$
$$
y _f''(t) + 3y_f'(t) + 2y_f(t) =2 \delta (t)+6 \epsilon(t),并有y_f({0_-}) = y_f({0_+})  = 0\\
$$
<font color=red> $由于上式等号右端含有 \delta(t) , 故y _f''(t)含有 \delta(t)，从而y_f'(t)跃变  ,即y'_f({0_+}) \neq y'_f({0_-})\\ 
而y_f(t) 在t=0处连续，即y_f({0_-}) = y_f({0_+})=0，上式两边积分有：\\
[y'_f({0_+}) - y'_f({0_-})]+3[y_f({0_-}) -y_f({0_+})]+2\int_{0-}^{0+}y_f(t) dt=2+6\int_{0-}^{0+} \epsilon(t)dt$</font>

整理得：$y'_f({0_+}) =2+ y'_f({0_-})=2$

对$t>0$时，有$y _f''(t) + 3y_f'(t) + 2y_f(t) =6$

不难求出其齐次解为：$C_{f1}e^{-t}+C_{f2}e^{-2t},$其特解为常数$3$

$\therefore y_f(t)=C_{f1}e^{-t}+C_{f2}e^{-2t}+3$

代入初值求得：$y_f(t)=-4e^{-t}+e^{-2t}+3,t \geq0$
### 2.6、响应的分类
|分类标准|对应响应|
|--|--|
|响应的不同起因|储能响应、受激响应|
|系统的性质和输入信号的性质|自由响应（取决于系统性质，即特征根）、强迫响应（取决于输入信号的形式）|
|响应的变化形式|瞬态响应（t无限增大，响应趋于零）、稳态响应（响应恒定或为某个稳态函数）|
# 二、阶跃响应
## 1、定义
LTI系统在零状态下，由单位阶跃信号引起的响应称为单位阶跃响应，简称阶跃响应，记为$s(t)$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200311212512800.png#pic_center)
## 2、一阶系统方程的阶跃响应
对于一阶系统方程
$$
y '(t)+ay(t)=b\epsilon(t)
$$
则零状态响应：
$$
y_{ZS}(t)=\rm e^{-at} \int_{0-}^t \chi(t) e^{a \tau} d \tau,(t \geq0)
$$
则阶跃响应：
$$
y (t)=s(t)=\rm e^{-at} \int_{0-}^t b\epsilon(t) e^{a \tau} d \tau = \frac {b}{a} \cdot(1-e^{-at}),(t \geq0)
$$
## 3、阶跃响应的测量
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200311213101527.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
# 三、冲激响应
## 1、定义
储能状态为零的系统，在单位冲激信号作用下产生的零状态响应称为冲激响应，记为$h(t)$
## 2、一阶系统的冲激响应
对于一阶系统方程
$$
y '(t)+ay(t)=b\delta(t)
$$
则冲激响应：
$$
y (t)=h(t)=\rm e^{-at} \int_{0-}^t b\delta(t) e^{a \tau} d \tau = b \cdot e^{-at} \cdot \epsilon(t)
$$
## 3、例一（$y''(t)+5y'(t)+6y(t)=f(t)$）
描述某系统的微分方程为$y''(t)+5y'(t)+6y(t)=f(t)$，求其冲激响应$h(t)$

解：根据$h(t)$定义有$h''(t)+5h'(t)+6h(t)= \delta(t),\\
并且有 h'({0_-}) = h({0_-})  = 0，先求h'({0_+})  和 h({0_+})$

<font color=red> $由于上式等号右端含有 \delta(t) , 故h''(t)含有 \delta(t)，从而h'(t)跃变  ,即h' ({0_+}) \neq h'({0_-})\\ 
而h(t) 在t=0处连续，即h({0_-}) = h({0_+})=0，上式两边积分有：\\
[h'({0_+}) - h'({0_-})]+5[h({0_-}) -h({0_+})]+6\int_{0-}^{0+}h(t) dt=1$</font>

整理得：$h'({0_+}) =1+ h'({0_-})=1$

对$t>0$时，有$h''(t)+5h'(t)+6h(t)=0$

不难求出其齐次解为：$C_{1}e^{-2t}+C_{2}e^{-3t},$

$\therefore h(t)=(C_{1}e^{-2t}+C_{2}e^{-3t}) \cdot \epsilon(t)$

代入初值求得：$h(t)=(e^{-2t}-e^{-3t})   \cdot \epsilon(t)$
## 4、例二（$y''(t)+5y'(t)+6y(t)=f''(t)+2f'(t)+3f(t)$）
描述某系统的微分方程为$y''(t)+5y'(t)+6y(t)=f''(t)+2f'(t)+3f(t)$，求其冲激响应$h(t)$

解：根据$h(t)$定义有
$$h''(t)+5h'(t)+6h(t)=\delta''(t) + 2\delta'(t) +3\delta(t)  \\
\tag{1}
$$
$并且有 h'({0_-}) = h({0_-})  = 0，先求h'({0_+})  和 h({0_+})$
由方程可知：$h(t)$中含有$\delta(t)$
故令：
$$\begin{cases}
h(t)=a \delta(t) +P_1(t) , [P_i(t)中为不含有\delta(t的函数) ]\\
h'(t)=a \delta'(t) + b \delta(t) + P_2(t)\\
h''(t)=a \delta''(t) + b \delta'(t) + c \delta(t) + P_3(t)\\
\end{cases}$$
代入式（1）整理得：
$$
a \delta''(t) + (b+5a) \delta'(t) + (6a+5b+c) \delta(t) + P_1(t)+P_2(t)+ P_3(t)=\delta''(t) + 2\delta'(t) +3\delta(t)
$$
利用$\delta(t)$系数匹配，得$a=1,b=-3,c=12$
$$h(t)=  \delta(t) +P_1(t)  
\tag{2}$$
$$h'(t)=  \delta'(t) -3 \delta(t) + P_2(t) 
\tag{3}
$$
$$h''(t)=  \delta''(t) -3 \delta'(t) + 12 \delta(t) + P_3(t)
\tag{4}$$
$对式（3）从0_{-}到0_{+}积分h(0_{+})-h(0_{-})=-3 \\ 对式（4）从0_{-}到0_{+}积分h'(0_{+})-h'(0_{-})=12$

对$t>0$时,有$h''(t)+5h'(t)+6h(t)=0,特征根-2，-3$

不难求出其齐次解为：$C_{1}e^{-2t}+C_{2}e^{-3t},$

$\therefore h(t)=(C_{1}e^{-2t}+C_{2}e^{-3t}) \cdot \epsilon(t)$

代入初始条件$h(0_{+})=-3,h'(0_{+}) =12$求得：$h(t)=(3e^{-2t}-6e^{-3t})   \cdot \epsilon(t)$

$结合式（2），h(t)= \delta(t)+(3e^{-2t}-6e^{-3t}) \cdot \epsilon(t)$
## 5、阶跃响应与冲激响应的关系
$$
\begin{cases}
h(t)= \frac{ds(t)}{dt}\\
\\
s(t)= \int _{-\infty}^{t}h( \tau ) d \tau
\end{cases}
$$
# 四、卷积及其应用
## 1、信号的时域分解与卷积积分
### 1.1任意信号的分解
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020031314303840.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
$“0"$号脉冲高度$f(0)$，宽度$\Delta$，用$p(t)$表示为 $f(0) \Delta p(t)$

$“1"$号脉冲高度$f(\Delta)$，宽度$\Delta$，用$p(t-\Delta)$表示为 $f(\Delta) \Delta p(t-\Delta)$

$“-1"$号脉冲高度$f(-\Delta)$，宽度$\Delta$，用$p(t+\Delta)$表示为 $f(-\Delta) \Delta p(t+\Delta)$

$\hat {f(t)}=\sum_{n=-\infty}^{\infty}f(n\Delta) \Delta p(t-n\Delta)$

$$
\lim_{\Delta \to 0} \hat{f(t)} =f(t) = \int _{-\infty}^{\infty} f(\tau) \delta(t- \tau) d \tau
$$
### 1.2任意信号作用下的零输入响应
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200313144942934.png#pic_center)
根据$h(t)$定义：
$$
\delta(t)  \implies h(t)
$$
由时不变性：
$$
\delta(t - \tau)  \implies h(t - \tau)
$$
由齐次性：
$$
f(\tau) \delta(t - \tau)  \implies f(\tau) h (t - \tau)
$$
由叠加性：
$$
\int_{- \infty}^{+\infty} f(\tau) \delta(t - \tau)  d\tau \implies  \int_{- \infty}^{+\infty} f(\tau) h (t - \tau) d\tau
$$
$$
y_f(t)=\int_{- \infty}^{+\infty} f(\tau) h(t - \tau) d\tau  ,卷积积分
$$
### 1.3卷积积分的定义
已知定义在区间$(-\infty,+\infty)$上的两个函数$f_1(t)$和$f_2(t)$，则定义积分$f(t)=\int_{- \infty}^{+\infty} f_1(\tau) f_2(t - \tau) d\tau$
为$f_1(t)$和$f_2(t)$的卷积积分，简称卷积；记为
$$
f(t)=f_1(t) *f_2(t)
$$
<font color=red>温馨提醒：$\tau$  为积分变量，积分后的结果为关于 $t$  的函数</font>
$$
y_f(t)=\int_{- \infty}^{+\infty} f(\tau) h(t - \tau) d\tau =f_1(t) *h(t)
$$
## 2、卷积的图解法
$$
 f_1(t) *f_2(t) = \int_{- \infty}^{+\infty} f_1(\tau) f_2(t - \tau) d\tau
$$
四步图解法：
（1）换元：$t  换为 \tau \to f_1(\tau), f_2(\tau)$

（2）反转平移（折叠平移）：$f_2(\tau)反转\to f_2(-\tau),再右移t\to  f_2(-(\tau -t))=f_2(t- \tau)$<font color=red>【左加右减在$\tau$的里面】</font>

（3）乘积：$f_1(\tau) f_2(t - \tau)$

（4）积分：$\tau$从$-\infty$到$+\infty$对乘积项积分

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200313161546962.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =550x)
总结：图解法步骤比较繁杂，但是按照四步法“战略”就可以一步步把题目搞定。不过，图解法对于求某一时刻的卷积值还是比较方便的，对于简单的信号，通过画图就可以直观的求出某一时刻的卷积值。

# 五、卷积积分的性质 
## 1、奇异（冲激）函数的卷积特性
1、$f(t)*\delta(t) = \delta(t)* f(t) = f(t)$

2、$f(t)* \delta'(t) = f'(t) , f(t)* \delta^{(n)}(t) = f^{(n)}(t)$

3、$f(t)*\epsilon(t) = \int_{-\infty}^{+\infty} f(\tau) \epsilon(t- \tau)d\tau = \int_{-\infty}^{t} f(\tau)  d\tau$

<font color=red>$\epsilon(t)*\epsilon(t) = t\epsilon(t)$【重点关注】</font>
## 2、卷积的微积分性质


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200313161615756.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_20,color_FFFFFF,t_70#pic_center =500x) 
## 3、卷积的时移特性
卷积的时移特性说白了就是：一个卷积积分，时间 $t$ 无论左移还是右移，其积分值等于相应函数左移或右移后的函数值。下面通过一个公式来说明：
若：$f(t)=f_1(t)*f_2(t),$
则：$f_1(t-t_1)*f_2(t-t_2) \\
= f_1(t-t_1-t_2)*f_2(t)\\
= f_1(t)*f_2(t-t_1-t_2)\\
=f (t-t_1-t_2)$
# 总结
连续系统的时域分析，重点难点内容，多看、多做、多动手。

<strong><font color=red>零输入、零状态、阶跃、冲激
卷积积分【重点关注】</font>
<br>

「你可能还想看」系列文章：
[【信号与系统】笔记合集，你确定不收藏吗？我已经收藏了](https://axyzdong.blog.csdn.net/article/details/105909575)

><strong>上一篇笔记承蒙各位小伙伴的厚爱，访问量蹭蹭上涨，然而我不食言，继续更，希望喜欢。
如果文章中有哪些知识点<font color=blue>写错</font>的地方，欢迎私信我
如果文章中哪些知识点<font color=blue>不理解</font>的地方，欢迎私信我
如果文章中还有哪些需要<font color=blue>补充</font>的地方，欢迎私信我

 <strong>码字不易，大家的支持就是我坚持下去的动力。点赞后不要忘了关注我哦！
