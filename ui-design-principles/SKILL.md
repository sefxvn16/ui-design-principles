---
name: ui-design-principles
description: "Thiết kế, sửa và rà soát giao diện web, app hoặc game theo tư duy tổ chức không gian trong kiến trúc: công năng, bố cục, phân cấp, đường gióng, tỷ lệ, khoảng trống và quan hệ thị giác. Áp dụng cả chỉnh sửa UI cục bộ. Không dùng cho code không liên quan thiết kế UI, thiết kế công trình hoặc yêu cầu chỉ tạo ảnh bitmap hay đặc tả DESIGN.md."
---

# Nguyên tắc thiết kế giao diện

## A. Phạm vi áp dụng

Áp dụng khi thiết kế mới, chỉnh sửa hoặc review bố cục và quan hệ thị giác của UI web, app hoặc game. Dùng nguyên lý thiết kế kiến trúc để tổ chức giao diện; không quy định một phong cách hình ảnh hoặc công nghệ cố định.

Giữ các ràng buộc về tính năng, luồng nghiệp vụ và luật chơi. Skill không cấp quyền sửa, cài đặt, thêm dependency hoặc phát hành ngoài yêu cầu hiện tại và hướng dẫn Personal/Project.

Áp dụng quy tắc riêng dự án trong đúng dự án. Khi skill UI chuyên biệt đã đảm nhiệm cùng nội dung, chỉ bổ sung phần còn thiếu; không lặp hai quy trình. Skill này không bắt buộc gọi skill khác hoặc sinh ảnh. Yêu cầu chỉ tạo đặc tả hệ thiết kế hay tài sản bitmap thuộc phạm vi công cụ tương ứng.

**Cách đọc quy tắc:** mỗi quy tắc nêu điều kiện áp dụng, hành vi bắt buộc, ngoại lệ và dấu hiệu không đạt. Số đo bắt buộc chỉ lấy từ chuẩn công khai (WCAG) hoặc từ `DESIGN.md`/quy ước dự án. Số khác trong skill là dấu hiệu cần xem lại, không phải lỗi tự động. Bỏ hoặc vượt một quy tắc phải có lý do viết được trong một câu, gắn với yêu cầu hoặc ràng buộc cụ thể. Không dùng "hợp lý", "cân đối", "đẹp" làm tiêu chí nếu không kèm quan hệ hoặc tác vụ kiểm được.

## B. Xác định nhiệm vụ

**Đối tượng sử dụng:** dùng dữ kiện đã có để xác định các đặc điểm của đối tượng ảnh hưởng đến nhiệm vụ: nhóm tuổi, quốc gia/khu vực, ngôn ngữ, bối cảnh văn hóa và mức quen thuộc với công nghệ. Chỉ hỏi phần còn thiếu khi câu trả lời có thể làm đổi quyết định thiết kế trong phạm vi được giao. Với thiết kế mới chưa rõ đối tượng, hỏi trước khi chọn hướng; với sửa cục bộ, không bắt thu thập đủ hồ sơ đối tượng. Dùng thông tin này để quyết định cách trình bày, mật độ, chữ, màu, biểu tượng và tương tác; không suy diễn sở thích chỉ từ tuổi hoặc quốc tịch.

Từ thông tin có sẵn, xác định kết quả cần đạt, nội dung, đối tượng chính, thiết bị, cách sử dụng và ràng buộc liên quan. Với dự án có sẵn, xem quy ước, component và token liên quan trước khi đề xuất thay đổi.

**Nền tảng và cách nhập:** xác định thiết bị đích, cách nhập (chuột, trackpad, bàn phím, chạm) và hướng màn. Khi tác vụ chạm tới điều khiển, vùng chạm hoặc bố cục theo kích thước màn, đọc thêm file nền tảng tương ứng; sửa cục bộ không chạm tới các yếu tố này thì không cần.

| Sản phẩm dùng                                  | Đọc thêm                                    |
| ---------------------------------------------- | ------------------------------------------- |
| Chuột, trackpad, bàn phím (Windows, macOS)     | `references/desktop.md`                     |
| Cảm ứng (tablet, mobile)                       | `references/touch.md`                       |
| Cả hai (web responsive, tablet có bàn phím)    | Cả hai file                                 |

**Mức can thiệp:** xác định một mức cho tác vụ trước khi sửa.

