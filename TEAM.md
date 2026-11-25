# Team

## Thông tin nhóm

- Tên nhóm: MKTT
- Lớp: L3B
- Repo nhóm: `K5-L3B-DAY13-MKTT-LaunchEconomics` (xem [SUBMISSION.md](SUBMISSION.md))
- URL repo, nhánh nộp, commit chốt: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics · nhánh `main` · commit chốt: ...

## Thành viên

| STT | Họ tên | MSSV | Email | GitHub | Vai trò |
| --: | ------ | ---- | ----- | ------ | ------- |
|   1 | Đoàn Đăng Khoa | 2A202603766 | 26ai.khoadd@vinuni.edu.vn | ddkhoa2605 | P1 · Người viết code (trước giải lao), người kiểm số (sau giải lao) |
|   2 | Nguyễn Văn Minh | 2A202603771 | 26ai.minhnv7@vinuni.edu.vn | vminh21 | P2 · Người kiểm số (trước giải lao), người viết code (sau giải lao) |
|   3 | Vũ Đình Thắng | 2A202603753 | 26ai.thangvd2@vinuni.edu.vn | ThangVu2303 | P3 · Người gắn nhãn 1 |
|   4 | Nguyễn Hữu Thịnh | 2A202603726 | 26ai.thinhnh2@vinuni.edu.vn | huuthinh812 | P4 · Người gắn nhãn 2, kiêm giữ hồ sơ |

Bốn vai của lab:

- **Người viết code:** viết và chạy `src/lab13.py`.
- **Người kiểm số:** tính tay một con số để đối chiếu, điền bảng.
- **Người gắn nhãn 1:** đọc đề, theo dõi điều kiện "Xong khi"; gắn nhãn 20 ca độc lập ở CP3.
- **Người gắn nhãn 2, kiêm giữ hồ sơ:** điền `report/team/ho_so_launch_v0.md` từ đầu buổi; gắn nhãn 20 ca độc lập ở CP3.

Đổi người viết code sau giờ giải lao, để ít nhất hai người trong nhóm tự tay tính được chi phí.

## Cá nhân

Mỗi thành viên đồng thời tạo một báo cáo riêng trong `report/` theo dạng:

```text
report/team/MSSV_HoTen.md
```

Ví dụ: `report/team/20241234_NguyenVanAn.md`.

Đóng góp của từng thành viên (bằng chứng là PR trên repo nhóm):

## DoanDangKhoa-2A202603766

### Phần việc phụ trách

- Nhiệm vụ A (A1–A3) và B (B1–B4) trong `src/lab13.py`; E2 rủi ro kinh tế.

### Đóng góp cụ thể

- Viết ba hàm A1 (ba phép thử ĐẠT), `mo_hinh`, bảng A2, A3 theo loại, B1 chín kịch bản, B2, B3 giới hạn số lần chạy, B4 xem lại 100%.
- Soạn ba dòng rủi ro kinh tế E2 (PR #5, đã đóng; nhóm dùng bản E2 trong PR #6).

### Bằng chứng

- PR #1: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/1 · PR #5: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/5

## NguyenVanMinh-2A202603771

### Phần việc phụ trách

- Kiểm số nhiệm vụ A, B; viết A4, D1, tỉ lệ mở lại và E1 trong `src/lab13.py`; review PR #3, #6.

### Đóng góp cụ thể

- Kiểm tay A2 độc lập với code (4.373.585 đ; 4.472 đ/việc thành công `simulated`), tính A4 (4.599 đ = 0,38×; 5.784 đ = 0,48× `simulated`), so cả hệ thống 0,49×.
- Viết D1 (1.251 · 3.103 · 1.000 · 300 · m ≥ 299, DE 6,96, power 0,64), tỉ lệ mở lại 4,25% / 3,97%, E1 (82,83% · 27,12% · 4,25%).

### Bằng chứng

- PR #2: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/2 · PR #4 (báo cáo cá nhân): https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/4 · [Báo cáo cá nhân](report/team/2A202603771_NguyenVanMinh.md)

## VuDinhThang-2A202603753

### Phần việc phụ trách

- Nhiệm vụ C (gắn nhãn người 1) và nhiệm vụ D (`pilot_plan.yaml`).

### Đóng góp cụ thể

- Gắn nhãn độc lập 20 ca lỗi theo năm loại Google PAIR.
- Viết `pilot_plan.yaml`: D1, D2, đánh đổi mức chênh 6 điểm, ba luật dừng NẾU – TRONG – THÌ – KHÔNG THÌ, rollback, ngày quyết định, `simulated_inputs`; sửa theo review.

### Bằng chứng

- PR #3: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/3 · [Báo cáo cá nhân](report/team/2A202603753_VuDinhThang.md)

## NguyenHuuThinh-2A202603726

### Phần việc phụ trách

- Nhiệm vụ C (gắn nhãn người 2, bảng khắc phục), nhiệm vụ E và hồ sơ launch v0; tổng hợp các file trong `report/team/`.

### Đóng góp cụ thể

- Điền `bang_chi_phi.md` (A1–A4, B1–B4) từ số P1, P2 bàn giao; bảng khắc phục 5 ca; `chi_so.md` (E1, 11 event có `trace_id`, E2); `ho_so_launch_v0.md` (bảy mục, đề xuất Go có điều kiện); `group_report.md`.

### Bằng chứng

- PR #6: https://github.com/ddkhoa2605/K5-L3B-DAY13-MKTT-LaunchEconomics/pull/6 · [Báo cáo cá nhân](report/team/2A202603726_NguyenHuuThinh.md)

