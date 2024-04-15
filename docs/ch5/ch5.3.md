# 前言
==离散系统 z 域分析相关内容==

# 概述
求逆 z 变换的方法有：

1、幂级数展开法

2、部分分数展开法

3、反演积分（留数法）

一般而言，双边序列可分解成因果序列 $f_1(k)$ 和反因果序列 $f_2(k)$ 两部分，即：

$f(k)=f_1(k)+f_2(k)=f(k)\epsilon(k)+f(k)\epsilon(-k-1)$

对应的，其 z 变换也有两个部分

$F(z)=F_1(z)+F_2(z),\alpha <|z|<\beta$

# 一、幂级数展开法
根据 z 变换的定义，因果序列和反因果序列的象函数分别是 $z ^{-1}和 z$ 的幂级数。其系数就是相应的序列值。

><font color=black>例：已知象函数
$$F(z)=\frac{z^2}{(z+1)(z-2)}=\frac{z^2}{z^2-z-2}$$
其收敛域如下，分别求相对应的原序列 $f(k)$。
（1）$|z|>2$ 
（2）$|z|<1$ 
（3）$1<|z|<2$

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503213833424.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =550x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503214015866.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =550x)

# 二、部分分数展开法
$$F(z)=\frac{B(z)}{A(z)}=\frac{b_mz^m+b_{m-1}z^{m-1}+...+b_1z+b_0}{z^n+a_{n-1}z^{n-1}+...+a_1z+a_0},式中n\ge m$$

## 1、$F(z)$ 均为单极点，且不为0
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503214857603.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503214951549.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
## 2、$F(z)$ 有共轭单极点

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503215105605.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)

## 3、$F(z)$ 有重极点
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020050321521472.png#pic_center =550x)
# 总结
逆 z 变换和拉普拉斯逆变换求解方法很相似，但是也要注意区别，常用的 z 变换要熟记。

<br>

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。