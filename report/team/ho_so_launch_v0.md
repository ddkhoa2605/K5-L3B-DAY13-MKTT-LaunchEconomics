# Hồ sơ launch v0 · Trợ lý hoàn phí LogiX-VN · Gate 2a

Nhóm: MKTT · Lớp: L3B. Phân công và điều kiện pilot dưới đây là đề xuất để nhóm xác nhận trước Gate 2a.

| Mục | Con số chính | Trạng thái | Người phụ trách |
| --- | --- | --- | --- |
| 1 · Chi phí mỗi việc thành công | **4.472 đ/việc thành công `simulated`** trên toàn mẫu, với **978/1.200** yêu cầu thành công. | Giả lập | Quản lý sản phẩm trợ lý hoàn phí |
| 2 · Ba yếu tố nhạy nhất | Làm lại **+51,8%**, xem lại **+40,7%**, lương **+23,1% `simulated`** theo các kịch bản tăng ở B1. | Giả lập | Quản lý sản phẩm trợ lý hoàn phí |
| 3 · So với nhân viên tự làm | Chi phí biến đổi cả hệ thống trên toàn mẫu là **5.865 đ/yêu cầu**, bằng **0,49×** mốc **12.000 đ/yêu cầu `simulated`**, tính theo B3 với **222 yêu cầu không thành công**. | Giả lập | Quản lý sản phẩm trợ lý hoàn phí |
| 4 · Chỉ số chính, chỉ số dùng, chỉ số an toàn | Trong đợt chạy thử, đóng trong 24 giờ và không mở lại trong 7 ngày **82,83% (994/1.200)**, sửa hoặc bỏ gợi ý **27,12% (48/177)**, mở lại trong 7 ngày **4,25% (51/1.200)**. | Xong, có bằng chứng | Trưởng nhóm CSKH |
| 5 · Bảng lỗi và cách khắc phục | Có đề xuất cho **5 ca thuộc 5 loại lỗi**. Ca 20 dùng khóa chống trùng theo quyền hoàn phí. Hai người gắn nhãn độc lập đồng thuận **20/20 (100%)**. [Bảng lỗi](bang_loi.md) | Xong, có bằng chứng | Kỹ sư trưởng tích hợp sổ cái |
| 6 · Pilot plan | Đề xuất `noi_dia` và `hang_nang`, **20 nhân viên mỗi nhóm**. MDE **6 điểm phần trăm**, cần **859 quan sát hiệu dụng** và ít nhất **5.980 yêu cầu thực tế mỗi nhóm**. Cỡ mẫu hiệu dụng tối đa của cách chia này là **1.000** (20 / ICC 0,02), thấp hơn **1.251** cần cho mức chênh 5 điểm; nếu tác động thật chỉ là 5 điểm thì power còn khoảng **0,64** (khoảng 36% khả năng bỏ sót). Dừng từ **1 ca hoàn trùng**. Chốt dự kiến **12/01/2027** khi đủ theo dõi. [Kế hoạch pilot](pilot_plan.yaml) | Chưa | Giám đốc vận hành LogiX-VN |
| 7 · Rủi ro kinh tế | Khi xem lại 100% trong phạm vi `noi_dia` và `hang_nang`, chi phí là **11.743–12.415 đ/việc thành công `simulated`**, tuỳ thời gian làm lại. [Rủi ro và hành động](chi_so.md#e2--rủi-ro-kinh-tế) | Giả lập | Quản lý sản phẩm trợ lý hoàn phí |

**Đề xuất Gate 2a — Go có điều kiện** cho `noi_dia` và `hang_nang`. Hai loại có chi phí **2.696 đ** và **8.221 đ/việc thành công `simulated`**. Loại `quoc_te` (**22.515 đ = 1,88×**, thành công 27,3%) và `doi_tac` (**10.215 đ = 0,85×**, thành công 54,4%) nằm ngoài phạm vi (các số chi phí và tỉ lệ thành công của hai loại này đều là `simulated`). Kịch bản xem lại 100% có thể lên **12.415 đ/việc thành công `simulated`**. [Bảng chi phí](bang_chi_phi.md)

- **06/12/2026 · Kỹ sư trưởng tích hợp sổ cái:** Kiểm thử khóa chống trùng và xác nhận event `refund_ledger_write` phát hiện giao dịch trùng.
- **06/12/2026 · Giám đốc vận hành LogiX-VN:** Ký chấp nhận mức chênh **6 điểm phần trăm** và mức power khoảng **0,64** nếu tác động thật là 5 điểm; xác nhận đủ **20 nhân viên mỗi nhóm** và khả năng thu ít nhất **5.980 yêu cầu mỗi nhóm** trong kỳ đo.
- **21/12/2026 · Trưởng nhóm CSKH:** Kiểm tra phút xem lại và tỷ lệ mở lại của hai nhóm. Giảm mức xem lại khi có đủ bảy ngày theo dõi và đạt ngưỡng an toàn trong kế hoạch pilot.
