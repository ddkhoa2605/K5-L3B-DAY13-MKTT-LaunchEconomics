# Báo cáo cá nhân — VuDinhThang-2A202603753

## 1. Thông tin thành viên

- Họ tên: Vũ Đình Thắng
- MSSV: 2A202603753
- Email: 26ai.thangvd2@vinuni.edu.vn
- Vai trong nhóm: **P3** · người gắn nhãn 1, phụ trách kế hoạch pilot (nhiệm vụ D)

## 2. Phần việc phụ trách

- **Nhiệm vụ C:** gắn nhãn độc lập 20 ca lỗi theo năm loại Google PAIR (cột "Nhãn người 1" trong `bang_loi.md`), so nhãn với P4 và soát bảng khắc phục 5 ca.
- **Nhiệm vụ D:** viết `report/team/pilot_plan.yaml`, gồm chú thích D1 và D2, cách chia, cỡ mẫu, khả năng tách tác động, luật dừng, rollback, ngày quyết định và `simulated_inputs`.
- Nhận số từ P1 (A3, B3, B4) và P2 (D1, tỉ lệ mở lại, E1) để đặt phạm vi và ngưỡng cho pilot.

## 3. Đóng góp cụ thể

- **Gắn nhãn 20 ca (C).** Gắn theo nguyên nhân gốc, không theo chỗ cần sửa. Phân bố nhãn: Do người dùng 4 · Hệ thống 5 · Ngữ cảnh 4 · Giới hạn hệ thống 4 · Ngầm 3. Tôi commit bộ nhãn trước, để trống cột người 2 và tỉ lệ đồng thuận cho đến khi so với P4. Hai bộ nhãn trùng **20/20 (100%)**, trên ngưỡng 80%.
- **Phạm vi pilot.** Chỉ đưa `noi_dia` (2.696 đ = 0,22×) và `hang_nang` (8.221 đ = 0,69×) vào pilot. Loại `quoc_te` (22.515 đ = 1,88×) và `doi_tac` (10.215 đ = 0,85×, biên quá mỏng). Các số đều `simulated`, lấy từ A3.
- **Cách chia và cỡ mẫu (D1).** Chọn chia ngẫu nhiên theo nhân viên, 20 + 20 người. Không chia theo depot, vì 6 depot mỗi nhóm chỉ cho n hiệu dụng tối đa 300 và ít hơn 20 cụm. Không đủ người cho mức chênh 5 điểm (cần 84 > 40 người) nên chấp nhận MDE **6 điểm**: n = **859** mỗi nhóm, DE **6,96**, cần **≥ 299 yêu cầu/người**, tức 5.980 yêu cầu thực tế mỗi nhóm. Tôi ghi rõ đánh đổi: nếu tác động thật chỉ 5 điểm thì power còn khoảng **0,64**.
- **Tách được tác động (D2).** Viết 5 câu: đối chứng chạy cùng tuần và cùng depot; bốc thăm 40 `staff_id` bằng code (seed 2026, phân tầng theo depot); giảm ảnh hưởng gián tiếp bằng cách chỉ cho tài khoản nhóm trợ lý dùng trợ lý và kiểm hằng tuần rằng lượt gọi từ đối chứng bằng 0; chốt chỉ số, ngưỡng và ngày quyết định (12/01/2027) trước khi bắt đầu; đủ 20 cụm mỗi nhóm.
- **Ba luật dừng NẾU – TRONG – THÌ – KHÔNG THÌ:**
  - **An toàn:** so tỉ lệ mở lại 7 ngày với đối chứng (+2 điểm) kèm trần 6%, và dừng ngay từ 1 ca hoàn tiền trùng. Tôi không dùng ngưỡng tuyệt đối 3%, vì mức hiện tại trong phạm vi đã là **3,97%** (`simulated`), nên ngưỡng 3% sẽ dừng oan ngay tuần đầu.
  - **Chi phí:** dừng khi cps vượt **6.000 đ** trong 2 tuần liên tiếp, tức tăng 76% so với 3.414 đ và vượt kịch bản xấu nhất của B1 (+51,8%). Hành động lấy từ B3 (giới hạn 2 lần chạy) và A3 (thu hẹp về `noi_dia`).
  - **Mức độ sử dụng:** dừng khi tỉ lệ bỏ qua gợi ý vượt **40%** trong 1 tuần, so với mức hiện tại 27,12%.

  Mỗi luật có một vai trò có quyền dừng và một thời hạn.
- **Sửa theo review của P2 (commit `e5195a7`):**
  - Ghi đúng 15,3 là phút **làm lại** mỗi ca, không phải phút xem lại.
  - Bỏ khoản "chạy lại" khỏi công thức của luật dừng chi phí, vì khoản này đã nằm trong token + tool, để tránh đếm hai lần.
  - Ghi rõ ngưỡng 6.000 đ chưa gồm chi phí cố định.

## 4. Bằng chứng

- PR #3: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/3
- Commit `163a179`: gắn nhãn người 1 cho 20 ca, kèm bản đầu `pilot_plan.yaml`.
- Commit `e5195a7`: sửa `pilot_plan.yaml` và `bang_loi.md` theo review của P2.
- [pilot_plan.yaml](pilot_plan.yaml) đọc được bằng `yaml.safe_load`, không còn dấu `?` ngoài dòng chú thích, có 3 luật dừng.
- [bang_loi.md](bang_loi.md): cột "Nhãn người 1", đồng thuận 20/20.

## 5. Công cụ AI đã dùng

- **Claude Code:** dùng để đọc đề và lập kế hoạch phân công cho nhóm, rà các điều kiện "Xong khi", hỗ trợ viết chú thích và cấu trúc `pilot_plan.yaml`, và sửa file theo nhận xét review của P2. Phần gắn nhãn 20 ca tôi tự làm, không dùng AI, để giữ tính độc lập với P4.
- **Cách tự kiểm tra:**
  - Chạy `python -c "import yaml; yaml.safe_load(open('../report/team/pilot_plan.yaml', encoding='utf-8'))"` để chắc file đọc được, và tìm dấu `?` ngoài dòng chú thích.
  - So mọi con số trong yaml (859, DE 6,96, m ≥ 299, power 0,64, 3,97%, 27,12%) với output `python lab13.py` của P2.
  - Tự giải lại câu D1e: 20m ≥ 859 × (0,98 + 0,02m) → m ≥ 298,5 → **299**.
  - Đọc lại từng luật dừng để chắc có đủ bốn vế, có ngưỡng, có thời hạn và chỉ một vai trò có quyền dừng.

## 6. Tự đánh giá

- Đã hoàn thành phần việc của P3: bộ nhãn người 1 và kế hoạch pilot đủ trường, các con số khớp kết quả của P2.
- Hiểu được:
  - Khi chia theo cụm, số cụm quyết định cỡ mẫu hiệu dụng. Vì vậy chia theo depot không dùng được, dù số yêu cầu rất lớn.
  - Ngưỡng an toàn phải đặt dựa trên mức đang quan sát được, nếu không pilot sẽ dừng oan.
- Cần cải thiện:
  - Lần đầu tôi để sai đơn vị (15,3 phút) và đếm trùng khoản chạy lại trong luật dừng; lỗi chỉ được phát hiện khi P2 review. Lần sau tôi sẽ đối chiếu từng con số trong chú thích với dòng output tương ứng của `lab13.py` trước khi mở PR.
  - Nên gửi bản nháp luật dừng cho P4 sớm hơn để hồ sơ launch và `chi_so.md` dùng cùng ngưỡng ngay từ đầu.
