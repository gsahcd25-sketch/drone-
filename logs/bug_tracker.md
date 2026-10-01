# 🐞 NHẬT KÝ SỰ CỐ & THEO DÕI SỬA LỖI (BUG TRACKER)

## Danh sách Bug chi tiết

### [BUG-001] Động cơ bị giật cục khi tăng tốc đột ngột
- **Ngày phát hiện:** 01/10/2026
- **Mô tả:** Khi đẩy ga nhanh từ 10% lên 60%, Motor 2 có hiện tượng khựng lại rồi mới quay.
- **Nguyên nhân dự đoán:** Tần số tín hiệu PWM ra ESC chưa tương thích hoặc thời gian đáp ứng của ESC quá chậm.
- **Các bước sửa lỗi (Action Items):**
  1. [x] Kiểm tra lại xung PWM (chuyển từ 50Hz lên 400Hz).
  2. [ ] Tiến hành Calibrate lại hành trình ga của ESC (ESC Calibration).
- **Kết quả:** Đang theo dõi.