| Mức          | Khi nào                                          | Được đổi                                              | Phải giữ                                         |
| ------------ | ------------------------------------------------ | ----------------------------------------------------- | ------------------------------------------------ |
| Sửa cục bộ   | Yêu cầu nêu một thành phần, vùng hoặc lỗi cụ thể | Vùng được giao và quan hệ trực tiếp với nó            | Cấu trúc, nhận diện và quy tắc ngoài vùng        |
| Tinh chỉnh   | Yêu cầu cải thiện màn hoặc luồng có sẵn          | Bố cục, phân cấp, khoảng cách trong hệ hiện có        | Nhận diện thị giác, component/token, luồng       |
| Thiết kế lại | Yêu cầu nêu rõ thay hướng hoặc nhận diện         | Cấu trúc và nhận diện                                 | Tính năng, luồng nghiệp vụ, luật chơi            |
| Review       | Chỉ yêu cầu nhận xét                             | Không sửa                                             | Toàn bộ                                          |

Không trộn tinh chỉnh với thiết kế lại trong cùng tác vụ. Yêu cầu không nói rõ mức thì chọn mức thấp nhất đáp ứng được yêu cầu và nêu giả định; nếu mức đó không đủ, nêu lý do và hỏi. Không đạt: được giao sửa một panel nhưng đổi token dùng chung của cả ứng dụng.

**Loại màn:** xếp từng màn (hoặc từng vùng nếu một màn có nhiều loại) vào một loại; loại quyết định mật độ, mức lặp và mức tự do bố cục.

| Loại         | Ví dụ                                   | Mật độ                                                       | Vị trí và lặp                                                                    | Bất đối xứng                      |
| ------------ | --------------------------------------- | ------------------------------------------------------------ | -------------------------------------------------------------------------------- | --------------------------------- |
| Thao tác     | Dashboard, admin, công cụ, form nhiều bước | Cao khi tác vụ cần so sánh hoặc thao tác liên tục            | Điều khiển cùng vai trò giữ vị trí giữa các màn; lặp cấu trúc cùng vai trò là đúng | Chỉ khi phản ánh vai trò vùng     |
| Đọc          | Tài liệu, bài viết, trợ giúp            | Ưu tiên dòng đọc liên tục                                    | Heading và section lặp nhất quán                                                 | Chỉ khi phản ánh vai trò vùng     |
| Thuyết phục  | Landing page, trang sản phẩm            | Theo luận điểm của từng section                              | Hai section liền kề khác vai trò không dùng chung bố cục                         | Cho phép                          |
| Trải nghiệm  | Portfolio, trưng bày                    | Theo nhịp trình bày                                          | Biến đổi có chủ đích                                                             | Cho phép                          |
| Chơi         | Gameplay, HUD, menu game                | Vùng gameplay ưu tiên tầm nhìn; HUD tối thiểu, đặt ở rìa     | HUD và điều khiển giữ vị trí trong một chế độ chơi                               | Theo luật chơi                    |

Xác định loại theo màn, không theo cả sản phẩm: landing page của một app là Thuyết phục, màn làm việc trong app là Thao tác. Không chắc thì chọn theo tác vụ chính của người dùng trên màn và nêu giả định.

Chỉ hỏi khi dữ liệu thiếu làm đổi hướng thiết kế; không hỏi lại dữ kiện đã có. Khi có thể tiếp tục với thông tin hiện tại, nêu giới hạn hoặc giả định có ảnh hưởng đến phương án. Nếu xung đột ràng buộc đòi quyết định lớn, nêu đánh đổi để người dùng quyết định.

Giới hạn phân tích và thay đổi vào phạm vi được giao cùng ảnh hưởng trực tiếp. Các phần dưới là nhóm hướng dẫn, không phải quy trình bắt buộc chạy toàn bộ cho mọi chỉnh sửa nhỏ.

Đọc `DESIGN.md` của dự án trước khi thiết kế, sửa hoặc kiểm UI; dùng các quy tắc đã xác nhận để đối chiếu cùng yêu cầu hiện tại và hướng dẫn dự án. Nếu có xung đột làm đổi quyết định thiết kế, nêu rõ để người dùng chốt. Nếu chưa có file và được phép ghi, tạo `DESIGN.md` ở gốc dự án từ yêu cầu đã chốt và tài liệu, code, UI đã kiểm. Tách rõ quy tắc đã xác nhận với hiện trạng chưa xác nhận; không biến lỗi UI thành quy tắc. Chỉ ghi phần liên quan: loại màn, vùng chính/phụ và ưu tiên quan sát, bố cục và đường gióng, tỷ lệ, thang khoảng cách và khoảng trống, điểm đổi bố cục, màu và chữ, component và trạng thái, responsive và ngoại lệ đã duyệt. Không tự đặt thông số thiếu căn cứ. Nếu chỉ được phép đọc hoặc chưa có dự án đích, báo giới hạn thay vì tự tạo file.

