# OLEDDriver_STM32_HAL
基于HAL库使用硬件I2C+DMA的SSD1306的128*64OLED屏幕驱动程序。  
A 128*64OLED screen driver for SSD1306 based on the HAL library using hardware I2C+DMA  
  
## 使用时注意  
* 1.工程中外设相关的配置可能与CubeMAX中的文件存在差异如果重新生成代码时注意甄别  
* 2.使用时只需修改OLED.h文件中的宏定义的值即可，其中需要修改的是  
       #define IIC  
       #define IIC_Addr  
* 3.程序中提供了阻塞模式、中断模式、DMA，通过修改宏定义  
       #define IIC_Mode_Blocking即可  
       此行下面注释中的对应内容即为宏定义的内容  
* 4.字模数据中含有中文需要在  目标选项->C/C++选项卡 中的 “Misc Control”一栏中加入“--no-multibyte-chars”，此在OLED.h中也有提及  
* 5.在使用非阻塞传输时，需要编辑的中断回调函数在 OLED.h文件中的末尾注释中提及直接复制即可  
  
**本例程基于STM32H743VIT6编写  
