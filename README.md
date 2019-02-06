# MPU-6050 test
明らかに3.3V接続の方が安定する。5Vだとread errorが時々起きる。

```
RasPi               MPU-6050
3.3V     VCC        VCC
GPIO 2   SDA        GND
GPIO 3   SCL        SCL
---                 SDA
(-)      GND        ---
                    ---
                    ---
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
