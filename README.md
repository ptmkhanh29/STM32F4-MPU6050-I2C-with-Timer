# STM32F4-MPU6050-I2C-with-Timer
- Sensor GY-521 6DOF IMU MPU6050 interface STM32F411 using I2C. 
- Create Timer2 generate delay 1ms to update data roll, pitch, yaw or titl angle for Balance Robot.

# Debug data KeilC

![Screenshot (295)](https://user-images.githubusercontent.com/113729333/219967594-0076f74d-711c-419a-97e6-1ced3975cf22.png)

# Testing MPU6050 

![z4122522368779_7e4f63293683361a80f66142073afdac](https://user-images.githubusercontent.com/113729333/219967764-85f5f492-b49f-4ec4-8e8f-19bf16dc7312.jpg)

# Explain code 
- STM32F411 using I2C1 interface with MPU6050, config bellow:

![i2c](https://user-images.githubusercontent.com/113729333/219968001-8b9c3e87-ea48-4058-933d-dbaa4eef7983.png)

- Config Timer2 generate 1ms update data from Mpu6050:

![timer2](https://user-images.githubusercontent.com/113729333/219968031-4e4bf85d-91f9-480f-8589-fa9388dee7b7.png)

To calculate the timer interrupt time for Timer 1 on the STM32F4 microcontroller to generate a 1ms timer interrupt, you can use the following formula:

`Timer Interrupt Time = (Timer Prescaler + 1) * (Timer Period + 1) / Timer Clock Frequency`

With:
1. > Timer Prescaler is the value of the timer prescaler register (TIMx_PSC)
2. > Timer Period is the value of the timer auto-reload register (TIMx_ARR)
3. > Timer Clock Frequency is the frequency of the timer clock (TIMxCLK)
Where: Prescaler = 99, Timer Period = 9999, Timer Clock Frequency = 100.000 Hz
Thus: Time = (99+1)*(9999+1)/100000 = 1ms -> interrupt with 1ms
