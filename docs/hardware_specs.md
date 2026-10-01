# 🔌 SƠ ĐỒ KẾT NỐI PHẦN CỨNG & PINOUT (STM32)

## 1. Bảng phân công chân (Pinout Mapping)

### MPU6050 (IMU) -> STM32 (I2C1)
- VCC  -> 3.3V
- GND  -> GND
- SCL  -> PB6 (I2C1_SCL)
- SDA  -> PB7 (I2C1_SDA)
- INT  -> PA0 (External Interrupt)

### Tay điều khiển Microzone Receiver (PPM / S.BUS) -> STM32
- Signal -> PA1 (TIM2_CH1 - Input Capture)
- VCC    -> 5V
- GND    -> GND

### ESC / Motor -> STM32 (PWM Timers)
- Motor 1 (Trước-Phải) -> PA8 (TIM1_CH1)
- Motor 2 (Sau-Phải)   -> PA9 (TIM1_CH2)
- Motor 3 (Sau-Trái)   -> PA10 (TIM1_CH3)
- Motor 4 (Trước-Trái)  -> PA11 (TIM1_CH4)

### GPS Module -> STM32 (USART2)
- TX -> PA3 (USART2_RX)
- RX -> PA2 (USART2_TX)

---

## 2. Lưu ý cấp nguồn & Chống nhiễu
- Mạch STM32 và MPU6050 được cấp nguồn qua BEC 5V/3.3V cách ly.
- Cụm la bàn số / GPS gắn trên cọc nâng cao tối thiểu 5cm so với mặt PDB/ESC.
