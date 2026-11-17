# Desktop: chuột, trackpad, bàn phím (Windows, macOS)

Đọc khi sản phẩm dùng chuột, trackpad hoặc bàn phím và tác vụ chạm tới điều khiển hoặc bố cục theo kích thước cửa sổ. Quy tắc chung ở `SKILL.md` vẫn áp dụng; file này chỉ thêm phần làm đổi bố cục. Skill không quy định khác biệt riêng giữa Windows và macOS; app native theo một hệ điều hành thì theo hướng dẫn của nền tảng đó hoặc `DESIGN.md`.

- **Cửa sổ đổi cỡ:** kích thước xem do người dùng kéo, không theo danh sách thiết bị. Xác định cửa sổ nhỏ nhất sản phẩm hỗ trợ (theo `DESIGN.md`; chưa có thì hỏi khi nó làm đổi bố cục). Kiểm ở cửa sổ đó, một cỡ thường dùng và một cửa sổ rất rộng. Trên cửa sổ rất rộng, vùng chính không kéo giãn đến mức dòng đọc quá dài hoặc nhãn cách xa giá trị của nó. Không đạt: bảng hai cột giãn toàn màn, nhãn trái và số phải cách nhau nửa màn hình.
- **Mật độ:** với con trỏ, màn Thao tác được phép dày hơn bản cảm ứng, nhưng vẫn giữ thứ tự khoảng cách ở C và vùng chạm tối thiểu ở E.
- **Hover:** hover chỉ bổ sung. Thông tin hoặc thao tác bắt buộc phải tới được bằng click và bàn phím; nếu sản phẩm cũng chạy trên cảm ứng, phải có đường bằng chạm. Tooltip không chứa thông tin duy nhất cần để quyết định. Không đạt: nút xóa chỉ hiện khi rê chuột qua hàng.
- **Bàn phím và focus:** thứ tự focus đi theo đường thao tác ở C. Dấu focus nhìn thấy (WCAG 2.4.7), không bị phần neo che (WCAG 2.4.11), không làm thành phần đổi kích thước hoặc đẩy thành phần bên cạnh. Tránh viền kép do viền thành phần cộng outline focus. Không đạt: focus nhảy từ form sang thanh điều hướng rồi quay lại nút gửi.
- **Menu chuột phải và phím tắt:** không là đường duy nhất tới một thao tác.
- **Lớp nổi gần mép cửa sổ:** menu và popover mở gần mép đổi hướng hoặc vị trí để không bị cắt; kiểm lại khi thu nhỏ cửa sổ.
