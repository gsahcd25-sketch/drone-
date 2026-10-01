# 🧪 QUY TRÌNH ĐO ĐẠC HIỆU SUẤT & THỬ NGHIỆM RIG TEST

## 1. Hệ thống giá thử nghiệm (Rig Test Frame)
- Sử dụng khung thử nghiệm 1 trục (1-DOF) để cân chỉnh PID Pitch/Roll.
- Sử dụng khung thử nghiệm 3 trục (3-DOF) dạng khớp cầu để test cân bằng tổng thể.

## 2. Mẫu bảng đo đạc hiệu suất Động cơ & Cánh (Test Bench Log)
*Điều kiện test: Pin 2S đầy điện (8.4V), Nhiệt độ môi trường 28°C.*

| % Ga (Throttle) | Dòng điện (A) | Điện áp (V) | Công suất (W) | Lực kéo (Gram) | Hiệu suất (g/W) | Nhiệt độ Motor (°C) |
| :-------------: | :-----------: | :---------: | :-----------: | :------------: | :-------------: | :-----------------: |
| 25%             | 0.8 A         | 8.2 V       | 6.56 W        | 80 g           | 12.19 g/W       | 32 °C               |
| 50%             | 2.5 A         | 7.9 V       | 19.75 W       | 210 g          | 10.63 g/W       | 40 °C               |
| 75%             | 5.8 A         | 7.5 V       | 43.50 W       | 380 g          | 8.73 g/W        | 52 °C               |
| 100%            | 9.2 A         | 7.1 V       | 65.32 W       | 520 g          | 7.96 g/W        | 68 °C               |

## 3. Quy trình kiểm tra an toàn trước khi cất cánh (Pre-flight Checklist)
- [ ] Kiểm tra điện áp Pin >= 7.6V (Pin 2S).
- [ ] Tín hiệu Microzone kết nối ổn định (FAILSAFE phản hồi đúng).
- [ ] Cánh quạt không bị nứt, ốc khoá động cơ chặt.
- [ ] MPU6050 đã cân bằng Zero-Offset trên mặt phẳng.
