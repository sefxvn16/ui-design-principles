# Nguyên tắc thiết kế giao diện

[English](README.md) | [Tiếng Việt](README.vi.md)

Skill chuyển các nguyên lý thiết kế kiến trúc thành quy tắc thiết kế, chỉnh sửa và rà soát giao diện web, app và game.

Skill vận dụng tổ chức không gian, phân cấp, trục và datum, tỷ lệ, nhịp điệu và quan hệ đặc/rỗng vào bố cục UI. AI dùng các quy tắc này để ưu tiên vùng làm việc chính, tổ chức vùng phụ, thiết lập quan hệ căn và kiểm tra giao diện. Quyết định riêng của dự án được ghi vào `DESIGN.md` để những lần sau áp dụng và đối chiếu.

## Nội dung

- Xác định đối tượng sử dụng: nhóm tuổi, quốc gia/khu vực, ngôn ngữ, bối cảnh văn hóa và mức quen thuộc với công nghệ. Chỉ hỏi thông tin còn thiếu khi câu trả lời có thể đổi quyết định thiết kế, không suy diễn sở thích chỉ từ đặc điểm nhân khẩu học.
- Xác định mức can thiệp (sửa cục bộ, tinh chỉnh, thiết kế lại, review) và loại màn (Thao tác, Đọc, Thuyết phục, Trải nghiệm, Chơi); loại màn quyết định mật độ, mức lặp và mức tự do bố cục.
- Ưu tiên vị trí, diện tích và tầm nhìn của vùng chính để người dùng quan sát và thao tác; vùng phụ hỗ trợ vùng chính; đường đọc đi theo đường thao tác.
- Căn theo chuẩn rõ ràng: mép khung, mép chữ, baseline, tâm và vùng hình nhìn thấy. Cấu trúc đến từ trục căn chung thay vì khung viền; các cột cạnh nhau kết thúc trên đường đáy chung; bảng giữ nhãn và số trên mép cố định.
- Quy tắc riêng nền tảng nằm ở file riêng, chỉ đọc khi cần: `references/desktop.md` (chuột, trackpad, bàn phím trên Windows/macOS) và `references/touch.md` (cảm ứng trên tablet, mobile).
- Khoảng cách theo thứ tự cố định (trong nhóm < giữa nhóm < giữa vùng); mỗi vùng trống lớn có vai trò nêu được; mỗi vùng bao biểu đạt một phạm vi.
- Đổi bố cục responsive kế thừa breakpoint của dự án, giữ vai trò, thứ tự ưu tiên và ngữ cảnh. Nội dung, trạng thái biến đổi, lớp nổi và vùng cuộn được kiểm để không bị cắt, che hoặc xê dịch.
- Ngưỡng số bắt buộc chỉ lấy từ chuẩn công khai (WCAG về vùng chạm, tương phản, focus nhìn thấy) hoặc `DESIGN.md` của dự án.
- Kiểm bằng các phép thử có tên (squint, skeleton, 5 giây, đường tác vụ, mép và lớp) và so trước–sau trên cùng điều kiện. Phát hiện khi review ghi vị trí, chuẩn so sánh, quan sát → hệ quả → hướng sửa, mức P0–P3 và loại bằng chứng.

Mỗi quy tắc nêu điều kiện áp dụng, hành vi bắt buộc, ngoại lệ và dấu hiệu không đạt. Skill không quy định phong cách hình ảnh, framework hoặc thang khoảng cách cố định. Các ràng buộc dự án và giới hạn quyền thao tác vẫn được giữ.

## File và ngôn ngữ

| File | Vai trò |
| --- | --- |
| [SKILL.md](ui-design-principles/SKILL.md) | Bản skill tiếng Việt |
| [SKILL.en.md](ui-design-principles/SKILL.en.md) | Bản dịch đầy đủ tiếng Anh |
| [references/desktop.md](ui-design-principles/references/desktop.md), [desktop.en.md](ui-design-principles/references/desktop.en.md) | Quy tắc desktop (chuột, trackpad, bàn phím), tiếng Việt và tiếng Anh |
| [references/touch.md](ui-design-principles/references/touch.md), [touch.en.md](ui-design-principles/references/touch.en.md) | Quy tắc cảm ứng (tablet, mobile), tiếng Việt và tiếng Anh |
| [references/verify.md](ui-design-principles/references/verify.md), [verify.en.md](ui-design-principles/references/verify.en.md) | Phép thử, so trước–sau và định dạng review, tiếng Việt và tiếng Anh |
| [README.md](README.md) | Tài liệu tiếng Anh |

## Sử dụng

Với AI hỗ trợ skill, chép cả thư mục `ui-design-principles` (gồm `references/`) vào nơi AI đó đọc skill. Để dùng tiếng Anh, chép nội dung `SKILL.en.md` vào `SKILL.md` trong thư mục cài đặt; bản tiếng Anh dẫn tới các file `*.en.md`. Mỗi bản cài chỉ dùng một ngôn ngữ hoạt động.

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
