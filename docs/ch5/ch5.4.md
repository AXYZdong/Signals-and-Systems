# 前言
单边 z 变换将系统的初始条件自然地包含于其代数方程中，可求得零输入、零状态响应和全响应。
 
# 一、差分方程的变换解
 $$\sum_{i=0}^{n}a_{n-i}y(k-i)=\sum_{j=0}^{m}b_{m-j}f(k-j)$$

设 $f(k)$ 在 $k=0$ 时接入，系统初始状态为 $y(-1),y(-2),...,y(-n)$.

取单边 z 变换得：

$$\sum_{i=0}^{n}a_{n-i}[z^{-i}Y(z)+\sum_{k=0}^{i-1}y(k-i)z^{-i}]=\sum_{j=0}^{m}b_{m-j}[z^{-j}F(z)]$$


$$[\sum_{i=0}^{n}a_{n-i}z^{-i}]Y(z)+\sum_{i=0}^{n}a_{n-i}[\sum_{k=0}^{i-1}y(k-i)z^{-i}]=(\sum_{j=0}^{m}b_{m-j}z^{-j})F(z)]$$

$$Y(z)=\frac{M(z)}{A(z)}+\frac{B(z)}{A(z)}F(z)=Y_x(z)+Y_f(z)$$

><font color=blue size=3>令$$H(z)=\frac{Y_f(z)}{F(z)}=\frac{B(z)}{A(z)}$$
>称为系统函数

><font color=red>$h(k)  \longleftrightarrow H(z)$

例1：若某系统的差分方程为

$$y(k)-y(k-1)-2y(k-2)=f(k)+2f(k-2)$$

已知：$y(-1)=2,y(-2)=-1/2,f(k)=\epsilon(k)$。

求系统的 $y_x(k)、y_f(k)、y(k)$

><font color=black>解：方程取单边 z 变换
>$$Y(z)-[z^{-1}Y(z)+y(-1)]-2[z^{-2}Y(z)+y(-2)+z^{-1}y(-1)]=F(z)+2z^{-2}F(z)$$
$$Y(z)=\frac{(1+2z^{-1})y(-1)+2y(-2)}{1-z^{-1}-2z^{-2}}+\frac{1+2z^{-2}}{1-z^{-1}-2z^{-2}}F(z)=\frac{z^2+4z}{z^2-z-2}+\frac{z^2+2}{z^2-z-2}\frac{z}{z-1}$$
$$Y_x(z)=\frac{z^2+4z}{z^2-z-2}=\frac{2z}{z-2}+\frac{-z}{z+1}$$
$$\longrightarrow y_x(k)=[2(2)^k-(-1)^k]\epsilon(k)$$
$$Y_y(z)=\frac{2z}{z-2}+\frac12\frac{ z}{z+1}-\frac32\frac{ z}{z-1}$$
$$\longrightarrow y_f(k)=[2^{k+1}+\frac12(-1)^k-\frac32]\epsilon(k)$$
$y(k)=y_x(k)+y_f(k)$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503234324263.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
# 二、系统的 z 域框图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503234554951.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
例：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503235042397.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503235059544.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503235108297.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
# 三、利用 z 变换求卷积和

例：求 $2^k\epsilon(k)*[2^{-k}\epsilon(k)]$

><font color=black>解：$$2^k\epsilon(k)\longleftrightarrow \frac{z}{z-0.5},|z|>0.5$$
>$$2^{-k}\epsilon(k) \longleftrightarrow \frac{z^{-1}}{z^{-1}-0.5}=\frac{-2}{z-2},|z|<2$$
>原式的象函数为：
>$$\frac{-2z}{(z-0.5)(z-2)}=\frac{\frac43z}{z-0.5}+\frac{-\frac43z}{z-2}$$
$$\longrightarrow 原式= \frac43(0.5)^k\epsilon(k)+\frac43(2)^k\epsilon(-k-1)$$


# 总结
最后一遍笔记，收官，杀青啦！！！

联系之前的 **频域分析** 和 **复频域分析**，**z 域分析** 与之相似，但是也要注意区别。
<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。