# 🚁 DỰ ÁN NGHIÊN CỨU & PHÁT TRIỂN DRONE TRINH SÁT & RTH (RETURN TO HOME)

> **Mục tiêu dự án:** Tự thiết kế, lập trình và tối ưu mẫu Drone mini 3-inch phục vụ quay phim, trinh sát cứu hộ cứu nạn, tích hợp tính năng tự động quay về vị trí xuất phát (Return To Home - RTH).
> 
> **Thời gian thực hiện:** 01/10/2026 – 01/01/2027 (3 tháng)  
> **Người thực hiện:** Độc lập (1 thành viên)  
> **Ngân sách tối đa:** 10,000,000 VNĐ

---

## 📌 1. TỔNG QUAN HỆ THỐNG & PHẦN CỨNG (HARDWARE ARCHITECTURE)

### 1.1. Danh mục linh kiện & Trạng thái vật tư
| STT | Tên thiết bị / Linh kiện | Thông số / Model | Trạng thái | Ghi chú / Ngân sách |
| :-: | :----------------------- | :--------------- | :--------: | :------------------ |
| 1 | Mạch điều khiển trung tâm (MCU) | STM32 (F4/F7) | 🟢 Có sẵn | Xử lý thuật toán chính |
| 2 | Cảm biến gia tốc & Góc quay | MPU6050 (IMU) | 🟢 Có sẵn | Giao tiếp I2C/SPI |
| 3 | Mạch la bàn số (Magnetometer) | HMC5883L / QMC5883L | 🟢 Có sẵn | Xác định hướng địa lý |
| 4 | Camera trinh sát & Quay phim | Insta360 GO 3S | 🟢 Có sẵn | Quay phim/Truyền ảnh |
| 5 | Nguồn cấp (Battery) | Pin LiPo 2S | 🟢 Có sẵn | Tối ưu khối lượng |
| 6 | Khung Drone (Frame) | Khung 3-inch (Carbon) | 🟢 Có sẵn | Thiết kế nhỏ gọn |
| 7 | Động cơ & ESC | Brushless Motors + ESC | 🟢 Có sẵn | Đã test điều khiển |
| 8 | Định vị toàn cầu (GPS) | GPS Module (M8N/M9N) | 🔴 Còn thiếu | Cần mua (Phục vụ RTH) |
| 9 | Cánh quạt (Propellers) | Cánh 3-inch (3016/3020) | 🔴 Còn thiếu | Cần mua thử nghiệm |
| 10 | Cảm biến độ cao (Barometer/LiDAR)| BMP280 / VL53L1X | 🔴 Còn thiếu | Cần mua để giữ độ cao |

---

## 📅 2. KẾ HOẠCH & TIẾN ĐỘ 5 GIAI ĐOẠN (ROADMAP)
