# Guitar Tuner

Ứng dụng web giúp người dùng chỉnh dây đàn guitar thông qua microphone. Sử dụng kỹ thuật phân tích tín hiệu (correlation) để phát hiện nốt nhạc và so sánh với các tần số chuẩn của các dây đàn.

## 🎯 Tính năng chính

- Phát hiện nốt nhạc đang được chơi qua microphone.
- Hiển thị tên nốt, tần số và độ lệch so với tần số chuẩn.
- Chọn dây đàn cần chỉnh từ danh sách.
- Tự động báo "Đúng" hoặc "Sai" khi nốt đang chơi gần hoặc lệch tần số chuẩn.
- Phát âm thanh mẫu của dây E để người dùng so sánh nếu muốn.

## 🛠️ Công nghệ sử dụng

- **HTML5** và **CSS3**: Giao diện người dùng đơn giản, trực quan.
- **JavaScript**: Điều khiển luồng dữ liệu, xử lý âm thanh, giao tiếp với microphone.
- **Web Audio API**: Ghi âm và xử lý tín hiệu âm thanh theo thời gian thực.
- **Web Workers**: Xử lý correlation để phân tích tần số mà không làm chậm UI.


## 🚀 Hướng dẫn sử dụng

1. **Mở file `index.html` trên trình duyệt hỗ trợ Web Audio API** (Chrome, Firefox, Edge).
2. **Cho phép truy cập microphone** khi được yêu cầu.
3. **Chọn dây đàn muốn chỉnh** (E2, A2, D3, G3, B3, E4).
4. **Gảy dây đàn tương ứng**, hệ thống sẽ hiển thị:
   - Tên nốt nhạc được phát hiện.
   - Tần số đo được.
   - Trạng thái "Đúng" (In-tune) hoặc "Sai" (Out-of-tune).
   - Mức độ lệch tần số.
5. Nhấn nút **"Bắt đầu/Dừng"** để phát âm thanh mẫu dây E (tuỳ chọn).

## ⚙️ Nguyên lý hoạt động

- Lấy mẫu tín hiệu âm thanh qua microphone.
- Gửi dữ liệu vào Web Worker để tính **correlation** với tập các tần số thử nghiệm.
- Xác định tần số có biên độ mạnh nhất → nốt nhạc gần đúng nhất.
- So sánh với tần số chuẩn để quyết định "Đúng" hoặc "Sai".

## 📌 Lưu ý

- Ứng dụng chạy hoàn toàn trên trình duyệt, không yêu cầu backend.
- Có thể cần môi trường HTTPS để truy cập microphone trên một số trình duyệt.

## 📄 Giấy phép

MIT License.