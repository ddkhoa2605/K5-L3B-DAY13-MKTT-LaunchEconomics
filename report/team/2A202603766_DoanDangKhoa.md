# Báo cáo cá nhân — DoanDangKhoa-2A202603766

## 1. Thông tin thành viên

- Họ tên: Đoàn Đăng Khoa
- MSSV: 2A202603766
- Email: 26ai.khoadd@vinuni.edu.vn
- Vai trong nhóm: **Người viết code** (P1) trước giải lao; **người kiểm số** sau giải lao

## 2. Phần việc phụ trách

- **Nhiệm vụ A (CP1):** ba hàm A1, hàm `mo_hinh`, bảng A2 và A3 trong `src/lab13.py`.
- **Nhiệm vụ B (CP2):** bảng độ nhạy B1 (9 kịch bản), B2 (cặp và xếp hạng), B3 (giới hạn chạy lại, chi phí cả hệ thống), B4 (xem lại 100%).
- **Sau giải lao, kiểm số:** kiểm lại từng bước năm câu D1 để đối chiếu với code của P2.
- **E2 (rủi ro kinh tế):** soạn ba dòng E2 từ số B1, B4, A4 (PR #5, đã đóng vì chỉ dùng để đóng góp ý kiến cho Thịnh (P4); nhóm dùng bản E2 trong PR #6).
- **Phối hợp:** bàn giao số A, B cho P4 điền `bang_chi_phi.md`; review và merge PR #2 của P2.

## 3. Đóng góp cụ thể

**A1 — Ba phép thử đáp án biết trước.** Viết `so_lan_chay_ky_vong`, `ti_le_thanh_cong`, `he_so_chi_phi_moi_viec_thanh_cong`. Với p = 0,8: tối đa 2 lần → 1,20; chạy đến khi đúng → 1,25; hệ số chi phí tối đa 3 lần → 1,25. Chương trình in "Ba phép thử đáp án biết trước: ĐẠT".

**A2 — `mo_hinh(runs, reqs, ...)`.** Tử số cộng token và tool của **mọi lần chạy** kể cả lần lỗi, cộng tiền xem lại và làm lại (phút `_simulated` × 2.000 đ); mẫu số chỉ đếm yêu cầu có `ket_qua == 'thanh_cong'`. Hàm nhận sẵn tham số giá, hệ số và `max_lan_chay` để B gọi lại. Kết quả (xem lại, làm lại, tổng, cps là **simulated**):

| Khoản | Giá trị |
| --- | ---: |
| Token | 245.585 đ (đo từ trace) |
| Tool | 84.000 đ (đo từ trace) |
| Lần chạy thứ 2 và 3 | 93.804 đ (đo từ trace) |
| Xem lại | 1.780.000 đ (simulated) |
| Làm lại | 2.264.000 đ (simulated) |
| Tổng | 4.373.585 đ |
| Việc thành công | 978 |
| Chi phí mỗi việc thành công | 4.472 đ (simulated), gấp 16,3× hoá đơn token và tool chia số yêu cầu (274,7 đ) |

Khoản lớn nhất là làm lại (51,8%), rồi xem lại (40,7%) [simulated]. So với nhân viên tự làm 12.000 đ, tính cả phần nhân viên làm thay 222 ca: 5.865 đ mỗi yêu cầu = 0,49× [simulated].

**A3 — Tách theo loại.** noi_dia 2.696 đ (0,22×), hang_nang 8.221 đ (0,69×), quoc_te 22.515 đ (1,88×), doi_tac 10.215 đ (0,85×) [simulated]. Tỉ lệ ok theo lần thử của quoc_te giảm 30,0% → 11,4% → 2,2%, nên chạy lại chỉ tốn thêm tiền.

**B1–B4.**
- B1: giá token ×2 → +5,6%; ÷2 → −2,8%; xem lại ×2 → +40,7%; ÷2 → −20,3%; làm lại ×2 → +51,8%; ÷2 → −25,9%; lương +25% → +23,1%; tối đa 2 lần → −5,2%; 1 lần → −8,1% [simulated].
- B2: giá token ×2 cùng xem lại ×2 = 6.543 đ (+46,3%), bằng tổng hai tác động riêng vì mô hình cộng tuyến tính [simulated]. Xếp hạng: 1. làm lại, 2. xem lại, 3. lương.
- B3: chi phí cả hệ thống 1/2/3 lần = 7.449.781 / **6.901.220** / 7.037.585 đ. Giới hạn 2 lần rẻ nhất cho công ty, khác giới hạn cho cps thấp nhất (1 lần) [simulated].
- B4: xem lại 100% (noi_dia + hang_nang) = 11.743 đ (0,98×) với 9 phút làm lại; 12.415 đ (1,03×) với 15,3 phút làm lại thật trong dữ liệu. Hoà vốn nếu mỗi lần xem lại ≤ 5,1 phút (hoặc ≤ 4,8 phút) [simulated].

**Kiểm số D1** (tính lại từng bước, đối chiếu với code của P2; baseline 0,70, α 0,05, power 0,8, ICC 0,02, z = 1,95996 và 0,84162):

- a) p̄ = 0,725; số hạng 1 = 1,95996 × √(2 × 0,725 × 0,275) = 1,2377; số hạng 2 = 0,84162 × √(0,21 + 0,1875) = 0,5306; n = (1,7683)² / 0,05² = 1.250,7 → **1.251** mỗi nhóm.
- b) DE = 1 + 74 × 0,02 = 2,48; n = 1.251 × 2,48 = 3.102,5 → **3.103**; 3.103 / 75 = 41,4 → 42 người mỗi nhóm, tổng 84 > 40: không đủ người.
- c) 20 / 0,02 = **1.000** < 1.251: không đạt mức chênh 5 điểm.
- d) 6 / 0,02 = **300**; chỉ 6 cụm < 20: loại.
- e) Mức chênh 6 điểm: p̄ = 0,73; n = (1,2306 + 0,5272)² / 0,06² = 858,3 → **859**; giải 20m / (1 + (m − 1) × 0,02) ≥ 859 → m ≥ 859 × 0,98 / (20 − 859 × 0,02) = 298,5 → **m ≥ 299**, DE = 6,96; kiểm: 20 × 299 / 6,96 = 859,2 ≥ 859.

