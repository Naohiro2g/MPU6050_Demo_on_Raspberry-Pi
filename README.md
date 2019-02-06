# MPU-6050 (GY-521) test

 - 明らかに3.3V電源供給の方が安定している。5Vだとread errorが時々起きる。
モジュール上の3.3Vレギュレーターが5Vから3.3Vを作っており、モジュール内は3.3V動作のはずだが。
 - SCL、SDAはモジュール内で4.7KΩで3.3Vにプルアップされている。
ラズパイ基板上でも1.8KΩでプルアップされているので、合成抵抗は1.3KΩである。
 - AD0はモジュール内で4.7KΩでプルダウンされていて、I2Cアドレスは0x68である。
プルアップすると0x69として使える。

```
sudo i2cdetect -y 1
```

 - 実験に使ったモジュールは、抵抗の実装が間違っているようで、
プルダウン抵抗1KΩ、電源インジケーターLEDの電流制限抵抗4.7KΩと入れ替わっている。



```
RasPi               MPU-6050
3.3V     VCC        VCC
GPIO 2   SDA        GND
GPIO 3   SCL        SCL
---                 SDA
(-)      GND        ---
                    ---
                    AD0
                    ---
```

# MPU6050_Demo_on_Raspberry-Pi

Simple MPU6050 demo with Raspberry Pi 2 
Simple MPU6050 Demo on Raspberry pi 2 using ITG-MPU breakout board (MPU6050)
This breakout board from aliexpress for $1.50. 40pin old IDE cable used to connect to raspi2
no interrupt, +vcc of the board is connected to +5v of raspi2
only sda, scl connected to raspi2.
MPU data accessed regularly every 10ms (.01sec), sleep time reduced to allow data processing and draw.
By Opata Padmasiri  
codes for reading data from MPU6050 and complementary filter taken from the following blog: 
http://blog.bitify.co.uk/2013/11/reading-data-from-mpu-6050-on-raspberry.html
