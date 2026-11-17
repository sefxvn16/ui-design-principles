# Cảm ứng: tablet, mobile

Đọc khi sản phẩm dùng chạm và tác vụ chạm tới điều khiển, vùng chạm hoặc bố cục theo kích thước màn. Quy tắc chung ở `SKILL.md` vẫn áp dụng; file này chỉ thêm phần làm đổi bố cục. Tablet có chuột hoặc bàn phím thì đọc thêm `desktop.md`.

- **Khai báo tư thế:** ghi hướng màn, tay đỡ máy, ngón chạm và cỡ màn trước khi đặt điều khiển theo vị trí tay. Chỉ áp nghiên cứu hoặc quy tắc vị trí có cùng tư thế; không dùng "vùng ngón cái" của nghiên cứu cầm dọc một tay cho màn ngang cầm hai tay. Khi đổi thiết bị hoặc tư thế mục tiêu, kiểm lại các quyết định vị trí dựa trên tư thế cũ.
- **Vùng chạm:** 44×44 (WCAG 2.5.5 mức AAA; Apple HIG 44 pt) hoặc khoảng 48 dp, tương đương khoảng 9 mm, cách nhau khoảng 8 px (web.dev, Accessible tap targets). Các mốc khác nhau thì theo `DESIGN.md`; chưa có thì nêu các mốc kèm điều kiện và hỏi khi lựa chọn làm đổi bố cục. Khi so với ngưỡng tính bằng mm, đổi px CSS sang mm theo thiết bị: mm = px CSS × (chiều rộng màn tính bằng mm ÷ chiều rộng khung tính bằng px CSS).
- **Vùng bấm vô hình:** khi phần hiển thị nhỏ hơn ngưỡng, mở rộng vùng bấm vô hình quanh nó; không làm hàng hoặc hình to ra phá tỷ lệ và nhịp. Vùng bấm vô hình của các mục tiêu không chồng nhau và không làm vùng chứa sinh thanh cuộn. Không đạt: đặt `min-height` bằng ngưỡng làm cả bảng phình.
- **Mục tiêu gần mép màn:** chạm hẳn mép, hoặc cách mép rõ ràng; tránh khoảng lửng ở giữa. Mốc tham khảo: điểm chạm lệch trong khoảng 6,4 mm từ mép (Kasahara, Yamanaka, Miyashita 2026: 15 người, một tay cầm, ngón trỏ tay kia chạm, Pixel 6a); tư thế khác thì chỉ tham khảo.
- **Xoay màn và vùng an toàn:** dọc và ngang là hai bố cục sắp lại theo thứ tự ưu tiên (E), không phải một bố cục xoay. Điều khiển và thông tin thiết yếu nằm trong vùng an toàn nền tảng báo (tai thỏ, góc bo, thanh hệ thống; trên web là `env(safe-area-inset-*)`).
- **Che khuất:** ngón và bàn tay che vùng đang chạm và quanh nó; thông tin cần đọc để quyết định và phản hồi của thao tác không đặt ngay dưới đường tay đưa tới. Bàn phím ảo không che trường đang nhập và nút tiếp tục.
- **Không có hover:** thao tác bắt buộc không phụ thuộc hover; nhấn giữ không là đường duy nhất.
- **Kiểm:** đo ở khung thấp nhất của thiết bị mục tiêu (thường là màn ngang của điện thoại) và một khung lớn hơn. Đo trên trình duyệt giả lập không chứng minh độ chính xác chạm; chưa thử trên máy thật thì ghi rõ.
