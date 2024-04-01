>Author：AXYZdong 自动化专业 工科男
>**有一点思考，有一点想法，有一点理性！** 
>`定个小小目标，努力成为习惯！在最美的年华遇见更好的自己！`
>**CSDN@AXYZdong，CSDN首发，AXYZdong原创**
>唯一博客更新的地址为： 👉 **[AXYZdong的博客](https://blog.csdn.net/qq_43328313)** 👈


[video(video-npqVeRtF-1593575664146)(type-bilibili)(url-https://player.bilibili.com/player.html?aid=968735596)(image-https://ss.csdn.net/p?http://i1.hdslb.com/bfs/archive/b53ab56c9533315dc76c42ff2bf602d236ef4e9e.png)(title-Multisim这几个使用技巧要知道！！！)]

前往b站观看高清视频 👉 [Multisim这几个使用技巧要知道！！！](https://www.bilibili.com/video/BV1Np4y1S7XR/)

<br>

>Multisim 14 仿真

@[TOC]

<br>

## 一.	实验目的
1.	观测连续时间系统的时域分析。
2.	研究二阶串联电路的阶跃响应。
3.	观测更改参数对于连续系统的阶跃响应的影响。
4.	观测系统的状态轨迹的显示。
<br>

## 二.	实验原理
<br>

### 1. 状态轨迹简介
1、	任何变化的物理过程在第一时刻所处的 `“状态”`（状况、形态或姿态），都可以用若干被称为“状态变量”的物理量来描述。电路也不例外，若一个含储能元件的网络在不同时刻各支路电压、电流都在变化，那么电路在不同时刻所处的状态也不相同。

2、	对 n 阶网络可以用n个状态变量来描述。可以设想一个 n 维空间，每一维表示一个状态变量，构成一个`“状态空间”`。网络在每一时刻所处的状态可以用状态空间中一个点来表达，随着时间的变化，点的移动形成一个轨迹，称为“状态轨迹”。二阶网络的状态空间就是一个平面，状态轨迹是平面上的一条曲线。一个 n 阶系统，只能有 n 个状态变量，不能多也不可少，且 n 个状态变量间线性无关的。

3、	为便于用双踪示波器直接观察到网络的状态轨迹，本实验仅研究 `RLC 串联电路`构成的二阶网络，它的状态轨迹可在二维状态平面上表示。
<br>

### 2. R，L，C的电压电流关系
        
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613172404344.png#pic_center) 

$$
        \to
        \begin{cases}
        i_R=\frac{u_R}{R}\\
        \\
        u_R=i_R\cdot R
        \end{cases}
$$
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613172741476.png#pic_center)     
$$
        \to
        \begin{cases}
       u_L(t)=L\frac{di_L(t)}{dt}\\
        \\
       i_L(t)=\frac{1}{L}\int_{-\infty}^{t}u_L(\tau)d\tau
        \end{cases}
$$
<br>


       
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613173131732.png#pic_center)       
$$
        \to
        \begin{cases}
       i_C(t)=C\frac{du_C(t)}{dt}\\
        \\
       u_C(t)= \int_{-\infty}^{t}i_C(\tau)d\tau
        \end{cases}
$$
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613173300149.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center)
</p><center><sup><code>▲ RLC串联电路 </code></sup></center><p></p>     
<br>

 >插播一条反爬虫信息，读者可以忽略：
><br>
>![在这里插入图片描述](https://img-blog.csdnimg.cn/20200604235654825.gif#pic_center =500x)

### 3. 求解状态方程

如图所示的RLC串联电路，选取 $i_L$ 和 $u_C$ 为中间状态， $u_C$  为输出， $u_i$  为输入。根据电压关系，
$$i_LR+L\frac{di_L}{dt}+u_c=u_i  \tag1$$	                   	 

求得相应的微分方程(状态方程)为：

$$
        \to
        \begin{cases}
      u'_c=\frac{1}{C}i_L\tag 2\\
        \\
       i'_L=-\frac{1}{L}u_c-\frac{R}{L}i_L+\frac{1}{L}u_i 
        \end{cases}
$$
	                  
由(2) 式不难看出，当已知电路的激励电压ui和初始条件 $i_L(t_0)$、$u_c(t_0)$，就可以唯一地确定 $t≥t_0$ 时，该电路的电流和电容两端的电压 $u_c$。
将$$i_C(t)=C\frac{du_C(t)}{dt}$$ 带入(1)式，相应的输入输出之间的关系：
$$LC\frac{d^2u_c}{dt^2}+RC\frac{du_c}{dt}+u_c=u_i\tag 3$$


根据(3)式整理得：
$$\frac{d^2u_c}{dt^2}+\frac{R}{L}\frac{du_c}{dt}+\frac{1}{LC}u_c=\frac{1}{LC}u_i\tag 4$$

二阶网络标准化形成的微分方程为
$$\frac{d^2u_c}{dt^2}+2\xi\omega_n\frac{du_c}{dt}+\omega^2_nu_c=\omega^2_nu_i\tag 5$$

其中 $ξ$ 称为阻尼比，  $\omega$ 称为无阻尼自振角频率。
比较（4）式和（5）式，得
  $$\omega_n=\frac{1}{\sqrt{LC}}
\\
ξ=\frac{R}{2}\sqrt{\frac{C}{L}}\tag 6$$
由（6）式可知，改变 $R、L和C$ ，使电路分别处于 $ξ＝0、0＜ξ＜1 和 ξ＞1$ 三种状态。根据（3）式，可直接解得 $u_C(t)$ 和 $i_L(t)$  。如果以 $t$ 为参变量，求出 $i_L=f( u_C)$ 的关系，并把这个关系，画在 $u_C-i_L(t)$ 平面上。显然，后者同样能描述电路的运动情况。
<br>


### 4. 不同阻尼下的状态轨迹


 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613180054669.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_70#pic_center =600x)
 </p><center><sup><code>▲  RLC电路在过阻尼时的状态轨迹 </code></sup></center><p></p>     
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613180134684.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center =600x)
</p><center><sup><code>▲  RLC电路在欠阻尼时的状态轨迹 </code></sup></center><p></p>     
<br>
 
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2020061318021755.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center =600x)
 </p><center><sup><code>▲  RLC电路在R=0时的状态轨迹 </code></sup></center><p></p>     
<br>


- 李沙育图是电压电流瞬时相互关系的图形表示，即状态轨迹。如果电压电流同是正弦，图是椭圆，长轴和水平轴之间的夹角就是电压电流差角。
<br>

### 5. 实验原理图
- 实验原理线路如图所示，$R=R1+R2=R1+33Ω$，改变 $R1$ 也就改变了 $R$ 的值， $ξ$ 值也会改变，从而使电路处于过阻尼、欠阻尼和临界阻尼的状态。为了便于测量，$R2$ 两端的电压和 $i_L$ 成正比，只要将  $U_{R_2}$ 和 $U_C$ 加到示波器的两个输入端，其李萨如图形即为该电路的状态轨迹。但示波器的两个输入必须有一个共地端，而   $U_{R_2}$  和 $U_C$ 没有共地端，因此必须将 （A点和B点）通过如图 的减法器（取 $R1=Rf$ ），将双端输入的 $U_C$ 变为与 $U_{R  }$  一个公共端的单端输出。这样，电容两端的电压  $U_{R  }$ 和 $U_C$ 有一个公共接地端，从而能正确地观察该电路的状态轨迹。

- 在本实验中，观察状态轨迹采用简易方法，由于 $R2$ 阻值很小，在B点电压仍表现为容性，因此电容电压可看成A和GND之间的电压。实验箱一般都是采用这种近似方法。
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613183617600.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center =500x)

 </p><center><sup><code>▲  Multisim 图</code></sup></center><p></p>     
<br>
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613183649439.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center =400x)
 </p><center><sup><code>▲ 减法器电路     </code></sup></center><p></p>     
<br>
 

## 三. 仿真结果
<br>


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613184626822.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center =600x)
 </p><center><sup><code>▲ Ui 和 iL波形    </code></sup></center><p></p>     
<br>


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613184449745.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_35,color_FFF000,t_70#pic_center =600x)
 </p><center><sup><code>▲ 状态轨迹     </code></sup></center><p></p>     
<br>

## 四. 总结
- 临界阻尼的计算
- 输入信号的选择：幅度 $4V$、频率 $f=1KHz$ 、占空比50%的方波
- 显示李萨如图形：示波器工作模式选择 `A/B` 


\
更多相关文章：

[【信号与系统】常用信号的分析与基本运算 (Matlab实现)](https://blog.csdn.net/qq_43328313/article/details/105897569)

[【信号与系统】Multisim 仿真信号合成与分解](https://blog.csdn.net/qq_43328313/article/details/106722506)

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
