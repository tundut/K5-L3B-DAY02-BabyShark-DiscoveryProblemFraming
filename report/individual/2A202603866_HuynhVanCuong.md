# Báo cáo cá nhân — 2A202603866_HuynhVanCuong

> Template chi tiết: [docs/01-worksheet.md](../../docs/01-worksheet.md).

## 1. Thông tin học viên

- Họ tên: Huỳnh Văn Cường
- MSSV: 2A202603866
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm: BabyShark
- Link repo nhóm: https://github.com/tundut/K5-L3B-DAY02-BabyShark-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Pain từ người khác | Khi tôi thuê xe máy để chạy app và xe hỏng ngay ngày đầu, tôi muốn được ghi nhận sự cố có mã theo dõi và biết khi nào được đổi xe / tạm dừng tính giờ, để không mất tiền thuê trong lúc chờ bảo hành dài. | Tài xế thuê xe; CSKH bên cho thuê | Ngày 1 đã hỏng; chờ BH theo ngày–tuần; giờ thuê vẫn chạy; nhiều tài xế trong nhóm chat nói trả xe vì chờ quá lâu (quan sát nhóm tài xế / trải nghiệm bản thân). |
| 2 | Tốn thời gian | Khi xe đã báo lỗi nhưng không có mã ticket xuyên suốt tới xưởng bảo hành, tôi muốn biết trạng thái từng bước (đã tiếp nhận / đã vào BH / ước nhận lại), để quyết định chờ tiếp hay trả xe. | Tài xế; điều phối BH | Không có mã chuẩn lúc báo lỗi; cập nhật rời rạc qua chat; mỗi lần hỏi lại mất ~10–30 phút; visibility gần như 0 trong nhiều ngày. |
| 3 | Lặp lại | Khi mỗi lần báo xe hỏng tôi phải gửi lại ảnh, biển số, ngày nhận xe qua nhiều kênh, tôi muốn chỉ nộp một lần đủ thông tin, để khỏi lặp lại và bị CSKH bảo “thiếu bằng chứng”. | Tài xế; CSKH | Mỗi case gửi lại 2–4 lần ảnh/chứng từ; mỗi vòng ~15–20 phút; hay bị yêu cầu bổ sung sau nhiều giờ. |
| 4 | Tốn thời gian | Khi tôi cần đối chiếu xem hôm nay bị trừ bao nhiêu giờ thuê trong lúc xe nằm xưởng, tôi muốn có bản ghi rõ ràng theo sự cố, để không phải tự tính tay và tranh cãi lúc trả xe. | Tài xế; kế toán thuê xe | Đối chiếu thủ công cuối kỳ; dễ lệch vài giờ–vài ngày; tranh chấp khi checkout. |
| 5 | Cần đọc, tổng hợp nhiều thông tin | Khi CSKH nhận nhiều tin báo lỗi lẫn lời than “trừ giờ oan”, họ muốn gom đúng hiện trạng + lịch sử thuê + chính sách tạm dừng, để trả lời nhất quán trong một ca. | CSKH thuê xe | Một case phải mở chat + ảnh + hợp đồng + lịch BH; ước ~20–40 phút/case khi cao điểm. |
| 6 | Pain từ người khác | Khi bạn cùng nhóm tài xế bị “treo” xe hỏng nhiều ngày mà vẫn bị tính thuê, họ muốn được xử lý công bằng sớm, để còn giữ việc chạy app thay vì trả xe. | Tài xế mới / thuê dài hạn | Pattern trả xe hàng loạt sau sự cố BH chậm (nghe từ nhóm; cần kiểm chứng thêm ở CP4). |
| 7 | Lặp lại | Khi tôi học và nộp bài nhiều kênh (LMS + portal + GitHub), tôi muốn biết mình còn thiếu bước nào trước deadline, để khỏi sót nộp. | Học viên cohort | Mỗi ngày kiểm tra 2–3 nơi; dễ sót standup / link repo. |
| 8 | Tốn thời gian | Khi nhóm chọn đề dự án dài hạn, tôi muốn so sánh nhanh ràng buộc–deliverables–tech stack của vài đề, để chọn đề vừa sức và còn slot. | Thành viên nhóm dự án | Catalog hàng trăm đề; đọc chi tiết từng đề tốn nhiều phút/đề. |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- Giữ: góc “thiếu mã ticket end-to-end” và “churn trả xe” — khớp trải nghiệm thật.
- Bỏ: các gợi ý kiểu “làm chatbot CSKH tổng quát” / “agent tự dừng billing” — đó là solution trá hình hoặc vượt boundary vận hành; không ghi vào cột Job Story.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Thuê xe hỏng ngày 1 — thiếu mã theo dõi BH, giờ thuê vẫn chạy | Actor rõ, bottleneck cụ thể, impact (trả xe) đo được, vừa sức lab | Tỉ lệ trả xe / SLA BH chính thức của từng đối tác thuê |
| 2 | Báo lỗi phải gửi lại bằng chứng nhiều lần | Lặp lại rõ, dễ vẽ quy trình, metric “số vòng bổ sung” | Chính sách bằng chứng tối thiểu của từng hãng |
| 3 | CSKH gom thông tin rời để trả lời case BH | Impact phía vận hành, khác góc tài xế | Có được quan sát CSKH thật trong lab không |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi tôi thuê xe máy chạy app và xe hỏng ngay ngày đầu, tôi muốn được ghi nhận sự cố có mã theo dõi và biết lộ trình bảo hành / đổi xe, để không mất tiền thuê oan trong lúc chờ. |
| Actor | Tài xế thuê xe máy (chạy Xanh SM / app tương tự); CSKH bên cho thuê |
| Thời điểm / bối cảnh | Ngày 1 hoặc sớm sau khi nhận xe; xe không chạy được / không đủ an toàn |
| Quy trình hiện tại (3–7 bước) | Phát hiện lỗi → báo hotline/chat → chờ (không mã) → xếp lịch BH → sửa lâu → nhận lại hoặc trả xe |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước sau báo lỗi: không có mã + không trạng thái — kéo dài theo **ngày–tuần**; mỗi lần hỏi lại ~10–30 phút |
| Impact (nếu không giải thì sao) | Tài xế mất thu nhập, vẫn bị tính thuê → trả xe hàng loạt; bên cho thuê mất công suất đội xe + tăng tranh chấp |
| Success metric (baseline → target) | (1) % case có mã trong &lt; 5 phút sau báo lỗi: ~0% → ≥ 90%. (2) Tỉ lệ trả xe trong 7 ngày sau báo lỗi: giảm so với baseline nội bộ sau A/B |
| Phương án không dùng AI | Form báo lỗi bắt buộc + sinh mã ticket rule-based + SMS trạng thái cố định; SOP tạm dừng giờ thuê khi xe vào BH |
| Giả thuyết về AI (nếu có) | AI hỗ trợ soạn ticket / checklist bằng chứng / gợi ý nhánh xử lý; người duyệt mọi quyết định tiền thuê |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
[1 Phát hiện xe hỏng] ⏱ ngay
        │
        ▼
