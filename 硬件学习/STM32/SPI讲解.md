# SPI讲解

## SPI接口原理

+ 串行、高速、全双工、同步

  ![image-20210327221557830](C:\Users\Sherlock\AppData\Roaming\Typora\typora-user-images\image-20210327221557830.png)

+ MISO主设备数据输入，从机输出
+ MOSI主设备数据输出，从设备输入
+ SCLK时钟信号，主设备产生
+ CS从设备片选，主设备控制 
+ CPOL为1时候闲置为高电平
+ CPHA为1时第二个边沿采集
+ 