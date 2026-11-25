# Bảng lỗi và cách khắc phục · Nhiệm vụ C

20 ca lỗi nằm trong `docs/Ngay13_Lab13_De_bai_hoc_vien.docx`. Năm loại theo Google PAIR: **Do người dùng · Hệ thống · Ngữ cảnh · Giới hạn hệ thống · Ngầm**. Gắn nhãn theo nguyên nhân gốc, không theo chỗ cần sửa.

## Đối chiếu hai bộ nhãn

**Nhãn người 1:** P3 (họ tên: Vũ Đình Thắng) · **Nhãn người 2:** P4 (họ tên: Nguyễn Hữu Thịnh)

P3 và P4 gắn nhãn độc lập (8 phút, không trao đổi) rồi mới so. Hai bộ nhãn trùng cả 20 ca nên **Nhãn thống nhất** lấy theo nhãn chung. Quy trình: P3 commit bộ nhãn người 1 trước (commit `163a179`, PR #3); P4 gắn bộ nhãn người 2 vào phiếu nháp cá nhân trước khi đối chiếu (theo báo cáo cá nhân P4). P3 không dùng AI khi gắn nhãn.

|  Ca | Nhãn người 1      | Nhãn người 2      | Trùng? | Nhãn thống nhất   |
| --: | ----------------- | ----------------- | ------ | ----------------- |
|   1 | Do người dùng     | Do người dùng     | Có     | Do người dùng     |
|   2 | Hệ thống          | Hệ thống          | Có     | Hệ thống          |
|   3 | Ngữ cảnh          | Ngữ cảnh          | Có     | Ngữ cảnh          |
|   4 | Giới hạn hệ thống | Giới hạn hệ thống | Có     | Giới hạn hệ thống |
|   5 | Ngầm              | Ngầm              | Có     | Ngầm              |
|   6 | Do người dùng     | Do người dùng     | Có     | Do người dùng     |
|   7 | Hệ thống          | Hệ thống          | Có     | Hệ thống          |
|   8 | Hệ thống          | Hệ thống          | Có     | Hệ thống          |
|   9 | Do người dùng     | Do người dùng     | Có     | Do người dùng     |
|  10 | Ngữ cảnh          | Ngữ cảnh          | Có     | Ngữ cảnh          |
|  11 | Giới hạn hệ thống | Giới hạn hệ thống | Có     | Giới hạn hệ thống |
|  12 | Ngầm              | Ngầm              | Có     | Ngầm              |
|  13 | Giới hạn hệ thống | Giới hạn hệ thống | Có     | Giới hạn hệ thống |
|  14 | Do người dùng     | Do người dùng     | Có     | Do người dùng     |
|  15 | Hệ thống          | Hệ thống          | Có     | Hệ thống          |
|  16 | Ngữ cảnh          | Ngữ cảnh          | Có     | Ngữ cảnh          |
|  17 | Ngầm              | Ngầm              | Có     | Ngầm              |
|  18 | Ngữ cảnh          | Ngữ cảnh          | Có     | Ngữ cảnh          |
|  19 | Giới hạn hệ thống | Giới hạn hệ thống | Có     | Giới hạn hệ thống |
|  20 | Hệ thống          | Hệ thống          | Có     | Hệ thống          |

**Độ khớp của P3 với nhãn tham khảo:** 20/20 (100%).

**Đồng thuận giữa hai người gắn nhãn độc lập:** 20 / 20 = **100%** (đạt ngưỡng 80%).

## Quy tắc phân biệt cho các ca không trùng

Không có ca lệch: hai bộ nhãn trùng 20/20, nên không cần quy tắc phân biệt hay viết lại định nghĩa.

## Bảng khắc phục cho 5 ca, mỗi loại một ca

Ngưỡng và vai trò dưới đây là đề xuất cho pilot. `input_validation_failed`, `refund_ledger_write` và `order_lookup_completed` đã được đưa vào đặc tả event. [Danh sách event](chi_so.md#danh-sách-event)

|  Ca | Loại lỗi          | Phát hiện bằng gì                                                                                                                                                                          | Khắc phục thế nào                                                                                                                                                        | Ai phụ trách                     |
| --: | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------- |
|   1 | Do người dùng     | Hằng ngày, kiểm tra `input_validation_failed` với lý do `sai_dinh_dang_tai_khoan`. Ngưỡng theo dõi là **từ 1 yêu cầu/ngày**.                                                               | Kiểm tra định dạng theo ngân hàng thụ hưởng trước khi tạo lệnh hoàn. Nếu sai, chỉ rõ trường cần sửa để khách nhập lại.                                                   | Quản lý sản phẩm trợ lý hoàn phí |
|  20 | Hệ thống          | Theo dõi `refund_ledger_write` liên tục. Cảnh báo khi cùng một quyền hoàn phí có **từ 2 giao dịch thành công khác mã giao dịch**.                                                          | Dùng một khóa chống trùng cố định cho mỗi quyền hoàn phí và dùng lại khóa đó khi khách gửi lại yêu cầu hoặc hệ thống thử lại. Đối soát các giao dịch trùng đã phát sinh. | Kỹ sư trưởng tích hợp sổ cái     |
|  18 | Ngữ cảnh          | Hằng tuần, ghép `ticket_reopened` vì khách nghi hoàn thiếu với `audit_sample_checked` qua `request_id`. Rà soát nếu có **từ 1 ca** mở lại dù số tiền hoàn khớp đối soát.                   | Hiển thị phí ban đầu, tỷ lệ hoàn và số tiền cuối trong thông báo, chẳng hạn **30.000 đ × 50% = 15.000 đ**.                                                               | Trưởng nhóm CSKH                 |
|  19 | Giới hạn hệ thống | Hằng ngày, đếm `order_lookup_completed` có kết quả `ngoai_khoang_du_lieu`. Rà soát luồng chuyển tiếp khi có **từ 1 yêu cầu/ngày**.                                                         | Giải thích giới hạn tra cứu **12 tháng** và chuyển yêu cầu cho nhân viên kèm mã đơn và lý do. Nhân viên kiểm tra hồ sơ lưu trữ nếu có.                                   | Trưởng nhóm CSKH                 |
|  17 | Ngầm              | Hằng tuần, dùng `audit_sample_checked` để so tiền đã hoàn với số đúng theo bảng giá có hiệu lực ở mẫu đơn dưới 2 kg. Cảnh báo từ **1 ca sai lệch** và kiểm tra phiên bản bảng giá đã dùng. | Xóa bản giá cũ trong bộ nhớ đệm khi bảng giá mới có hiệu lực, ghi phiên bản đã dùng vào trace và đối soát các đơn bị ảnh hưởng.                                          | Kế toán trưởng                   |
