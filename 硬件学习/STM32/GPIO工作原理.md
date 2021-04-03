GPIO工作原理

## 输入模式

1. 输入浮空 GPIO_Mode_IN_FLOATING不接高电平也不接低电平一般做ADC输入用减少上下拉电阻对结果的影响

   ![img](https://img-blog.csdn.net/2018042410442526?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

2. 输入上拉 GPIO_Mode_IPU

   ![img](https://img-blog.csdn.net/20180424104950824?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

3. 输入下拉

   ![img](https://img-blog.csdn.net/20180424105050410?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

4. 模拟输入 模拟通道

   ![img](https://img-blog.csdn.net/20180424105222199?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

##  输出模式

1. 开漏输出（只能强低电平，高电平需要外部电阻拉高，适合电流驱动）

   ![img](https://img-blog.csdn.net/20180424105447668?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

2. 开漏复用输出

![img](https://img-blog.csdn.net/20180424105941821?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

3. 推挽输出（输出强高低电平，数字文件）

   ![img](https://img-blog.csdn.net/20180424110504740?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

4. 推挽复用输出

![img](https://img-blog.csdn.net/20180424110513557?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JhaWR1XzM3MzY2MDU1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

## GPIO寄存器

端口模式MODER一组IO十六个（00输如01通用输出10复用功能11模拟功能）

输出类型OTYPER（0输出推挽1输出开漏）
输出速度OSPEEDR（00 2M 01 25M 10 50M 11 100M/80M）

上拉下拉PUPDR//四个32为配置寄存器(00无01上拉10下拉11保留)

输入数据IDR（读）

输出数据ODR//两个数据寄存器（rw ）

置位/复位BSRR（w低16位（写0不操作 写1置1）高16位写0不操作写1复位0）

配置锁存LCKR

两个复用AFRL\AFRH()

## 所有IO可以做外部中断输入

# 位操作

支持位带操作的地址为0x20000000-0x200FFFFF(SARM)和0x40000000-0x400FFFFF(片上外设)

别名区地址 add=0x22000000+(A-0x20000000)*32+n *4(A字节地址，n位序号)

# extern变量声明 关联别的函数或者变量

# typydef 定义变量的别名

Strurt 结构体名字｛

成员变量；

···

｝变量名列表；

#　时钟系统

## 时钟

+ LSIRC 低速内部RC时钟，精度低适合看门狗等要求精度不高的使用32KHz
+ HSIRC高速内部RC时钟16MHZ
+ LSEOSC低速外部晶振时钟32.768Khz
+ HSEOSE高速外部晶振时钟4~26MHZ
+ PLL锁向倍频输出













