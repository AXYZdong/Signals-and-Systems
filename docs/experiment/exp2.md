>Author：AXYZdong 自动化专业 工科男
>**有一点思考，有一点想法，有一点理性！** 
>`定个小小目标，努力成为习惯！在最美的年华遇见更好的自己！`
>**CSDN@AXYZdong，CSDN首发，AXYZdong原创**
>唯一博客更新的地址为： 👉 **[AXYZdong的博客](https://blog.csdn.net/qq_43328313)** 👈


[video(video-npqVeRtF-1593575664146)(type-bilibili)(url-https://player.bilibili.com/player.html?aid=968735596)(image-https://ss.csdn.net/p?http://i1.hdslb.com/bfs/archive/b53ab56c9533315dc76c42ff2bf602d236ef4e9e.png)(title-Multisim这几个使用技巧要知道！！！)]
前往b站观看高清视频 👉 [Multisim这几个使用技巧要知道！！！](https://www.bilibili.com/video/BV1Np4y1S7XR/)

<br>

><font color=black>Multisim 14 仿真</font>

<br>

@[TOC]


## 一. 实验目的
1. 观察信号波形的分解与合成，加深对信号频谱的理解。
2. 学会用软件 Multisim 进行方波信号的产生、分解和合成。
<br>

## 二. 实验原理
任何电信号都可由不同频率、不同幅度和不同初相的正弦信号叠加而成。

对于周期性信号，其各次谐波的频率为基波频率的整数倍，而非周期性信号则包含有从零到无穷大的所有频率分量，每个分量的幅度都趋向无限小，但其相对大小是不同的。

以方波信号为例：当f (t)为一周期性方波（幅度为 ，周期 T，占空比为 50%）
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200612194655323.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_70#pic_center)
 <br>
 
只有 1、3、5、7、......等奇次谐波分量,偶次谐波为 0.
例如 A=5，信号幅度为-5V—+5V，理论上偶次谐波为 0，根据上面的公式可得出 1、3、5次谐波分量信号峰峰值分别为下表中的值：
     
分析实验的功能与性能指标： 
功能：此次实验主要功能是实现信号的产生，并让我们在对信号的分解过程中体会傅里叶级数对周期信号的展开，以及滤波器的设计（该实验主要使用带通和全通滤波器（即移相器）），最后通过将分解出的谐波分量合成。
性能指标：
- 对于方波而言：频率要为 1kHz，幅度为 5V（即峰峰值为 10V），方波关键顶部尽可能是直线，而不是斜线。
- `滤出的基波`：波形要为正弦波，频率为 1kHz，幅度理论值为 6.37V（注：其实滤除的基波幅度只要不太离谱即可，因为后面的加法器电路可以调整增益，可以调到6.37V，后面的 3 次谐波也一样）故最主要的是波形和频率。
- `3 次谐波`：波形要为正弦波，频率为 3kHz，幅度理论值为 2.12V。
- `移相器（即全通滤波器）`：不能对信号的幅度和频率有影响，只能改变信号的相位，使信号与输入方波的相位相等。
- `加法器`：能够弥补滤波出的信号幅度与理论值的误差，将各个谐波分量合成。
- 最后合成的信号与产生的方波信号相位与频率应相等。

实验电路的结构如下：
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200612195006427.png#pic_center)

<br>

>插播一条反爬虫信息，读者可以忽略：
><br>
>![在这里插入图片描述](https://img-blog.csdnimg.cn/20200604235654825.gif#pic_center =500x)

<br>

### 1. 方波发生电路（Multisim 仿真）
如图所示的是运放实现的方波发生器原理图，也可以用 NE555 产生方波, 由反相滞回比
较器和 RC 充放电电路构成，输出的方波幅值由二极管限定。
- `滞回比较器的阈值为` $$\pm U_T =\frac{R_1}{R_1+R_2}U_Z$$ 
- `方波的周期为` $$T=2R_3C\ln\frac{2R_1}{R2}$$

 <br>
 
可取 $R3=2KΩ+100KΩ$ 的电位器组成。另外输出需要 5Vp,可以使用 ZPD5.1 的稳压管，后面再接电位器分压即可。使用 multisim 搭建电路。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200612200006654.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_18,color_FFF000,t_70#pic_center)
<br>

### 2. 分解出基波（Multisim 仿真）
波形为正弦波，频率为 1kHz，峰峰值理论上 12.732V，幅度可以允许存在误差，在后面的加法器进行调整，故最主要的是波形和频率。从方波中提取出一次谐波可以通过设计一个二阶有源低通滤波器实现。二阶有源低通滤波器的 `转移函数` 为： 
<br>

$$A(s)=\frac{A_{uf}\omega_0^2}{s^2+\frac{\omega_0}{Q}s+\omega_0^2}$$
<br>


### 3. 分解出三次谐波，频率 3*1000=3000Hz：
- 三次谐波波形为正弦波，频率为 3kHz，峰峰值理论上 4.244V。
- 从方波中提取三次谐波可以通过设计一个四阶有源带通滤波器实现。
- 加入三次谐波之后，方波受干扰，所以方波输出后加入了电压跟随器，起缓冲、隔离、提高带载能力的作用。三次谐波的周期是原信号方波的 1/3 倍，也就是一个周期的原信号方波对应三个周期的基波。

<br>

### 4. 移相电路（Multisim 仿真）
<br>

#### (1) 波形合成时为何需要移相电路？
移相是由于电路附带的电容引起的，在方波——正弦波的转换过程中，相移在所难免的，这就需要移相来解决附加相移。移相电路是对分频滤波以后的各个谐波信号进行相位的调整，是它们的相位关系能同步。初相对合成波形的影响如图所示。 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200612200212928.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_100#pic_center)
<br>
#### (2) 移相电路应该怎样调节？
应该先调节好各次谐波的相位再合成？还是将各次谐波合成后，再调节移相电路？以原始的方波信号为基准信号，接到示波器的 `CH1` 输入端，将移相网络的输出端接到 `CH2` 端，双踪是示波，通过可变电阻对输出的相移进行改变，输入输出比表达式应该是 `Rw` 的函数;应先将滤好的各次谐波分别移相后再合成。由于滤波器用到了对不同频率有不同响应的储能元件，对于滤除的波形会产生不同的附加相位，并且加法电路不含相移功能，此时设计一个相移网络是不同频率的波形经过其得到符合各自要求移相比较困难或者根本不可能实现，因此要对各次谐波进行不同程度的移相。
<br>

#### (3) 具体电路
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2020061220033566.png#pic_center)
从上面的设计图和实际此时的结果来看，我们的滤波器会使滤除的波形相对于原来的超前，但是由于采用了反相加法电路进行最后的波形叠加，相当于给每个谐波的相位不上 180度，反而能使相位超期，即时用如图的移相电路进行移相。
<br>


### 5. 基波和三次谐波的合成（Multisim 仿真）
 
如果分解出更多的谐波，然后将它们移相后叠加，如图中所示，越来越接近与原信号
方波 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200612200502105.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_100#pic_center)
<br>

## 三. 仿真结果
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200612200641674.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_F00000,t_70#pic_center =550x)
</p><center><sup><code>▲ 基波 + 三次谐波 合成</code></sup></center><p></p>
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020061220073829.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_F00000,t_70#pic_center =550x)
</p><center><sup><code>▲ 基波 + 三次谐波 + 五次谐波 合成</code></sup></center><p></p>
<br>

## 四. 实验总结
- 五次谐波加上去合成效果不是太明显，一方面由于五次谐波幅值本来就小，另一方面由于仿真的误差，对于最终波形的合成也有很大影响。
- 方波产生 $\to$ 滤波电路 $\to$ 移相电路 $\to$ 波形合成
- Multisim 中电路 `子模块` 化的使用。

\
更多相关文章：

[【信号与系统】常用信号的分析与基本运算 (Matlab实现)](https://blog.csdn.net/qq_43328313/article/details/105897569)

[【信号与系统】Multisim 仿真连续时间系统的时域分析](https://blog.csdn.net/qq_43328313/article/details/106735174)

[【信号与系统】Multisim 仿真抽样定理与信号恢复](https://blog.csdn.net/qq_43328313/article/details/107332349)

[【信号与系统】笔记合集，你确定不收藏吗？我已经收藏了](https://axyzdong.blog.csdn.net/article/details/105909575)
<br>

\
**&emsp;&emsp;本次的分享就到这里**
***
![11](https://img-blog.csdnimg.cn/20200501223603394.gif#pic_center)

好书不厌百回读，熟读自知其中意。将学习成为习惯，用知识改变命运，用博客见证成长，用行动证明努力。
如果我的博客对你有帮助、如果你喜欢我的博客内容，请 **`“点赞”  “评论” “收藏”`** 一键三连哦！
**听说 👉 <font color=red> 点赞</font> 👈 的人运气不会太差，每一天都会元气满满呦！**^ _ ^ <3 <3 <3</font>
 **码字不易，大家的支持就是我坚持下去的动力。点赞后不要忘了👉<font color=red>关注</font>👈我哦！
 更多精彩内容请前往 [AXYZdong的博客](https://blog.csdn.net/qq_43328313)**
<hr><p>如果以上内容有任何错误或者不准确的地方，欢迎在下面👇留个言。或者你有更好的想法，欢迎一起交流学习~~~</p> 