[2 Báo hotline / chat thủ công] ⏱ 10–30p · 🔄 không mã chuẩn
        │
        ▼
[3 Chờ xếp lịch / đưa vào BH] 🔴 bottleneck · ⏱ ngày–tuần
   ⚠ giờ thuê vẫn chạy
        │
        ▼
[4 Sửa tại xưởng BH] 🔴 ít cập nhật trạng thái
        │
        ▼
[5 Nhận lại xe / trả xe (churn)]
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi tôi báo xe hỏng, tôi muốn nộp đủ bằng chứng một lần và được xác nhận đủ/thiếu ngay, để không gửi lại nhiều vòng. |
| Actor | Tài xế; CSKH |
| Thời điểm / bối cảnh | Ngay sau khi phát hiện lỗi, trước khi xe vào xưởng |
| Quy trình hiện tại (3–7 bước) | Chụp ảnh → gửi chat → CSKH bảo thiếu → gửi thêm → chờ duyệt → mới tạo lịch BH |
| Bottleneck (bước nào, mất bao nhiêu phút) | Vòng bổ sung bằng chứng: 2–4 vòng × 15–20 phút |
| Impact (nếu không giải thì sao) | Kéo dài toàn bộ chuỗi BH; tài xế bỏ cuộc |
| Success metric (baseline → target) | Số vòng bổ sung trung bình 3 → ≤ 1; % case “đủ hồ sơ từ lần 1” ≥ 80% |
| Phương án không dùng AI | Checklist bắt buộc trên form (ảnh tổng thể, chỗ hỏng, ODO, ngày nhận) trước khi submit |
| Giả thuyết về AI (nếu có) | AI kiểm tra nhanh ảnh đã đủ loại chưa, rồi mới cho submit |
| Cảm nhận nhanh | Rule (ưu tiên) / Workflow |

