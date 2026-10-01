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
### 🎯 Giai đoạn 1: Bổ sung phần cứng & Dựng khung chuẩn (01/10/2026 – 15/10/2026)
- [x] Test kết nối cơ bản: STM32 + MPU6050 + ESC + Motor.
- [ ] Mua bổ sung: GPS, Cánh quạt 3-inch, Cảm biến con lắc/độ cao.
- [ ] Hàn nối, đi dây gọn gàng, cách ly chống nhiễu từ tính cho La bàn số và GPS.
- [ ] Đo đạc tổng trọng lượng (AUW) và tính toán lực đẩy (Thrust-to-Weight ratio).

### 🎯 Giai đoạn 2: Lập trình phần mềm cơ bản (16/10/2026 – 31/10/2026)
- [x] Lập trình đọc MPU6050 & xuất xung PWM/DShot ra ESC để thay đổi tốc độ motor theo góc nghiêng.
- [ ] Lập trình bộ lọc dữ liệu cảm biến (Complementary Filter hoặc Kalman Filter).
- [ ] Viết vòng băm PID cho 3 trục (Roll, Pitch, Yaw) để giữ cân bằng.
- [ ] Giải mã dữ liệu GPS (NMEA Protocol) và dữ liệu La bàn số qua STM32.

### 🎯 Giai đoạn 3: Bay thử nghiệm & Hệ thống đo đạc hiệu suất (01/11/2026 – 15/11/2026)
- [ ] **Xây dựng Rig test (Khung thử nghiệm):** Dựng giá treo cố định 1 trục / 3 trục để test PID an toàn.
- [ ] **Đo đạc hiệu suất (Test Bench):** 
  - Đo lực kéo (Thrust), dòng điện tiêu thụ (Amperes), nhiệt độ motor ở các mức ga (25%, 50%, 75%, 100%).
  - Chọn lọc quy trình chuẩn hóa: Áp dụng các quy trình kiểm thử phổ thông trước (Pre-flight checklist), sau đó tinh chỉnh thành quy trình tối ưu riêng.
- [ ] Bay cất cánh thực tế trong nhà/không gian hẹp ở chế độ Acro/Angle.

### 🎯 Giai đoạn 4: Thử nghiệm & Phát triển thuật toán Return To Home (RTH) (16/11/2026 – 15/12/2026)
- [ ] Lập trình thuật toán lưu tọa độ điểm cất cánh (Home Point).
- [ ] Viết logic tính toán góc quay (Heading) và khoảng cách từ vị trí hiện tại về Home Point bằng dữ liệu GPS + Magnetometer.
- [ ] Thử nghiệm các kịch bản RTH ban đầu:
  1. Tự động tăng độ cao an toàn (Safe Altitude).
  2. Quay đầu về hướng Home Point.
  3. Di chuyển về tọa độ Home Point.
  4. Hạ cánh tự động hoặc trả quyền điều khiển cho phi công.

### 🎯 Giai đoạn 5: Tinh gọn phần cứng & Tối ưu hóa phần mềm (16/12/2026 – 01/01/2027)
- [ ] Tối ưu hóa trọng lượng, tích hợp gọn gàng Camera Insta360 GO 3S phục vụ trinh sát.
- [ ] Tinh chỉnh tham số PID & cấu trúc code trên STM32 để tiết kiệm năng lượng, tăng thời gian bay.
- [ ] Đóng gói tài liệu báo cáo kỹ thuật toàn bộ dự án.

---

## 🛠️ 3. BÁO CÁO LỖI & PHƯƠNG PHÁP XỬ LÝ (BUG TRACKING)

