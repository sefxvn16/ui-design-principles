---
name: ui-design-principles
description: "Thiết kế, sửa và rà soát giao diện web, app hoặc game theo tư duy tổ chức không gian trong kiến trúc: công năng, bố cục, phân cấp, đường gióng, tỷ lệ, khoảng trống và quan hệ thị giác. Áp dụng cả chỉnh sửa UI cục bộ. Không dùng cho code không liên quan thiết kế UI, thiết kế công trình hoặc yêu cầu chỉ tạo ảnh bitmap hay đặc tả DESIGN.md."
---

# Nguyên tắc thiết kế giao diện

## A. Phạm vi áp dụng

Áp dụng khi thiết kế mới, chỉnh sửa hoặc review bố cục và quan hệ thị giác của UI web, app hoặc game. Dùng nguyên lý thiết kế kiến trúc để tổ chức giao diện; không quy định một phong cách hình ảnh hoặc công nghệ cố định.

Giữ các ràng buộc về tính năng, luồng nghiệp vụ và luật chơi. Skill không cấp quyền sửa, cài đặt, thêm dependency hoặc phát hành ngoài yêu cầu hiện tại và hướng dẫn Personal/Project.

Áp dụng quy tắc riêng dự án trong đúng dự án. Khi skill UI chuyên biệt đã đảm nhiệm cùng nội dung, chỉ bổ sung phần còn thiếu; không lặp hai quy trình. Skill này không bắt buộc gọi skill khác hoặc sinh ảnh. Yêu cầu chỉ tạo đặc tả hệ thiết kế hay tài sản bitmap thuộc phạm vi công cụ tương ứng.

## B. Xác định nhiệm vụ

**Đối tượng sử dụng:** khi bắt đầu, xác định giao diện dành cho ai: nhóm tuổi, quốc gia/khu vực, ngôn ngữ, bối cảnh văn hóa và mức quen thuộc với công nghệ. Nếu chưa có thông tin, hỏi người dùng trước khi chọn hướng thiết kế; không hỏi lại dữ kiện đã rõ. Dùng thông tin này để quyết định cách trình bày, mật độ, chữ, màu, biểu tượng và tương tác; không suy diễn sở thích chỉ từ tuổi hoặc quốc tịch.

Từ thông tin có sẵn, xác định kết quả cần đạt, nội dung, đối tượng chính, thiết bị, cách sử dụng và ràng buộc liên quan. Phân biệt thiết kế mới, sửa cục bộ và review. Với dự án có sẵn, xem quy ước, component và token liên quan trước khi đề xuất thay đổi.

Chỉ hỏi khi dữ liệu thiếu làm đổi hướng thiết kế; không hỏi lại dữ kiện đã có. Khi có thể tiếp tục với thông tin hiện tại, nêu giới hạn hoặc giả định có ảnh hưởng đến phương án. Nếu xung đột ràng buộc đòi quyết định lớn, nêu đánh đổi để người dùng quyết định.

Giới hạn phân tích và thay đổi vào phạm vi được giao cùng ảnh hưởng trực tiếp. Các phần dưới là nhóm hướng dẫn, không phải quy trình bắt buộc chạy toàn bộ cho mọi chỉnh sửa nhỏ.

Đọc `DESIGN.md` của dự án trước khi thiết kế, sửa hoặc kiểm UI; dùng các quy tắc đã xác nhận để đối chiếu cùng yêu cầu hiện tại và hướng dẫn dự án. Nếu có xung đột làm đổi quyết định thiết kế, nêu rõ để người dùng chốt. Nếu chưa có file và được phép ghi, tạo `DESIGN.md` ở gốc dự án từ yêu cầu đã chốt và tài liệu, code, UI đã kiểm. Tách rõ quy tắc đã xác nhận với hiện trạng chưa xác nhận; không biến lỗi UI thành quy tắc. Chỉ ghi phần liên quan: vùng chính/phụ và ưu tiên quan sát, bố cục và đường gióng, tỷ lệ và khoảng trống, màu và chữ, component và trạng thái, responsive và ngoại lệ đã duyệt. Không tự đặt thông số thiếu căn cứ. Nếu chỉ được phép đọc hoặc chưa có dự án đích, báo giới hạn thay vì tự tạo file.

## C. Tổ chức bố cục