## C. Tổ chức bố cục

- **Công năng và tổng thể:** xác định vùng chính (nội dung hoặc đối tượng người dùng làm việc cùng, gồm vùng gameplay) và ưu tiên cho nó vị trí, diện tích, tầm nhìn để người dùng nhận biết, quan sát và thao tác thuận lợi. Vùng phụ (điều hướng, công cụ, HUD, thông tin bổ trợ) đặt ở rìa hoặc vùng riêng; không che khuất hoặc chia cắt nội dung cần quan sát, trừ khi thao tác cần. Khi không gian hạn chế, điều chỉnh vùng phụ trước nhưng giữ thông tin và điều khiển thiết yếu ở mức dùng được. Kích thước vùng phải chứa được nội dung và thao tác cần thiết; thứ bậc và quan hệ kích thước đi trước chi tiết trang trí. Với sửa cục bộ, giữ cấu trúc không liên quan.
- **Đường đọc và đường thao tác:** khi đặt hoặc đổi thứ tự vùng, xác định trình tự của tác vụ chính: bắt đầu ở đâu, cần đọc gì để quyết định, thực hiện ở điều khiển nào, kết quả hiện ở đâu. Đặt thông tin cần cho một quyết định trước hoặc cùng vùng với điều khiển thực hiện quyết định đó; phản hồi của thao tác hiện gần nơi thao tác hoặc nơi người dùng đang nhìn. Ngoại lệ: nhiều vùng làm việc song song là hợp lệ; thứ tự không bắt buộc trùng tuyệt đối với trái→phải, trên→dưới. Không đạt: nút xác nhận đứng trước phần tóm tắt cần đọc; người dùng phải rời nhóm sang vùng không liên quan rồi quay lại mới hoàn tất được.
- **Phân cấp:** dùng vị trí, kích thước, tương phản và khoảng trống để thể hiện mức quan trọng, hành động và trạng thái. Mỗi màn có một điểm nhấn chính: thành phần vẫn thấy đầu tiên khi làm squint test (F). Mỗi điểm quyết định (một form, hộp thoại, thẻ hoặc hàng công cụ) có tối đa một hành động chính; hành động khác ở cấp phụ. Màn Thao tác có thể có nhiều điểm quyết định song song, mỗi điểm vẫn chỉ một hành động chính. Thành phần phụ cần hỗ trợ việc hiểu hoặc thao tác với đối tượng chính. Giữa các cấp kích thước (toàn màn, vùng, nhóm, thành phần), mỗi cấp phải phân biệt được với cấp liền kề và cấp chứa nó không nhỏ hơn cấp được chứa. Chữ dùng ít bậc, thường 3 đến 4 (ví dụ tiêu đề; tên hoặc đầu mục; nhãn; chú thích); bậc tạo bằng cỡ, độ đậm và vị trí, không thêm màu chỉ để phân cấp. Không đạt: hai cấp heading khác vai trò trông giống nhau; tiêu đề nhóm nổi hơn tiêu đề vùng chứa nó; mỗi dòng một cỡ chữ.
- **Nhóm và khoảng cách:** đặt thành phần theo quan hệ ý nghĩa. Khoảng cách theo thứ tự bắt buộc: trong nhóm < giữa nhóm < giữa vùng. Heading gần phần nó dẫn hơn phần phía trên: khoảng từ heading tới nội dung của nó nhỏ hơn khoảng từ nội dung phía trên tới heading. Lấy giá trị từ thang khoảng cách của dự án; chưa có thang thì dùng một thang nhất quán và ghi vào `DESIGN.md` khi được phép. Sự thẳng hàng không được tạo liên hệ chức năng sai. Không đạt: khoảng giữa hai nhóm bằng hoặc nhỏ hơn khoảng trong nhóm; heading cách đều nội dung trên và dưới.
- **Khoảng trống có vai trò:** mỗi vùng trống lớn phải có một vai trò nêu được: tách nhóm, khoảng nghỉ, dành chỗ thao tác, giữ tầm nhìn hoặc chừa chỗ cho nội dung biến đổi. **Lỗ trống** là vùng trống không có vai trò nào trong số đó. **Khe vụn** là khoảng hẹp còn lại sau khi xếp, không có vai trò hoặc tách hai thành phần liên quan. Sửa bằng cách đổi kích thước hoặc vị trí vùng liên quan; không lấp bằng nội dung. Dấu hiệu cần xem lại: vùng trống không vai trò cao từ khoảng 40% chiều cao màn trở lên.
- **Mật độ và vùng bao:** chọn mật độ theo loại màn (B) và thông tin cần quan sát, so sánh, thao tác trong cùng tác vụ; dữ liệu cần đối chiếu nằm trong cùng vùng quan sát. Mỗi phần tử phải trả lời được câu hỏi: bỏ nó đi thì người dùng mất thông tin hoặc thao tác nào cho tác vụ; không trả lời được thì bỏ hoặc chuyển xuống lớp xem thêm. Không thêm dữ liệu, section hoặc vùng phụ chỉ để lấp chỗ trống; không bịa số liệu, khách hàng hoặc trích dẫn, dữ liệu mẫu phải ghi rõ là mẫu. Không ẩn dữ liệu thiết yếu vào tab, modal hoặc mục thu gọn chỉ để trông thoáng. Nhóm bằng khoảng cách trước; chỉ thêm khung, nền hoặc đường kẻ khi khoảng cách không đủ phân biệt. Mỗi vùng bao (khung, thẻ, panel) biểu đạt một đơn vị nội dung, một phạm vi thao tác hoặc một trạng thái; vùng bao lồng nhau hợp lệ khi mỗi cấp có phạm vi riêng. Không đạt: thẻ lồng thẻ cùng một phạm vi; dữ liệu cần so sánh bị tách vào các thẻ phải mở lần lượt.
- **Ranh giới và phạm vi điều khiển:** khi có nhiều vùng hoặc đối tượng có thể thao tác, biểu đạt rõ điều khiển thuộc vùng nào và tác động lên đối tượng nào. Dùng nhãn, vị trí, cách nhóm hoặc dấu phân cách phù hợp; không mặc định đóng khung mọi nhóm.
- **Tỷ lệ và cân bằng:** chọn tương quan kích thước theo nội dung, thao tác và trọng lượng thị giác của chữ, hình, màu và mật độ. Cân bằng có thể bất đối xứng trong giới hạn của loại màn. Tỷ lệ vàng, đối xứng, một phần ba hoặc hệ lưới là phương án khi hữu ích, nhưng không là công thức bảo đảm đẹp hay yêu cầu áp vào mọi thành phần. Kích thước theo vai trò của vị trí: vị trí quan trọng hơn thì lớn hơn; ô cùng vai trò giữ cùng kích thước dù có nội dung hay đang trống. Không đạt: ô trống co lại làm hàng lệch nhịp; ô phụ to hơn ô chính chỉ vì đang có nội dung.
- **Nhịp và nhất quán:** thành phần cùng vai trò dùng cấu trúc, khoảng cách, kiểu biểu đạt và hành vi tương ứng. Tận dụng hệ có sẵn; biến thể hoặc ngoại lệ phải có lý do liên quan yêu cầu. Không ép nội dung khác vai trò giống nhau. Trong một cột hoặc danh sách cùng vai trò, khoảng giữa các hàng đều nhau; đường kẻ phân hàng (nếu có) nằm giữa khoảng đó. Không đạt: đường kẻ dính sát hàng trên; khoảng giữa các hàng lệch nhau không theo nhóm.