| Mã lỗi | Mô tả sự cố / Hiện tượng | Nguyên nhân dự đoán | Phương pháp khắc phục | Trạng thái |
| :---: | :----------------------- | :------------------ | :-------------------- | :---------: |
| #ERR01 | Động cơ phản ứng chậm khi nghiêng khung | Chu kỳ đọc MPU6050 hoặc tần số vòng lặp PID quá thấp | Chuyển sang đọc MPU6050 qua ngắt (Interrupt) & tăng tần số PWM | 🟡 Đang xử lý |
| #ERR02 | Nhiễu góc quay khi chạy động cơ | Nhiễu từ tính do dòng điện lớn từ ESC làm lệch La bàn số | Dời La bàn số lên vị trí cao, cách xa dây nguồn chính | 🔴 Chờ test |
| #ERR03 | Trôi tọa độ GPS (GPS Drift) | Tín hiệu vệ tinh yếu khi bay thấp | Cấu hình lọc HDOP < 2.0 mới cho phép lưu Home Point | 🔴 Chờ test |
---

## 🤖 4. CHIẾN LƯỢC TÍCH HỢP AI & PHÂN TÁCH VAI TRÒ (HUMAN vs AI)

### 4.1. Vai trò của AI trong dự án
- **Hỗ trợ viết & Review code:** AI đóng vai trò là "Trợ lý lập trình", gợi ý cấu trúc toán học (Kalman Filter, công thức Haversine tính khoảng cách GPS), giải thích register của STM32, phát hiện lỗi cú pháp.
- **Phân tích dữ liệu Log:** Tải dữ liệu sensor/PID thu được từ quá trình test bench lên AI để nhờ phân tích đồ thị dao động và gợi ý tham số PID.
- **Tối ưu quy trình:** AI gợi ý danh mục kiểm tra an toàn (Checklist) tiêu chuẩn quốc tế.

### 4.2. Giới hạn tự làm (Nếu KHÔNG có AI)
- **Khả năng tự chủ:** Vẫn hoàn thành được phần cứng, cân bằng PID cơ bản và điều khiển bằng tay.
- **Điểm nghẽn khi thiếu AI:** Tốn nhiều thời gian tự đọc Datasheet chi tiết của STM32/MPU6050, mất thời gian tự giải hệ phương trình vi phân / ma trận toán học cho bộ lọc Kalman và công thức tính tọa độ RTH.

### 4.3. Nguyên tắc phân tách vai trò (Tách biệt Con người và AI)
1. **Con người nắm quyền quyết định tối cao (Human-in-the-loop):** AI chỉ gợi ý giải pháp, con người là người duyệt code, kiểm tra tính an toàn trước khi nạp vào STM32 và cắm pin.
2. **AI không làm thay phần thực hành:** AI không thể hàn mạch, không thể đo đạc lực kéo trên Rig test hay cảm nhận độ rung thực tế của Frame.
3. **Kiểm tra chéo (Cross-verification):** Mọi đoạn code thuật toán do AI sinh ra (nhất là code can thiệp trực tiếp vào ESC/Motor) đều phải qua kiểm thử từng phần trên bàn test trước khi cho cất cánh.

---

## 🎓 5. KẾT QUẢ ĐẠT ĐƯỢC & BÀI HỌC THU HOẠCH (LEARNING OUTCOMES)

### 💡 Khả năng tự chủ phát triển
- Tự chủ 100% quy trình thiết kế, tích hợp hệ thống nhúng điều khiển bay từ mức mạch holic (Bare-metal/HAL) đến ứng dụng thực tế.

### 📚 Kiến thức & Kỹ năng thu được
1. **Lập trình hệ thống nhúng nâng cao:** Làm chủ vi điều khiển STM32, giao tiếp I2C, SPI, UART, PWM, DShot.
2. **Xử lý tín hiệu & Thuật toán điều khiển:** Hiểu sâu bộ lọc dữ liệu (Kalman/Complementary), thuật toán điều khiển phản hồi vòng kín PID.
3. **Hệ thống định vị & RTH:** Hiểu cơ chế hoạt động của GPS, La bàn số, công thức lượng giác trên mặt cầu (Haversine Formula) để điều hướng.
4. **Kỹ năng thử nghiệm & Tối ưu hóa:** Xây dựng hệ thống test bench đo đạc hiệu suất động cơ, quy trình quản lý dự án kỹ thuật chuẩn mực.
