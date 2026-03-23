# OLEDDriver_STM32_HAL
## 基本描述
**此OLED驱动程序基于[江协科技](https://jiangxiekeji.com/tutorial/oled.html)OLED驱动编写**

基于HAL库使用硬件I2C+DMA的SSD1306的128*64OLED屏幕驱动程序。  
A 128*64OLED screen driver for SSD1306 based on the HAL library using hardware I2C+DMA  

## 使用时注意  
* 1.工程中外设相关的配置可能与CubeMAX中的文件存在差异如果重新生成代码时注意甄别  
* 2.使用时只需修改OLED.h文件中的宏定义的值即可，其中需要修改的是  
       `#define IIC`  
       `#define IIC_Addr`  
* 3.程序中提供了阻塞模式、中断模式、DMA，通过修改/设置宏定义  
       `#define IIC_Mode_Blocking`即可  
       此行下面注释中的对应内容即为宏定义的内容  
* 4.字模数据中含有中文需要在  目标选项->C/C++选项卡 中的 “`Misc Control`”一栏中加入“`--no-multibyte-chars`”，此在`OLED.h`中也有提及  
* 5.在使用非阻塞传输时，中断服务函数回调函数内容可以直接在回调函数中调用`OLED.h`文件中的`OLED_IIC_ISR()`函数 
* 6.在使用中文时要注意**字符编码**的问题，如果遇到显示中文时显示`?`则将`OLED_Data.c`文件中字库中的汉字删掉重新输入即可（本项目实例使用的编码是`GB2312`)

**本例程所用芯片：STM32H743VIT6  