Quy trình nháp hiện tại:

```text
[1 Chụp/quay hiện trạng] → [2 Gửi chat] → [3 CSKH: thiếu] 🔴
        → [4 Gửi lại] → [5 Lặp 2–4 vòng] → [6 Mới tiếp nhận chính thức]
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi CSKH nhận tin báo lỗi lẫn than trừ giờ, họ muốn có một hồ sơ sự cố đủ ngữ cảnh trong một chỗ, để trả lời đúng chính sách trong một ca làm việc. |
| Actor | CSKH / điều phối bên cho thuê |
| Thời điểm / bối cảnh | Ca trực cao điểm, nhiều case song song |
| Quy trình hiện tại (3–7 bước) | Đọc chat → tìm ảnh cũ → mở hợp đồng → hỏi xưởng → soạn trả lời → gửi |
| Bottleneck (bước nào, mất bao nhiêu phút) | Gom thông tin rời: ~20–40 phút/case |
| Impact (nếu không giải thì sao) | Trả lời chậm/mâu thuẫn → khiếu nại tăng, tài xế trả xe |
| Success metric (baseline → target) | P50 thời gian phản hồi có quyết định rõ: 40 phút → &lt; 15 phút |
| Phương án không dùng AI | Dashboard ticket + template trả lời theo loại lỗi |
| Giả thuyết về AI (nếu có) | AI draft trả lời + tóm tắt hồ sơ; CSKH gửi |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
[1 Nhận chat] → [2 Tìm ảnh/hợp đồng/lịch BH] 🔴 20–40p
  → [3 Hỏi xưởng] → [4 Soạn trả lời] → [5 Gửi tài xế]
```

### Card muốn pitch nhất

- Card số: **#1**
- Vì sao: Pain stakeholder thật, khác example “hết pin”; bottleneck = thiếu mã + visibility; metric và phương án không-AI đều rõ.
- Câu hỏi muốn nhóm phản biện: *Nếu chỉ làm form + mã rule-based (không AI) đã đủ giảm trả xe, thì phần AI còn mang lại giá trị đo được ở bước nào?*

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Thiếu số liệu “% trả xe” cứng từ đối tác | Có | Đổi metric thành % có mã + giảm trả xe so với baseline nội bộ, không bịa % |
| Dễ nhảy sang “AI tự pause billing” | Có | Giữ phương án không-AI + giả thuyết AI chỉ draft; quyết định tiền = người |
| Card #1 và #2 có thể gộp | Một phần | Giữ tách: #1 = visibility/billing wait; #2 = evidence loop — pitch #1 |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | *(điền sau CP3)* | |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: | |
| Nhận phản biện | Câu hỏi tôi nhận được: | Tôi đã sửa gì: |
| Gom cluster / cây OST | | |
| Chọn candidate problem | | |
| Kiểm chứng / research | | |
| Quy trình nhóm | | |
| Problem Statement | | |
| Mức can thiệp AI | | |
| Quyết định | | |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Thought-partner làm rõ pain thuê xe / ticket BH | Nhấn mạnh “thiếu mã end-to-end” | Hay kéo về chatbot/agent tự pause billing | Chỉ giữ Job Story về hành vi & pain; bỏ solution trá hình |
| CP2 Problem Card | Phản biện kiểu PM hoài nghi | Bắt thiếu baseline số | Đề xuất gộp lung tung / solution-first | Tách card, siết metric, giữ No-AI option |
| CP4 Research | | | | |
| CP5 Quy trình | | | | |
| CP5–6 Problem Statement | | | | |
| CP6 Mức can thiệp / quyết định | | | | |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn sau khi làm phần nhóm. **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

*(điền sau CP3)*

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

*(điền sau)*

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

*(điền sau)*

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

*(điền sau CP4)*

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

*(điền sau CP5–6)*

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

*(điền sau)*

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

*(điền cuối buổi)*

---

## 7. Tài liệu tham khảo

- [CHECKPOINTS.md](../../CHECKPOINTS.md)
- [docs/01-worksheet.md](../../docs/01-worksheet.md)
- [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md)
- Trải nghiệm / quan sát cộng đồng tài xế thuê xe chạy app (cần kiểm chứng thêm ở CP4)