Cả 5 câu khớp code của P2 và bảng đối chiếu. Lệch duy nhất là ở câu b nếu dùng n chưa làm tròn (3.101,8), nhỏ hơn 0,1%, trong sai số 2%.

## 4. Bằng chứng

- PR #1 (đã merge): https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/1 · nhánh `P1`, commit `ffc82f5`: "feat(lab13): implement A1 tests, mo_hinh, A3 per-type and B sensitivity tables".
- PR #5 (E2, đã đóng): https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/5 · PR #8 (báo cáo cá nhân, đã merge): https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/8.
- File `src/lab13.py`: các hàm `so_lan_chay_ky_vong`, `ti_le_thanh_cong`, `he_so_chi_phi_moi_viec_thanh_cong`, `mo_hinh`, `tinh_he_thong`, `bang_a2`, `bang_a3`, `bang_b1`, `bang_b3`, `bang_b4`.
- Cách chạy: `cd src && python lab13.py` (nếu pipe ra file thì đặt `PYTHONIOENCODING=utf-8`).

## 5. Công cụ AI đã dùng

- **Claude Code** (trợ lý AI trong terminal): hỗ trợ hướng dẫn viết code `lab13.py` (A1, `mo_hinh`, A3, B). Soạn nháp báo cáo này.
  
- **Cách tự kiểm tra:**
  - Ba phép thử A1 phải in ĐẠT (1,20 · 1,25 · 1,25) trước khi dùng `mo_hinh`.
  - So kết quả A2, A3, B với bảng đối chiếu trong `docs/Lab13_Huong_dan_chi_tiet_buoi_chieu.md` (chấp nhận lệch ≤ 2%).
  - Kiểm tính nhất quán: mỗi kịch bản "giảm một nửa" bằng đúng nửa mức tăng của "gấp đôi" (5,6 → 2,8; 40,7 → 20,3).
  - Đối chiếu số trong code với đề: B4 dùng phút làm lại trung bình trên cả 74 ca `lam_lai` (15,3), không chỉ 48 ca trong phạm vi (16,25) như lần chạy đầu; đã sửa theo hướng dẫn.
  - D1: tính lại từng bước (z, p̄, n, DE, m) và đối chiếu với output của P2 (1.251 · 3.103 · 1.000 · 300 · m ≥ 299); khớp trong sai số 2%.
- Không dùng AI để bịa số hay nhãn; mọi con số do `lab13.py` tính ra hoặc có cách tính ghi trong báo cáo.

## 6. Tự đánh giá

- Làm tốt: phần A và B khớp đáp án, ba phép thử A1 đạt, số simulated được ghi nhãn rõ.
- Bài học: tử số của chi phí mỗi việc thành công phải tính mọi lần chạy kể cả lần lỗi, còn mẫu số chỉ đếm việc thành công; tối ưu cps (giới hạn 1 lần) khác với tối ưu chi phí cả hệ thống (giới hạn 2 lần).
