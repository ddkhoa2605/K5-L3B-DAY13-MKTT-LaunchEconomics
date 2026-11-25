# Báo cáo nhóm

Báo cáo ngắn, tối đa 2 trang. Số liệu chi tiết nằm trong các file hồ sơ; ở đây chỉ dẫn lại con số chính.

## 1. Thông tin nhóm

- Tên nhóm: MKTT
- Lớp: L3B
- Thành viên: [Thông tin nhóm](../../TEAM.md)

## 2. Mục tiêu và cách tiếp cận

Nhóm đánh giá chi phí, mức độ sử dụng và an toàn của trợ lý hoàn phí LogiX-VN để chuẩn bị đề xuất pilot cho Gate 2a. Nhóm dùng dữ liệu chạy thử giả lập gồm **1.200 yêu cầu và 1.624 lượt chạy**, phân tích chi phí theo loại yêu cầu, rồi dùng bảng độ nhạy và bảng lỗi để xác định các điều kiện cần kiểm tra trong pilot. [Dữ liệu và công thức](../../docs/du_lieu_va_cong_thuc.md)

## 3. Giải pháp

- **A · Chi phí:** Cộng chi phí token và tool với chi phí lao động quy đổi từ phút xem lại và làm lại. Chia tổng chi phí cho số yêu cầu thành công, rồi tính riêng theo loại yêu cầu. [Bảng chi phí](bang_chi_phi.md#a2--mô-hình-chi-phí-từ-trace)
- **B · Độ nhạy:** Thay đổi từng yếu tố chi phí, so ba giới hạn chạy và kiểm tra kịch bản xem lại 100%. [Bảng độ nhạy](bang_chi_phi.md#b1--đổi-từng-yếu-tố)
- **C · Lỗi:** P3 và P4 gắn nhãn độc lập 20 ca, đồng thuận **20/20 (100%)**, rồi đề xuất cách phát hiện, khắc phục cho một ca ở mỗi loại lỗi. [Bảng lỗi](bang_loi.md)
- **D · Pilot:** Bản kế hoạch chia ngẫu nhiên theo nhân viên với đối chứng đồng thời. Mỗi nhóm có **20 nhân viên**, cần ít nhất **5.980 yêu cầu thực tế**, tương ứng **859 quan sát hiệu dụng** cho mức chênh **6 điểm phần trăm**. [Kế hoạch pilot](pilot_plan.yaml) · [PR #3](https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/3/files)
- **E · Đo lường:** Tính thử ba chỉ số, đề xuất hai chỉ số bổ sung, lập danh sách event và hành động cho hai rủi ro kinh tế. [Đặc tả chỉ số và rủi ro](chi_so.md)

## 4. Kết quả

- Chi phí toàn mẫu là **4.472 đ/việc thành công `simulated`**. Chi phí biến đổi cả hệ thống là **5.865 đ/yêu cầu `simulated`**, bằng **0,49×** mốc nhân viên tự làm. Nếu xem lại 100% trong phạm vi nội địa và hàng nặng, chi phí có thể lên tới **12.415 đ/việc thành công `simulated`**. [Bảng chi phí](bang_chi_phi.md)
- Trong đợt chạy thử, **82,83% (994/1.200)** yêu cầu đóng trong 24 giờ và không mở lại trong 7 ngày, **27,12% (48/177)** yêu cầu đã xem lại có gợi ý bị sửa hoặc bỏ, và **4,25% (51/1.200)** yêu cầu mở lại trong 7 ngày. [Đặc tả chỉ số](chi_so.md)
- Hồ sơ đề xuất **Go có điều kiện** cho nội địa và hàng nặng. Các điều kiện là kiểm thử chống hoàn tiền trùng, xác nhận đủ mẫu và kiểm tra an toàn trước khi giảm xem lại. Nhóm đã chấm hồ sơ của nhóm khác trong [phiếu chấm duyệt chéo](phieu_cham.md). [Hồ sơ launch](ho_so_launch_v0.md)

## 5. Khó khăn và cách xử lý

`main` local còn dùng khung Python khi GitHub đã có code của P1 và P2. Sau khi cập nhật đến `db0e54d` và cài thư viện vào môi trường ảo, `lab13.py` chạy hết và cả ba phép thử A1 đều đạt. Kế hoạch pilot đọc được bằng `yaml.safe_load`. Báo cáo ghi rõ mẫu số và phạm vi cho từng số chi phí. [Mã nguồn](../../src/lab13.py) · [Bảng chi phí](bang_chi_phi.md) · [Kế hoạch pilot](pilot_plan.yaml)

## 6. Tổng hợp đóng góp

P1 triển khai mô hình chi phí và độ nhạy. P2 đối chiếu số và bổ sung tính toán A4, D1, E1. P3 ghi nhãn người 1 và soạn kế hoạch pilot. P4 tổng hợp bảng chi phí, bảng lỗi, chỉ số, rủi ro và hồ sơ launch. [Thông tin nhóm](../../TEAM.md) · [Báo cáo cá nhân P4](2A202603726_NguyenHuuThinh.md)

## 7. Hạn chế và hướng cải thiện

Dữ liệu chạy thử là giả lập và thiếu đối chứng đồng thời, nên các tỷ lệ quan sát chỉ mô tả mẫu. Trong pilot, nhóm cần đo phút xem lại và làm lại thực tế, theo dõi mở lại đủ bảy ngày và ghi nhận hoàn tiền trùng. Thiết kế có power khoảng **64%** nếu tác động thực là **5 điểm phần trăm**. Bảng lỗi mới dựa trên 20 ca; khi pilot có ca thật cần gắn nhãn lại và kiểm tra định nghĩa năm loại lỗi. [Chỉ số và event](chi_so.md) · [Kế hoạch pilot](pilot_plan.yaml) · [Bảng lỗi](bang_loi.md)

## 8. Tài liệu tham khảo

- [Đề bài và yêu cầu của Lab 13](../../README.md)
- [Dữ liệu và công thức](../../docs/du_lieu_va_cong_thuc.md)
- [Hướng dẫn chi tiết của lab](../../docs/Lab13_Huong_dan_chi_tiet_buoi_chieu.md)