- **Công năng và tổng thể:** xác định vùng chính (nội dung hoặc đối tượng người dùng làm việc cùng, gồm vùng gameplay) và ưu tiên cho nó vị trí, diện tích, tầm nhìn để người dùng nhận biết, quan sát và thao tác thuận lợi. Vùng phụ (điều hướng, công cụ, HUD, thông tin bổ trợ) đặt ở rìa hoặc vùng riêng; không che khuất hoặc chia cắt nội dung cần quan sát, trừ khi thao tác cần. Khi không gian hạn chế, điều chỉnh vùng phụ trước nhưng giữ thông tin và điều khiển thiết yếu ở mức dùng được. Kích thước vùng phải chứa được nội dung và thao tác cần thiết; thứ bậc và quan hệ kích thước đi trước chi tiết trang trí. Với sửa cục bộ, giữ cấu trúc không liên quan.
- **Phân cấp:** dùng vị trí, kích thước, tương phản và khoảng trống để thể hiện mức quan trọng, hành động và trạng thái. Thành phần phụ cần hỗ trợ việc hiểu hoặc thao tác với đối tượng chính; tránh nhiều điểm nhấn cùng tranh sự chú ý. Giữa các cấp kích thước (toàn màn, vùng, nhóm, thành phần), chuyển tiếp theo vai trò nội dung; tránh bước nhảy đột ngột không có lý do.
- **Nhóm và khoảng trống:** đặt thành phần theo quan hệ ý nghĩa. Phân biệt khoảng cách trong nhóm, giữa nhóm và với biên; không mặc định các khoảng bằng nhau. Xét cả hình dạng vùng trống và vai trò phân nhóm, tạo khoảng nghỉ, dành chỗ thao tác hoặc giữ tầm nhìn. Sửa các khe vụn hoặc khoảng trống vô tình chia cắt nội dung liên quan, không mặc định lấp đầy vùng trống. Sự thẳng hàng không được tạo liên hệ chức năng sai.
- **Ranh giới và phạm vi điều khiển:** khi có nhiều vùng hoặc đối tượng có thể thao tác, biểu đạt rõ điều khiển thuộc vùng nào và tác động lên đối tượng nào. Dùng nhãn, vị trí, cách nhóm hoặc dấu phân cách phù hợp; không mặc định đóng khung mọi nhóm.
- **Tỷ lệ và cân bằng:** chọn tương quan kích thước theo nội dung, thao tác và trọng lượng thị giác của chữ, hình, màu và mật độ. Cân bằng có thể bất đối xứng. Tỷ lệ vàng, đối xứng, một phần ba hoặc hệ lưới là phương án khi hữu ích, nhưng không là công thức bảo đảm đẹp hay yêu cầu áp vào mọi thành phần.
- **Nhịp và nhất quán:** thành phần cùng vai trò dùng cấu trúc, khoảng cách, kiểu biểu đạt và hành vi tương ứng. Tận dụng hệ có sẵn; biến thể hoặc ngoại lệ phải có lý do liên quan yêu cầu. Không ép nội dung khác vai trò giống nhau.

Khi các lựa chọn thiết kế xung đột, ưu tiên: khả năng sử dụng; ý nghĩa và thứ bậc; nhóm và quan hệ căn; tỷ lệ và nhịp; trang trí. Thứ tự này không cho phép bỏ qua yêu cầu trực tiếp hoặc ràng buộc dự án.

## D. Đường gióng và quan hệ căn

Xác định các chuẩn cần thiết: mép vùng nội dung, trục của đối tượng chính hoặc mép panel. Từ đó thiết lập chuẩn nội bộ của từng nhóm và liên hệ với tổng thể. Ưu tiên dùng lại chuẩn phù hợp; không thêm đường gióng chỉ để có lưới dày hơn.

Phân biệt vai trò: lưới chia không gian thành hệ vị trí; đường gióng xác định quan hệ căn; trục tổ chức hướng hoặc tâm; datum là đường, mặt hoặc vùng làm chuẩn liên kết. Chúng có thể trùng nhau nhưng không đồng nghĩa.

Với thành phần cần đặt hoặc sửa, xác định đang căn theo gì:

| Chuẩn               | Cách dùng                                                                                            |
| ------------------- | ---------------------------------------------------------------------------------------------------- |
| Mép khung           | Căn các vùng, panel, trường nhập hoặc hàng thẻ. Kiểm cả padding nếu cần liên kết nội dung bên trong. |
| Mép chữ             | Căn tiêu đề, nhãn và nội dung theo mép đọc thực tế.                                                  |
| Baseline            | Căn chữ khác cỡ hoặc nhãn/giá trị cùng hàng; đỉnh bounding box không thay thế baseline.              |
| Tâm                 | Căn đối tượng theo vùng chứa hoặc trục có ý nghĩa; không mặc định lấy tâm toàn màn.                  |
| Vùng hình nhìn thấy | Kiểm icon, ảnh và sprite có khoảng trống hoặc alpha trong khung.                                     |

Căn hình học dùng tọa độ; căn quang học xét cảm nhận của hình nhìn thấy. Nếu cần hiệu chỉnh quang học, xác định thành phần và độ dịch khi đo được; giữ phạm vi sửa hẹp, không thay padding toàn hệ để chữa một hình lệch.