Khi các lựa chọn thiết kế xung đột, ưu tiên: khả năng sử dụng; ý nghĩa và thứ bậc; nhóm và quan hệ căn; tỷ lệ và nhịp; trang trí. Thứ tự này không cho phép bỏ qua yêu cầu trực tiếp hoặc ràng buộc dự án.

## D. Đường gióng và quan hệ căn

Xác định các chuẩn cần thiết: mép vùng nội dung, trục của đối tượng chính hoặc mép panel. Từ đó thiết lập chuẩn nội bộ của từng nhóm và liên hệ với tổng thể. Ưu tiên dùng lại chuẩn phù hợp; không thêm đường gióng chỉ để có lưới dày hơn.

**Số mép căn chính:** liệt kê các mép trái nơi nhiều vùng hoặc nhóm của màn bắt đầu (với chữ viết phải sang trái, xét mép phải). Khi có hơn 3 mép, mỗi mép phải gắn với một vai trò nêu được, ví dụ mép điều hướng, mép nội dung, mép cột phụ; mép không gắn vai trò thì đưa về mép gần nhất có vai trò. Hai mép gần nhau nhưng không trùng và không có lý do (thụt lề để biểu đạt cấp, căn quang học) là lỗi gần thẳng hàng. Không đạt: tiêu đề, đoạn văn và nút trong cùng nhóm bắt đầu ở ba mép lệch nhau vài pixel.

