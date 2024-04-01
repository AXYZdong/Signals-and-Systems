>Author：AXYZdong
>自动化专业 工科男
>有一点思考，有一点想法，有一点理性！
>CSDN@AXYZdong

@[TOC]
# 一、微分方程变换解
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200418153632979.png#pic_center)
><strong><font color=black>解：微分方程两边取拉氏变换，可得：
$$(s^2+5s+6)Y(s)-sy(0_{-})-y'(0_{-})-5y(0_{-})=(2s+10)F(s)$$
整理：
$$Y(s)=\frac{s+6}{s^2+5s+6}+\frac{2s+10}{s^2+5s+6}\cdot F(s)$$
故：$$Y_X(s)=\frac{s+6}{s^2+5s+6}=\frac{4}{s+2}+\frac{-3}{s+3},Y_f(s)=\frac{2s+10}
{s^2+5s+6}=\frac{-6}{s+2}+\frac{2}{s+3}+\frac{4}{s+1}$$
零状态响应：$$y_f(t)=(2e^{-3t}+4e^{-t}-6e^{-2t})\epsilon(t)$$
零输入响应：$$y_X(t)=( 4e^{-2t}-3e^{-3t})\epsilon(t)$$
全响应：$$y(t)=(-e^{-3t}+4e^{-t}-2e^{-2t})\epsilon(t)$$

# 二、系统函数
**系统函数定义为：**
$$H(s)=\frac{Y_f(s)}{F(s)}=\frac{B(s)}{A(s)}$$

*它只与系统的结构、元件的参数有关，而与激励、初始状态无关。*

$$y_f(t)=h(t)*f(t) \longrightarrow Y_f(s)=\mathcal{L}[h(t)]F(s)$$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200418154635957.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
# 三、系统的s域框图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200418155006355.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
**例：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200418155328304.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
><strong><font color=black>解：设左边加法器输出为：$X(s)$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200417224445871.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =500x)
则：$$X(s)=F(s)-5s^{-1}X(s)-4s^{-2}X(s)$$
$$Y(s)=X(s)+4s^{-2}X(s)$$
可得：$$X(s)=\frac{s^2}{s^2+5s+4}F(s)$$
$$Y(s)=\frac{s^2+4}{s^2+5s+4}F(s),即：({s^2+5s+4})Y(s)=(s^2+4)F(s)$$
（1）微分方程：$y''(t)+5y'(t)+4y(t)=f''(t)+4f(t)$
（2）系统函数：$$H(s)=\frac{s^2+4}{s^2+5s+4}$$
（3）$$H(s)=\frac{s^2+4}{s^2+5s+4}=1+\frac{5}{3(s+1)}-\frac{20}{3(s+4)}$$
$$h(t)=\mathcal{L^{-1}}[H(s)]=\delta(t)+(\frac{5}{3}e^{-t}-\frac{20}{3}e^{-4t})\epsilon(t)$$

 <br>

「你可能还想看」系列文章：
[【信号与系统】笔记合集，你确定不收藏吗？我已经收藏了](https://axyzdong.blog.csdn.net/article/details/105909575)
 \
 <strong> <font color=red><strong>看完就赞，养成习惯！！！^ _ ^ <3 <3 <3</font>
 码字不易，大家的支持就是我坚持下去的动力。点赞后不要忘了<font color=red>关注</font>我哦！