Khi đo, dùng cùng hệ tọa độ và mức scale. Với hai khung, so sánh x để căn trái, x+w để căn phải, x+w/2 để căn tâm ngang; áp dụng tương tự cho chiều dọc. Baseline cần dữ liệu chữ phù hợp. Không đặt dung sai pixel chung cho mọi môi trường hoặc suy số đo layout gốc từ ảnh đã scale.

## E. Thích nghi và triển khai

Xét khả năng đọc và thao tác theo thiết bị, cách nhập và khoảng cách nhìn. Không làm chữ hoặc vùng thao tác khó dùng để giữ tỷ lệ. Với game, kiểm cả vùng gameplay cần quan sát và phần HUD có thể che khuất.

Khi nhiệm vụ cần hỗ trợ nhiều kích thước, nội dung hoặc trạng thái, giữ vai trò, nhóm và thứ tự ưu tiên khi đổi số cột, chuyển hàng hoặc vị trí. Xem các trường hợp liên quan như chữ dài, nội dung tăng, trạng thái khác hoặc màn hẹp. Không thu nhỏ cả UI để giữ nguyên bố cục; không ép responsive cho đầu ra chỉ có một khổ cố định.

Khi tác vụ ảnh hưởng việc chuyển màn, mở panel, đổi chế độ hoặc bố cục, giữ dấu nhận diện và ngữ cảnh đủ rõ để người dùng nhận ra đang ở đâu, đang thao tác với đối tượng nào và đang ở chế độ nào. Giữ rõ đường tiếp tục hoặc quay lại theo luồng hiện có; không buộc vị trí thành phần phải cố định. Dùng tiêu đề, trạng thái, lựa chọn đang hoạt động hoặc dấu hiệu sẵn có khi phù hợp. Không tự thêm màn trung gian, bước xác nhận hoặc animation chỉ để biểu đạt chuyển tiếp.

Khi được giao triển khai, chuyển quan hệ thiết kế thành ràng buộc layout của công nghệ đang dùng, tận dụng component/token và quy ước dự án. Không tự thêm framework, dependency hoặc lớp trừu tượng.

## F. Kiểm tra và bàn giao

Kiểm các quan hệ và điều kiện sử dụng chịu ảnh hưởng bởi thay đổi, bằng công cụ và dữ liệu thực có. Kết hợp kiểm hình học với xem ở kích thước sử dụng thực tế khi có thể. Nếu không thể mở giao diện, thử thiết bị hoặc đo trực tiếp, nêu rõ giới hạn; không coi suy luận là kết quả đã thử.

Với vùng chịu ảnh hưởng, kiểm thành phần trong nhóm và nhóm trong tổng thể liên quan: kích thước, điểm nhấn, khoảng trống và điều khiển có còn làm rõ đối tượng chính và quan hệ giữa các phần không. Nếu thay đổi có chuyển màn, chế độ hoặc bố cục, kiểm lại dấu định hướng và phạm vi tác động của điều khiển. Chỉ mở rộng kiểm tra đến quan hệ trực tiếp bị ảnh hưởng, không biến sửa cục bộ thành rà toàn bộ giao diện hoặc luồng.

Khi review, chỉ rõ thành phần, chuẩn so sánh, vấn đề và ảnh hưởng, kèm cách sửa khi đủ căn cứ. Phân biệt số đo thực, quan sát từ ảnh và giả thuyết cần kiểm. Không bịa tọa độ, baseline hoặc kết quả thao tác. Có thể đo trong hệ tọa độ ảnh nếu ghi rõ là số đo ảnh, không phải đơn vị layout của sản phẩm.

Bàn giao theo tác vụ:

- **Thiết kế mới:** đưa phương án đủ để sử dụng hoặc triển khai và giải thích quyết định bố cục trọng yếu.
- **Sửa cục bộ:** nêu phần đã đổi, cách kiểm và giới hạn còn lại.
- **Review:** đưa nhận xét cụ thể có thể hành động; nếu chỉ được giao review thì không tự sửa.

Dùng bản đồ hoặc overlay đường gióng khi cần làm rõ quan hệ và có khả năng tạo. Không bắt mọi tác vụ sinh sơ đồ hoặc báo cáo dài. Khi được giao triển khai, phần giải thích không thay thế kết quả thực hiện.

Đối chiếu vùng được kiểm hoặc sửa với các quy tắc đã xác nhận trong `DESIGN.md`. Khi được phép ghi, cập nhật file nếu có quyết định mới đã duyệt hoặc quy tắc đã xác nhận còn thiếu; giữ nội dung không liên quan. Không đổi quy tắc để hợp thức hóa UI lệch chuẩn. Báo kết quả kiểm từng lần riêng, không biến `DESIGN.md` thành nhật ký kiểm tra.
