# Kiểm tra: phép thử, trước–sau, review

Đọc khi kiểm một thay đổi, so trước–sau hoặc review. Phạm vi kiểm và cách bàn giao ở mục F của `SKILL.md`.

## Phép thử

Chọn phép thử theo phạm vi thay đổi.

| Phép thử     | Cách làm                                                                                      | Đạt khi                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Squint       | Làm mờ hoặc thu nhỏ ảnh màn đến khi không đọc được chữ                                        | Vẫn nhận ra vùng chính, vùng phụ và các nhóm lớn theo đúng thứ tự ưu tiên; điểm nhấn chính thấy đầu tiên |
| Skeleton     | Thay chữ bằng khối trơn                                                                       | Phân cấp và nhóm vẫn đọc được từ vị trí, kích thước và khoảng trống                           |
| 5 giây       | Nhìn màn khoảng 5 giây rồi trả lời                                                            | Nói được màn này là gì, đối tượng chính là gì và hành động tiếp theo ở đâu                    |
| Đường tác vụ | Đi qua một tác vụ đại diện bằng các cách nhập trong phạm vi yêu cầu (chuột, chạm, bàn phím)   | Focus theo trình tự công việc, luôn nhìn thấy; không bỏ sót thông tin cần để quyết định       |
| Mép và lớp   | Mở lớp nổi gần mép vùng chứa; cuộn qua vùng neo; xem hai phía mỗi điểm đổi bố cục liên quan    | Không cắt, không che, không chồng                                                             |

Ghi rõ phép thử nào đã chạy trên giao diện thật, phép nào chỉ suy luận từ code hoặc ảnh. Phép 5 giây do agent tự trả lời thì ghi là tự đánh giá, không phải thử với người dùng.

## Trước và sau

Khi sửa UI hiện có và mở được giao diện, ghi nhận vùng liên quan trước khi sửa bằng ảnh hoặc số đo phù hợp. So sau sửa với cùng kích thước xem, dữ liệu, trạng thái và vị trí cuộn khi các yếu tố này ảnh hưởng kết quả. Chỉ ra quan hệ đã thay đổi, quan hệ trực tiếp cần giữ và thao tác đã kiểm lại. Điều kiện không thể giữ giống nhau thì ghi rõ khác biệt và giới hạn so sánh. Không bắt thiết kế mới có ảnh trước. Không đạt: so ảnh trước ở desktop với ảnh sau ở mobile rồi kết luận bố cục tốt hơn.

## Review

Mỗi phát hiện ghi đủ các phần sau.

- **Vị trí:** thành phần hoặc vùng.
- **Chuẩn so sánh:** quy tắc của skill, `DESIGN.md`, WCAG hoặc thành phần cùng vai trò.
- **Quan sát → hệ quả → hướng sửa:** hướng sửa chỉ đưa khi đủ căn cứ.
- **Mức:** P0 chặn tác vụ, gây mất dữ liệu hoặc không truy cập được; P1 hoàn thành được nhưng dễ sai hoặc phải tìm trợ giúp; P2 làm chậm, gây nhầm tạm thời hoặc lệch hệ thống; P3 lệch thị giác không ảnh hưởng tác vụ.
- **Bằng chứng:** số đo thực, quan sát từ ảnh hoặc giả thuyết cần kiểm.

Sắp phát hiện từ P0. Thứ tự sửa đề xuất: P0; trạng thái thiếu; lệch hệ thống; không nhất quán thị giác. Ghi ngắn "Điều đang tốt" để phần đúng không bị phá khi sửa. Không gán điểm số tổng. Không bịa tọa độ, baseline hoặc kết quả thao tác. Có thể đo trong hệ tọa độ ảnh nếu ghi rõ là số đo ảnh, không phải đơn vị layout của sản phẩm.

Dùng bản đồ hoặc overlay đường gióng khi cần làm rõ quan hệ và có khả năng tạo. Không bắt mọi tác vụ sinh sơ đồ hoặc báo cáo dài. Khi được giao triển khai, phần giải thích không thay thế kết quả thực hiện.
