>Author：AXYZdong<br>
>自动化专业 工科男<br>
>有一点思考，有一点想法，有一点理性！<br>
>CSDN@AXYZdong，CSDN首发，更多精彩内容请前往 [AXYZdong的博客](https://blog.csdn.net/qq_43328313)

@[TOC]
# 题目
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200417214620128.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
# 三、
解：微分方程两边取拉氏变换，可得：

$$(s^2+5s+6)Y(s)-sy(0_{-})-y'(0_{-})-5y(0_{-})=(2s+10)F(s)$$
整理：

$$Y(s)=\frac{s+6}{s^2+5s+6}+\frac{2s+10}{s^2+5s+6}\cdot F(s)$$

故：$$Y_X(s)=\frac{s+6}{s^2+5s+6}=\frac{4}{s+2}+\frac{-3}{s+3}\\[3ex]
Y_f(s)=\frac{2s+10}{s^2+5s+6}\cdot F(s)=\frac{2s+10}{s^2+5s+6}\cdot \frac{1}{s+1}=\frac{-6}{s+2}+\frac{2}{s+3}+\frac{4}{s+1}$$

零状态响应：$$y_f(t)=(2e^{-3t}+4e^{-t}-6e^{-2t})\epsilon(t)$$

零输入响应：$$y_X(t)=( 4e^{-2t}-3e^{-3t})\epsilon(t)$$

全响应：$$y(t)=(-e^{-3t}+4e^{-t}-2e^{-2t})\epsilon(t)$$

# 四、
（1）$$F(s)=\frac{s-2}{s(s-1)^2}$$
解：令：$$F(s)=\frac{k_{11}}{(s-1)^2}+\frac{k_{12}}{(s-1) }+\frac{k_2}{s}$$

令：$$F_1(s)=(s-1)^2F(s)=\frac{s-2}{s}$$

$k_{11}=F_1(s)|_{s=1}=-1,k_{12}=\frac{d}{ds}F_1(s)=\frac{s-(s-2)}{s^2}|_{s=1}=2,k_2=sF(s)|_{s=0}=-2$

故：$$F(s)=\frac{-1}{(s-1)^2}+\frac{2}{(s-1) }+\frac{-2}{s}$$

$F(s)$ 拉式反变换为 $$f(t)=(-te^t+2e^t-2)\epsilon(t)$$





\
\
（2）$$F(s)=\frac{2s+1}{s(s+2)(s+3)}$$
解：令：$$F(s)=\frac{k_1}{s}+\frac{k_2}{s+2}+\frac{k_3}{s+3}$$
$k_1=sF(s)|_{s=0}=1/6,k_2=(s+2)F(s)|_{s=-2}=3/2,k_3=(s+3F(s)|_{s=-3}=-5/3$

故：$$F(s)=\frac{ 1}{6s}+\frac{3}{2(s+2)}+\frac{-5}{3(s+3)}$$

$F(s)$ 拉式反变换为 $$f(t)=( \frac{ 1}{6}+\frac{3}{2}e^{-2t}-\frac{5}{3}e^{-3t})\epsilon(t)$$

# 五、
解：设左边加法器输出为：$X(s)$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200417224445871.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center)
则：$$X(s)=F(s)-5s^{-1}X(s)-4s^{-2}X(s)$$




$$Y(s)=X(s)+4s^{-2}X(s)$$

可得：$$X(s)=\frac{s^2}{s^2+5s+4}F(s)$$
$$Y(s)=\frac{s^2+4}{s^2+5s+4}F(s),即：({s^2+5s+4})Y(s)=(s^2+4)F(s)$$

（1）微分方程：$y''(t)+5y'(t)+4y(t)=f''(t)+4f(t)$

（2）系统函数：$$H(s)=\frac{s^2+4}{s^2+5s+4}$$

（3）$$H(s)=\frac{s^2+4}{s^2+5s+4}=1+\frac{5}{3(s+1)}-\frac{20}{3(s+4)}$$
$$h(t)=\mathcal{L^{-1}}[H(s)]=\delta(t)+(\frac{5}{3}e^{-t}-\frac{20}{3}e^{-4t})\epsilon(t)$$
# 总结
 <font color=red> 学习通考试60分钟没能做得完，还是练得少了，拿到题目不知如何下手，博客上重新写一遍，有点感觉了，$practise$ $makes$ $perfect$ ！！！不要眼高手低，多练，多练，多练！</font>
<br>

「你可能还想看」系列文章：
[【信号与系统】笔记合集，你确定不收藏吗？我已经收藏了](https://axyzdong.blog.csdn.net/article/details/105909575)
\
\
 <strong> <font color=red><strong>先赞后看，养成习惯！！！^ _ ^ <3 <3 <3</font>
 码字不易，大家的支持就是我坚持下去的动力。点赞后不要忘了<font color=red>关注</font>我哦！
