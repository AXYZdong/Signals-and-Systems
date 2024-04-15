><font color=black>使用的软件：Matlab
>version：R2018a

# 题目
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200502235439308.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =600x)

# 一、$(2-e^{-2t})u(t)$ 波形

```c
clear                   %清除工作空间的所有变量 
close all               %关闭所有的Figure窗口 
clc                     %清除命令窗口的内容，对工作环境中的全部变量无任何影响
t=-10:0.01:10;          %定义时间点
ut=(t>=0);              %产生单位阶跃信号
ft=(2-exp(-2*t)).*ut;   %计算这些点的函数值
plot(t,ft);             %画图命令，用直线段连接函数值表示曲线
grid on;                %在图上显示网格

```

运行结果：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200502235703557.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =600x)

# 二、$(1+\cos \pi t)[u(t)-u(t-2)]$ 波形

```c
clear                   %清除工作空间的所有变量 
close all               %关闭所有的Figure窗口 
clc                     %清除命令窗口的内容，对工作环境中的全部变量无任何影响
t=-4:0.01:4;            %定义时间点
ut1 =(t>=0);            %产生单位阶跃信号
ut2 =(t>=2);            %单位阶跃信号向右平移2个单位
ft=(1+cos(pi*t)).*(ut1-ut2);  %计算这些点的函数值
plot(t,ft);             %画图命令，用直线段连接函数值表示曲线
grid on;                %在图上显示网格

```
运行结果：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200502235754276.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =600x)

# 三、$f(t)=(2-e^{-2t})u(t)$ ，$f(2t)$ 和 $f(2-t)$波形
## 1、$f(2t)$ 波形
同时画出 $f(t)$ 波形，以进行对比

```c
clear                       %清除工作空间的所有变量 
close all                   %关闭所有的Figure窗口 
clc                         %清除命令窗口的内容，对工作环境中的全部变量无任何影响
t=-5:0.01:5;                %定义时间点
ut=(t>=0);                  %产生单位阶跃信号
ft=(2-exp(-2*t)).*ut;       %计算这些点的函数值
f2t=(2-exp(-2*(2*t))).*ut;  %计算这些点的函数值
plot(t,ft,'-r',t,f2t,'-b'); %画图命令，用直线段连接函数值表示曲线,f(t)和f(2t)用两种不同颜色曲线加以区别
text(-0.3,1.8,'f(2t)')      %设置标号f(2t)
text(1,1.8,'f(t)')          %设置标号f(t)
grid on;                    %在图上显示网格
```
运行结果：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200502235950362.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =600x)
## 1、$f(2-t)$ 波形
同时画出 $f(t)$ 波形，以进行对比

```c
clear                       %清除工作空间的所有变量 
close all                   %关闭所有的Figure窗口 
clc                         %清除命令窗口的内容，对工作环境中的全部变量无任何影响
t=-5:0.01:5;                %定义时间点
ut=(t>=0);                  %产生单位阶跃信号
ut1=((2-t)>=0);             %新信号的阶跃部分
ft=(2-exp(-2*t)).*ut;       %计算这些点的函数值
f2t=(2-exp(-2*(2-t))).*ut1; %计算这些点的函数值
plot(t,ft,'-r',t,f2t,'-b'); %画图命令，用直线段连接函数值表示曲线,f(t)和f(2-t)用两种不同颜色曲线加以区别
text(0,1.6,'f(t)')          %设置标号f(t)
text(1.6,1.6,'f(2-t)')      %设置标号f(2-t)
grid on;                    %在图上显示网格
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200503000056288.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMzI4MzEz,size_16,color_FFFFFF,t_70#pic_center =600x)
# 总结
**创建.m文件，在编辑区输入代码， 时间点的设置， 单位阶跃信号的产生， 波形平移、尺度的变换 ，不同波形设置不同的颜色 ，给不同的波形标号。** 这些都是要思考和解决的。
Matlab在电脑里装了好久，一直没用，昨天用了一下，感觉还是有许多需要学习的。有对Matlab感兴趣的小伙伴，欢迎一起交流学习啊！

>本文作者：AXYZdong <br>
>本文地址：https://axyzdong.github.io/Signals-and-Systems<br>
>仓库地址：https://github.com/AXYZdong/Signals-and-Systems<br>
>版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