**Trục trước khung:** cấu trúc của một nhóm hoặc cột đến từ trục căn chung (tiêu đề, hình, tên, thanh cùng một mép), không từ khung viền bao quanh. Khung chỉ thêm theo điều kiện ở C (Mật độ và vùng bao). Không đạt: các thành phần trong khung lệch mép nhau, khung được thêm để che sự lệch đó.

**Đường đáy chung:** khi các cột hoặc panel đặt cạnh nhau có lượng nội dung khác nhau, chọn một thành phần làm chuẩn đáy; mỗi cột kết thúc trên đường đó hoặc trên một hàng chung có chủ ý. Phân bổ chênh lệch vào khoảng giữa các hàng, giữ thứ tự khoảng cách ở C. Ngoại lệ: cột cuộn độc lập, hoặc nội dung dạng dòng chảy (bài viết, feed). Không đạt: cột ngắn dừng tùy ý; đáy hai cột cạnh nhau lệch vài pixel.

**Bảng và cặp nhãn–giá trị:** nhãn căn một mép đọc, số căn một mép chung theo cột (thường mép phải với chữ viết trái sang phải). Phần phụ của số (chênh lệch, phần cộng thêm) có vị trí riêng cạnh số chính; hàng không có phần phụ để trống vị trí đó, số chính không dịch. Không đạt: số tổng dịch sang trái ở hàng có phần cộng thêm.

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

Xét khả năng đọc và thao tác theo thiết bị, cách nhập và khoảng cách nhìn. Không làm chữ hoặc vùng thao tác khó dùng để giữ tỷ lệ. Với game, kiểm cả vùng gameplay cần quan sát và phần HUD có thể che khuất. Ngưỡng tối thiểu, trừ khi dự án cam kết mức cao hơn:

- **Vùng chạm:** tối thiểu 24×24 CSS px hoặc có khoảng cách tương đương với điều khiển lân cận (WCAG 2.2, 2.5.8). Ngưỡng cho cảm ứng ở `references/touch.md`.
- **Tương phản:** chữ thường 4,5:1; chữ lớn (từ 24px, hoặc từ 18,66px đậm) 3:1; thành phần UI và đồ họa cần nhận biết 3:1 (WCAG 1.4.3, 1.4.11). Skill chỉ quy định ngưỡng, không quy định chọn màu.
- **Không dựa riêng vào màu:** thông tin, trạng thái và lỗi phải có thêm chữ, hình, vị trí hoặc biểu tượng (WCAG 1.4.1).
- **Focus nhìn thấy:** điều khiển nhận focus bàn phím phải có dấu focus nhìn thấy (WCAG 2.4.7).

**Điểm đổi bố cục:** kế thừa breakpoint của dự án nếu còn đáp ứng nội dung và thao tác. Chỉ thêm hoặc đổi khi xuất hiện một trong các điều kiện: nội dung chồng hoặc bị cắt; quan hệ nhãn–giá trị mất rõ; điều khiển thiết yếu không còn dùng được. Dự án chưa có breakpoint thì đặt điểm đổi tại nơi nội dung bắt đầu hỏng, không theo danh sách thiết bị. Không suy phương thức nhập từ chiều rộng; quy tắc theo cách nhập ở file nền tảng (B). Màn hẹp là một bố cục sắp lại theo thứ tự ưu tiên, không phải bản rộng thu nhỏ. Khi đổi số cột, chuyển hàng hoặc vị trí, giữ vai trò, nhóm, thứ tự ưu tiên và đường đọc. Không thu nhỏ cả UI để giữ nguyên bố cục; không ép responsive cho đầu ra chỉ có một khổ cố định.

