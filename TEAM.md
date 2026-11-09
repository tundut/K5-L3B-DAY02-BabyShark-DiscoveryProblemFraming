# Team

> Điền file này trên repo chung do nhóm trưởng fork. Nhóm điền phần **Thông tin nhóm** và **Thành viên**. Mỗi người tự điền phần của mình trong **Cá nhân**. Không copy file này sang repo khác.

## Thông tin nhóm

- Tên nhóm: BabyShark
- Candidate problem nhóm chọn (1 câu): Khi xe thuê bị hỏng đã báo lỗi, sự cố không rõ trên hệ thống trong khi trừ thuê vẫn chạy; cần nối ticket với tạm dừng/ghi nhận hoàn.
- Quyết định cuối (Go / Not Yet / No-Go): Go, phạm vi nhỏ — MVP Rule (không AI quyết tiền)
- Repo: https://github.com/tundut/K5-L3B-DAY02-BabyShark-DiscoveryProblemFraming

## Thành viên

| STT | Họ và tên | MSSV | Vai trò trong nhóm | Tài khoản GitHub |
|---:|---|---|---|---|
| 1 | Nguyễn Phan Tuấn Đức | 2A202603818 | Nhóm trưởng / điều phối | tundut |
| 2 | Huỳnh Văn Cường | 2A202603866 | Pitch candidate chọn; research; quy trình + PS | cuong-huynh |
| 3 | Lê Ngọc Khánh | 2A202603804 | Phản biện; hỗ trợ kiểm chứng | lekhanh2k5-dotcom |

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

## Phân công theo checkpoint

| Checkpoint | Người chính | Người hỗ trợ | Sản phẩm |
|---|---|---|---|
| CP3 — Hội tụ nhóm | Đức | Cường, Khánh | Cluster, cây OST, bảng chấm điểm |
| CP4 — Kiểm chứng | Cường | Khánh | Assumption map, snapshot |
| CP4 — Research | Cường | Đức | Bảng research có link (Moiboo, Rently) |
| CP5 — Quy trình trước/sau | Cường | Khánh | Quy trình + before/after |
| CP5 — Problem Statement v0 | Cường | Đức | Problem Statement v0 |
| CP6 — Mức can thiệp + Problem Statement v1 | Đức | Cường | Ma trận, Rule MVP, eval, PS v1 |
| CP6 — Quyết định | Cả nhóm | — | 4 rủi ro + Go nhỏ + ngưỡng dừng |

## Cá nhân

### HuynhVanCuong-2A202603866

**Phần việc phụ trách:**

- Pitch Rank 1 (thuê xe / billing lệch sự cố) — candidate nhóm chọn
- Assumption map + khung kiểm chứng; research Pause Rental / incident
- Vẽ quy trình trước/sau; Problem Statement v0→v1; đề xuất Go Rule

**Đóng góp cụ thể:**

- Chốt bottleneck = lệch hai mạch (sự cố mờ vs billing tự động), không phải “thiếu chatbot”
- Bảng research Moiboo Pause Rental (×2) + Rently Incident → kết luận không tự xây agent
- Metric: % có mã &lt;5', cờ billing, giảm trả xe vs baseline nội bộ

**Bằng chứng:**

- `report/team/group_report.md` mục 2–8
- `report/individual/2A202603866_HuynhVanCuong.md` card #1

**Điều mình học được từ phần nhóm:**

- Research làm nhóm hạ mức can thiệp xuống Rule
- Viability (policy pause) phải ghi rõ và có ngưỡng dừng, không giả định fleet nào cũng pause được

### LeNgocKhanh-2A202603804

**Phần việc phụ trách:**

- *(Khánh tự điền)*

**Đóng góp cụ thể:**

-

**Bằng chứng:**

-

**Điều mình học được từ phần nhóm:**

-

### NguyenPhanTuanDuc-2A202603818

**Phần việc phụ trách:**

- *(Đức tự điền)*

**Đóng góp cụ thể:**

-

**Bằng chứng:**

-

**Điều mình học được từ phần nhóm:**

-
