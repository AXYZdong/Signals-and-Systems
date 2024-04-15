## 一.	实验目的
1.	观察离散信号频谱，了解其频谱特点。
2.	验证抽样定理并恢复原信号。
<br>

## 二.	实验原理
1、	由于离散时间信号处理更为灵活，所以工程中将连续信号转化为离散信号进行处理，然后再将处理后的离散信号转化为连续信号。

离散信号不仅可从离散信号源获得，而且也可从连续信号抽样获得。抽样信号$fs(t)= f(t)·S(t)$。其中f(t)为连续信号（例如三角波），$S(t)$ 是周期为 $Ts$ 的矩形窄脉冲。Ts 又称抽样间隔，$fs=1Ts$ 称抽样频率，$fs(t)$ 为抽样信号波形。$f(t)、S(t)、fs(t)$波形如图1。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714102221812.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_70#pic_center)
 </p><center><sup><code>▲ 图1   连续信号抽样过程</code></sup></center><p></p>
<br>

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020071410244537.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_70#pic_center)
  </p><center><sup><code>▲ 图2 信号的频谱</code></sup></center><p></p>
<br>

对抽样信号进行傅立叶分析可知，抽样信号的频率包括了原连续信号以及无限个经过平移的原信号频率。平移的频率等于抽样频率fs 及其谐波频率 $2fs、3fs$ ······。如图2所示，抽样信号的频谱是原信号频谱周期的延拓，它占有的频带要比原信号频谱宽得多。

2、	正如测得了足够的实验数据以后，我们可以在坐标纸上把一系列数据点连起来，得到一条光滑的曲线一样，抽样信号在一定条件下也可以恢复到原信号。只要用一截止频率等于原信号频谱中最高频率fn 的低通滤波器，滤除高频分量，经滤波后得到的信号包含了原信号频谱的全部内容，故在低通滤波器输出可以得到恢复后的原信号。

3、	由抽样定理可知，当抽样信号频率 $fs>=2fm$ (原信号最高频率)时，$Fs(w)$ 是 $F(w)$ 的无限个振幅按变化的“重复平移”，因此可以通过低通滤波器(截止频率 = $fm$ )从抽样信号 $fs(t)$ 中恢复原信号f(t)。$fmin＝2 fm$ 为最低抽样频率又称 `“奈奎斯特抽样率”` 。当 $fs＜2 fm$ 时，抽样信号的频谱会发生混迭，从发生混迭后的频谱中我们无法用低通滤波器获得原信号频谱的全部内容。在实际使用中，仅包含有限频率的信号是极少的，因此即使 $fs＝2 fm$ ，恢复后的信号失真还是难免的。图3画出了当抽样频率 $fs﹥2 fm$（不混叠时）及 $fs＜2 fm$（混叠时）两种情况下冲激抽样信号的频谱。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714102806979.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_70#pic_center)
  </p><center><sup><code>▲ （a）	高抽样频率时的连续信号、抽样信号及频谱（不混叠）</code></sup></center><p></p>
<br>

 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714102823532.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_25,color_FFF000,t_70#pic_center)
  </p><center><sup><code>▲ （b）	低抽样频率时的连续信号、抽样信号及频谱（混叠）</code></sup></center><p></p>
  </p><center><sup><code>▲ 图3 冲激抽样信号的频谱</code></sup></center><p></p>
<br>

实验中选用 $fs＜2fm、fs＝2fm、fs＞2fm$ 三种抽样频率对连续信号进行抽样，以验证抽样定理——要使信号采样后能不失真地还原，抽样频率 $fs$ 必须大于信号频谱中最高频率的两倍。
<br>

## 三. Multisim 仿真电路

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714103233190.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_30,color_FFF000,t_70#pic_center)
<br>

## 四. 不同频率下的波形
<br>

| 实验条件 | $f_s(t)$的波形  | 恢复信号$f'(t)$的波形|
|:---:| :---:|:---:|
| 抽样频率为 3KHz<br>截止频率为 2KHz |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714103948249.png) |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104013964.png)
| 抽样频率为 6KHz<br>截止频率为 2KHz |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104028884.png) |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104042304.png)
| 抽样频率为 12KHz<br>截止频率为 2KHz | ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104057191.png)|![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104109217.png)
| 抽样频率为 3KHz<br>截止频率为 4KHz |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104120610.png) |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104135188.png)
| 抽样频率为 6KHz<br>截止频率为 4KHz |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104147211.png) |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104156724.png)
| 抽样频率为 12KHz<br>截止频率为 4KHz |![在这里插入图片描述](https://img-blog.csdnimg.cn/20200714104208704.png) |![在这里插入图片描述](https://img-blog.csdnimg.cn/2020071410422066.png)

**由表格可知，不同抽样频率下，抽样频率越高，信号恢复的情况越好。**
<br>

## 五. 实验总结
- 抽样信号产生电路采用 `555定时器` ，产生不同频率的方波
- 方波产生 $\to$ 抽样电路 $\to$ 滤波电路 $\to$ 示波器显示波形
- 原信号采用的是 `三角波` 信号，其频率可以通过电位器调节

- 抽样信号在一定条件下可以恢复出原信号，其条件是 $f_s≥2B_f$，其中 $f_s$ 为抽样频率，$B_f$ 为原信号占有频带宽度。但是实际上要很好地实现信号的恢复，会要求更大一些。

- 若要恢复原信号，则低通滤波器的截止频率 $f_c$ 应该满足： $f_m≤f_c≤f_s-f_m$ ( $f_m$ 是原信号频谱中的最高频率）
<br>

## 六. 问题思考
理论上抽样信号只要通过一截止频率为 $f_c$  ($f_m≤f_c≤f_s-f_m，f_m$ 是原信号频谱中的最高频率）的低通滤波器就能恢复出原信号，那么实际低通滤波器相比较理想低通滤波器来说，在无失真恢复原信号时还需要考虑哪些影响?

答：通过低通滤波器会使不同频率点的信号受到不同程度上的放大或缩小，使得合成的信号失真，且低通滤波器的使用会在原有的信号基础上增加一个时移，或是相移，必然使得在对不同频率点的信号合成时信号失真。

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。