**Nội dung và trạng thái biến đổi:** với vùng có nội dung hoặc trạng thái biến đổi trong chức năng hiện có, chọn các ca có thể làm đổi bố cục: chữ dài (bản dịch, tên dài), số mục 0/1/nhiều, rỗng, đang tải, lỗi, dữ liệu một phần, thêm/xóa/đổi thứ tự. Với mỗi ca, giữ rõ nhóm, phạm vi điều khiển, điểm căn và đối tượng đang chọn. Vùng giữ kích thước dự kiến khi chuyển giữa đang tải và có dữ liệu; nội dung xuất hiện hoặc biến mất không đẩy điều khiển khác vào chỗ người dùng sắp thao tác. Lỗi của một vùng hiển thị trong vùng đó, kèm đường xử lý theo luồng hiện có. Ngoại lệ: không bắt mọi UI có đủ trạng thái; không tự thêm retry, sắp xếp hoặc luồng mới; đổi vị trí có chủ đích theo tác vụ vẫn được phép. Không đạt: dữ liệu tải xong đẩy nút khác vào dưới con trỏ; xóa thẻ giữa làm công cụ còn lại trông như thuộc thẻ khác.

**Lớp nổi và vùng cuộn:** khi có vùng cuộn, thành phần cố định (fixed/sticky) hoặc lớp nổi (menu, popover, tooltip, modal, drawer), xác định vùng nào cuộn, vùng nào neo và lớp nào phủ lên lớp nào. Bắt buộc: lớp nổi không bị khung chứa cắt và hiện đủ nội dung hoặc cuộn được bên trong; phần neo không che điều khiển đang focus, điểm đang thao tác hoặc đường tiếp tục (WCAG 2.4.11); lớp chặn nền có đường đóng rõ; không tạo hai vùng cuộn lồng nhau cùng hướng khi không cần. Ngoại lệ: modal chủ đích chặn nền theo luồng hiện có vẫn hợp lệ; không bắt dùng portal hoặc API cụ thể. Không đạt: menu mở ở cuối panel bị cắt mất các mục dưới; thanh sticky che trường đang nhập.

**Định hướng khi chuyển:** khi tác vụ ảnh hưởng việc chuyển màn, mở panel, đổi chế độ hoặc bố cục, giữ dấu nhận diện và ngữ cảnh đủ rõ để người dùng nhận ra đang ở đâu, đang thao tác với đối tượng nào và đang ở chế độ nào. Giữ rõ đường tiếp tục hoặc quay lại theo luồng hiện có; không buộc vị trí thành phần phải cố định. Dùng tiêu đề, trạng thái, lựa chọn đang hoạt động hoặc dấu hiệu sẵn có khi phù hợp. Không tự thêm màn trung gian, bước xác nhận hoặc animation chỉ để biểu đạt chuyển tiếp.

Khi được giao triển khai, chuyển quan hệ thiết kế thành ràng buộc layout của công nghệ đang dùng, tận dụng component/token và quy ước dự án. Không tự thêm framework, dependency hoặc lớp trừu tượng.

## F. Kiểm tra và bàn giao

Kiểm các quan hệ và điều kiện sử dụng chịu ảnh hưởng bởi thay đổi, bằng công cụ và dữ liệu thực có. Kết hợp kiểm hình học với xem ở kích thước sử dụng thực tế khi có thể. Nếu không thể mở giao diện, thử thiết bị hoặc đo trực tiếp, nêu rõ giới hạn; không coi suy luận là kết quả đã thử.

Với vùng chịu ảnh hưởng, kiểm thành phần trong nhóm và nhóm trong tổng thể liên quan: kích thước, điểm nhấn, khoảng trống và điều khiển có còn làm rõ đối tượng chính và quan hệ giữa các phần không. Nếu thay đổi có chuyển màn, chế độ hoặc bố cục, kiểm lại dấu định hướng và phạm vi tác động của điều khiển. Chỉ mở rộng kiểm tra đến quan hệ trực tiếp bị ảnh hưởng, không biến sửa cục bộ thành rà toàn bộ giao diện hoặc luồng.

**Phép thử:** chọn phép thử theo phạm vi thay đổi.

