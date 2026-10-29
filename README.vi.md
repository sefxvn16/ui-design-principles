# Nguyên tắc thiết kế giao diện

[English](README.md) | [Tiếng Việt](README.vi.md)

Skill chuyển các nguyên lý thiết kế kiến trúc thành quy tắc thiết kế, chỉnh sửa và rà soát giao diện web, app và game.

Skill vận dụng tổ chức không gian, phân cấp, trục và datum, tỷ lệ, nhịp điệu và quan hệ đặc/rỗng vào bố cục UI. AI dùng các quy tắc này để ưu tiên vùng làm việc chính, tổ chức vùng phụ, thiết lập quan hệ căn và kiểm tra giao diện. Quyết định riêng của dự án được ghi vào `DESIGN.md` để những lần sau áp dụng và đối chiếu.

## Nội dung

- Xác định đối tượng sử dụng trước khi chọn hướng thiết kế: nhóm tuổi, quốc gia/khu vực, ngôn ngữ, bối cảnh văn hóa và mức quen thuộc với công nghệ. Hỏi thông tin còn thiếu, không suy diễn sở thích chỉ từ đặc điểm nhân khẩu học.
- Ưu tiên vị trí, diện tích và tầm nhìn của vùng chính để người dùng quan sát và thao tác; vùng phụ hỗ trợ vùng chính.
- Căn theo chuẩn rõ ràng: mép khung, mép chữ, baseline, tâm và vùng hình nhìn thấy.
- Tổ chức nhóm, tỷ lệ, khoảng trống, nhịp và phạm vi điều khiển theo nội dung và công năng.
- Giữ vai trò, thứ tự ưu tiên và ngữ cảnh khi đổi bố cục responsive.
- Phân biệt số đo thực, quan sát từ ảnh và giả định chưa kiểm chứng khi rà soát.

Skill không quy định phong cách hình ảnh, framework hoặc thang khoảng cách cố định. Các ràng buộc dự án và giới hạn quyền thao tác vẫn được giữ.

## File và ngôn ngữ

| File | Vai trò |
| --- | --- |
| [SKILL.md](ui-design-principles/SKILL.md) | Bản skill tiếng Việt |
| [SKILL.en.md](ui-design-principles/SKILL.en.md) | Bản dịch đầy đủ tiếng Anh |
| [README.md](README.md) | Tài liệu tiếng Anh |

## Sử dụng

Với AI hỗ trợ skill, đặt `SKILL.md` trong thư mục `ui-design-principles` tại nơi AI đó đọc skill. Để dùng tiếng Anh, chép nội dung `SKILL.en.md` vào `SKILL.md` trong thư mục cài đặt. Mỗi bản cài chỉ dùng một ngôn ngữ hoạt động.

Cũng có thể cung cấp trực tiếp một trong hai file cho AI cùng yêu cầu có phạm vi rõ, ví dụ:

> Rà soát màn hình này theo skill UI design principles. Kiểm tra vùng làm việc chính, panel phụ, quan hệ căn và khả năng quan sát. Chỉ báo nhận xét, không sửa file.

Tuân thủ hướng dẫn cài đặt và quyền thao tác của AI đang dùng. Cài skill không cấp quyền sửa file ngoài phạm vi, thêm dependency hoặc phát hành thay đổi.

## Quy tắc thiết kế của dự án

Trước khi làm UI, skill đọc `DESIGN.md` của dự án. Nếu chưa có file và được phép ghi, skill tạo file từ yêu cầu đã chốt và bằng chứng dự án đã kiểm.

Quy tắc đã xác nhận được tách khỏi hiện trạng chưa xác nhận. Những lần sau đối chiếu UI với các quy tắc đó. Chỉ cập nhật quyết định đã duyệt hoặc quy tắc đã xác nhận còn thiếu; không sửa quy tắc để hợp thức hóa lỗi UI. Kết quả kiểm được báo riêng.

## Giới hạn kiểm chứng

Skill yêu cầu AI báo đúng những gì đã đọc hoặc thử. Kiểm tài liệu không chứng minh giao diện thực tế dễ dùng, đáp ứng yêu cầu tiếp cận hoặc đúng về thị giác. Kết quả phụ thuộc AI, công cụ và bằng chứng dự án có sẵn.

## Giới thiệu

Được duy trì bởi [sefxvn16 (Seafox)](https://github.com/sefxvn16). Repo chứa skill nguyên tắc thiết kế giao diện và bản dịch tiếng Anh dành cho AI hỗ trợ lập trình.

## Giấy phép

[MIT](LICENSE). Bản quyền (c) 2026 Seafox (sefxvn16).