| Phép thử     | Cách làm                                                                                      | Đạt khi                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Squint       | Làm mờ hoặc thu nhỏ ảnh màn đến khi không đọc được chữ                                        | Vẫn nhận ra vùng chính, vùng phụ và các nhóm lớn theo đúng thứ tự ưu tiên; điểm nhấn chính thấy đầu tiên |
| Skeleton     | Thay chữ bằng khối trơn                                                                       | Phân cấp và nhóm vẫn đọc được từ vị trí, kích thước và khoảng trống                           |
| 5 giây       | Nhìn màn khoảng 5 giây rồi trả lời                                                            | Nói được màn này là gì, đối tượng chính là gì và hành động tiếp theo ở đâu                    |
| Đường tác vụ | Đi qua một tác vụ đại diện bằng các cách nhập trong phạm vi yêu cầu (chuột, chạm, bàn phím)   | Focus theo trình tự công việc, luôn nhìn thấy; không bỏ sót thông tin cần để quyết định       |
| Mép và lớp   | Mở lớp nổi gần mép vùng chứa; cuộn qua vùng neo; xem hai phía mỗi điểm đổi bố cục liên quan    | Không cắt, không che, không chồng                                                             |

Ghi rõ phép thử nào đã chạy trên giao diện thật, phép nào chỉ suy luận từ code hoặc ảnh. Phép 5 giây do agent tự trả lời thì ghi là tự đánh giá, không phải thử với người dùng.

**Trước và sau:** khi sửa UI hiện có và mở được giao diện, ghi nhận vùng liên quan trước khi sửa bằng ảnh hoặc số đo phù hợp. So sau sửa với cùng kích thước xem, dữ liệu, trạng thái và vị trí cuộn khi các yếu tố này ảnh hưởng kết quả. Chỉ ra quan hệ đã thay đổi, quan hệ trực tiếp cần giữ và thao tác đã kiểm lại. Điều kiện không thể giữ giống nhau thì ghi rõ khác biệt và giới hạn so sánh. Không bắt thiết kế mới có ảnh trước. Không đạt: so ảnh trước ở desktop với ảnh sau ở mobile rồi kết luận bố cục tốt hơn.

**Review:** mỗi phát hiện ghi đủ các phần sau.

- **Vị trí:** thành phần hoặc vùng.
- **Chuẩn so sánh:** quy tắc của skill, `DESIGN.md`, WCAG hoặc thành phần cùng vai trò.
- **Quan sát → hệ quả → hướng sửa:** hướng sửa chỉ đưa khi đủ căn cứ.
- **Mức:** P0 chặn tác vụ, gây mất dữ liệu hoặc không truy cập được; P1 hoàn thành được nhưng dễ sai hoặc phải tìm trợ giúp; P2 làm chậm, gây nhầm tạm thời hoặc lệch hệ thống; P3 lệch thị giác không ảnh hưởng tác vụ.
- **Bằng chứng:** số đo thực, quan sát từ ảnh hoặc giả thuyết cần kiểm.

Sắp phát hiện từ P0. Thứ tự sửa đề xuất: P0; trạng thái thiếu; lệch hệ thống; không nhất quán thị giác. Ghi ngắn "Điều đang tốt" để phần đúng không bị phá khi sửa. Không gán điểm số tổng. Không bịa tọa độ, baseline hoặc kết quả thao tác. Có thể đo trong hệ tọa độ ảnh nếu ghi rõ là số đo ảnh, không phải đơn vị layout của sản phẩm.

Bàn giao theo tác vụ:

- **Thiết kế mới:** đưa phương án đủ để sử dụng hoặc triển khai và giải thích quyết định bố cục trọng yếu, gồm loại màn đã chọn.
- **Sửa cục bộ và tinh chỉnh:** nêu phần đã đổi, phép thử đã chạy, kết quả trước–sau và giới hạn còn lại.
- **Review:** đưa phát hiện theo định dạng trên; nếu chỉ được giao review thì không tự sửa.

Dùng bản đồ hoặc overlay đường gióng khi cần làm rõ quan hệ và có khả năng tạo. Không bắt mọi tác vụ sinh sơ đồ hoặc báo cáo dài. Khi được giao triển khai, phần giải thích không thay thế kết quả thực hiện.

Đối chiếu vùng được kiểm hoặc sửa với các quy tắc đã xác nhận trong `DESIGN.md`. Khi được phép ghi, cập nhật file nếu có quyết định mới đã duyệt hoặc quy tắc đã xác nhận còn thiếu; giữ nội dung không liên quan. Không đổi quy tắc để hợp thức hóa UI lệch chuẩn. Báo kết quả kiểm từng lần riêng, không biến `DESIGN.md` thành nhật ký kiểm tra.
