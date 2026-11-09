# Báo cáo cá nhân — 2A202603866_HuynhVanCuong

> Đổi tên file theo quy tắc `MSSV_HoTen.md`. Template chi tiết: [docs/01-worksheet.md](../../docs/01-worksheet.md).

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
| 1 | Pain từ người khác | Khi xe thuê bị hỏng và tôi đã báo lỗi, tôi muốn sự cố được theo dõi rõ trên hệ thống và việc trừ tiền thuê được tạm dừng hoặc ghi nhận để hoàn/cấn trừ sau có căn cứ, để không bị trừ thuê tự động trong lúc xe không dùng được mà không biết đòi lại thế nào. | Tài xế thuê xe; CSKH / kế toán bên cho thuê | Hệ thống vẫn trừ thuê tự động; trạng thái sự cố/BH không rõ lưu–quản lý thế nào; hoàn sau mơ hồ; treo ngày–tuần; có case nhận xe xong mới lộ hỏng (ví dụ ngày 1); nhiều tài xế nói trả xe vì treo (quan sát/nghe kể). |
| 2 | Tốn thời gian | Khi tôi (tài xế ô tô công nghệ) đã tới điểm đón ở khu Vin hoặc khu tương tự mà khách chưa ra, tôi muốn biết nên chờ tiếp, vòng chờ, hay hủy, để không vừa mất đoạn đường đã chạy tới điểm vừa mất thêm thời gian/xăng vì vòng vòng hoặc phải nhận đơn mới. | Tài xế ô tô công nghệ | Thường chờ vài–hơn mười phút; vòng vòng tốn thêm vài phút/vòng; hủy thì mất cả thời gian đã chạy tới điểm; tài xế vẫn hay chịu rủi ro vì không muốn mất khách (quan sát/nghe tài xế than). |
| 3 | Tốn thời gian | Khi app chỉ ghi điểm đón chung chung trong khu Vin/tòa nhà, tôi muốn biết khách đang ở cổng/sảnh nào, để khỏi chạy lòng vòng trong khu và nhắn qua lại nhiều lần. | Tài xế; khách | Nhắn 2–5 tin/lượt; vòng trong khu khoảng 5–10 phút/chuyến ở điểm đón phức tạp. |
| 4 | Pain từ người khác | Khi tôi đã tới điểm đón mà khách hủy sát giờ, tôi muốn được ghi nhận rõ mình đã di chuyển/chờ bao lâu, để khỏi mất cả đoạn đường chạy tới mà không có chuyến thay thế ngay. | Tài xế | Mất khoảng 10–20 phút đã chạy tới điểm; gặp vài lần trong ngày cao điểm (ước lượng từ quan sát tài xế). |
| 5 | Lặp lại | Khi trả hoặc đổi xe thuê cuối ngày/cuối kỳ, tôi muốn chốt ảnh và tình trạng xe một lần có xác nhận, để sau không bị đổ lỗi hỏng phát sinh sau khi tôi dùng. | Tài xế thuê xe; bên cho thuê | Mỗi lần trả xe mất khoảng 10–15 phút chụp/gửi; tranh chấp hiện trạng thỉnh thoảng xảy ra. |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- Tự nghĩ trước: (1) thuê xe hỏng / thiếu theo dõi BH + tính giờ (ngày đầu chỉ là một case cụ thể, không phải lúc nào cũng vậy), (2) chờ khách khu Vin phải vòng vòng / rủi ro hủy.
- Dùng AI/thought-partner chỉ để **mở rộng thêm 3 góc** cùng hệ tài xế (điểm đón khó tìm, hủy sát giờ, checklist trả xe) — giữ vì khớp vận hành thật, có thể đo thời gian.
- Bỏ các gợi ý kiểu “làm chatbot / agent tự quyết hủy chuyến / tự dừng billing” — đó là giải pháp trá hình, không ghi vào cột Job Story.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Xe thuê hỏng đã báo lỗi: phần sự cố/BH không rõ có được lưu–quản lý thế nào trên hệ thống, trong khi **trừ tiền thuê vẫn chạy tự động**; sau này hoàn/cấn trừ ra sao cũng mơ hồ | Pain nắm rõ; lệch “billing tự động” vs “sự cố thủ công/mờ”; impact tiền + trả xe; MVP có thể là Rule | Policy chính thức tạm dừng/hoàn giờ thuê khi BH; cách hệ thống hiện lưu (hay không lưu) trạng thái sự cố; baseline % trả xe |
| 2 | Tài xế ô tô chờ khách ở khu Vin / tương tự: vòng vòng hoặc hủy đều lỗ thời gian/xăng sau khi đã chạy tới điểm | Actor rõ; quy trình ngắn; rủi ro quyết định chờ/hủy cụ thể | Tần suất đúng theo từng khu; tín hiệu “khách còn ra” lấy từ đâu |
| 3 | Điểm đón trong khu Vin/tòa ghi chung chung → chạy lòng vòng + nhắn nhiều lần | Dễ vẽ quy trình; hay đi kèm pain #2 | Bao nhiêu % cuốc bị lệch điểm vs chỉ chậm khách |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi xe thuê bị hỏng và tôi đã báo lỗi, tôi muốn sự cố được ghi nhận–theo dõi trên hệ thống rõ ràng (không chỉ chat rời) và việc trừ tiền thuê được tạm dừng hoặc ghi nhận để hoàn/cấn trừ sau có căn cứ, để không bị hệ thống trừ thuê tự động trong lúc xe không dùng được mà không biết sau này đòi lại thế nào. |
| Actor | Tài xế thuê xe chạy app; CSKH / điều phối / kế toán bên cho thuê; xưởng BH |
| Thời điểm / bối cảnh | Sau khi phát hiện hỏng và đã báo (có case nhận xe xong mới lộ — ngày đầu chỉ là ví dụ); BH/treo xử lý kéo dài |
| Quy trình hiện tại (3–7 bước) | Phát hiện hỏng → báo hotline/chat → sự cố **không rõ** có được lưu/quản lý trên hệ thống thế nào → BH/chờ lâu → **hệ thống vẫn trừ tiền thuê tự động** → sau này hoàn/cấn trừ (nếu có) mơ hồ, tranh chấp hoặc bỏ cuộc / trả xe |
| Bottleneck (bước nào, mất bao nhiêu phút) | Lệch hai mạch: (A) sự cố/BH quản lý thủ công hoặc không minh bạch; (B) **billing tự động vẫn chạy**. Treo theo ngày–tuần; hỏi lại ~10–30 phút/lần; không biết “trừ rồi thì hoàn kiểu gì / khi nào” |
| Impact (nếu không giải thì sao) | Mất tiền thuê oan + mất thu nhập → trả xe; tranh chấp hoàn tiền tốn thêm thời gian CSKH/kế toán |
| Success metric (baseline → target) | (1) % case báo lỗi có mã + trạng thái trên hệ thống trong &lt; 5 phút: ~0% → ≥ 90%. (2) % case BH/treo có **cờ/ghi nhận gắn với billing** (tạm dừng hoặc đánh dấu hoàn sau) trước khi hết ngày sự cố. (3) Giảm trả xe trong 7 ngày sau báo lỗi so với baseline nội bộ. |
| Phương án không dùng AI | Form báo lỗi → mã ticket + trạng thái trên hệ thống; **rule gắn ticket với thuê**: đủ điều kiện thì tạm dừng trừ hoặc ghi nợ hoàn; sổ hoàn/cấn trừ có trạng thái (chờ duyệt / đã hoàn); tài xế xem được trên app |
| Giả thuyết về AI (nếu có) | **MVP không cần AI** — cần nối sự cố với billing bằng rule. AI sau này chỉ phụ (đọc mô tả chat, draft trả lời hoàn tiền) — không tự trừ/hoàn. |
| Cảm nhận nhanh | **Rule** (ưu tiên) / No AI cho MVP |

Quy trình nháp hiện tại:

```text
HIỆN TẠI — hai mạch lệch nhau

[1 Phát hiện hỏng] → [2 Báo chat/hotline]
        │
        ▼
[3 Sự cố: không rõ lưu/quản lý trên hệ thống thế nào] 🔴
   (chat rời, hỏi lại ~10–30p, treo ngày–tuần)
        │
        ▼
[4 BH / chờ sửa] ⏱ dài
        │
        │   song song:
        ▼
[B Hệ thống VẪN TRỪ TIỀN THUÊ TỰ ĐỘNG] 🔴 BOTTLENECK (tiền)
        │
        ▼
[5 Sau này hoàn / cấn trừ?] ⚠ không rõ quy trình → tranh chấp
   hoặc [6 Trả xe / bỏ cuộc]
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi tôi đã tới điểm đón ở khu Vin hoặc khu tương tự mà khách chưa ra, tôi muốn biết nên chờ tiếp, vòng chờ, hay hủy, để không vừa mất đoạn đường đã chạy tới điểm vừa mất thêm thời gian/xăng. |
| Actor | Tài xế ô tô công nghệ; khách |
| Thời điểm / bối cảnh | Sau khi app báo đã tới điểm đón tại khu đô thị / Vin / tòa nhà; chỗ dừng hạn chế |
| Quy trình hiện tại (3–7 bước) | Nhận cuốc → chạy tới điểm → chờ / vòng vòng → hết hạn chờ thì hủy hoặc đón được khách → (nếu hủy) nhận đơn mới |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước sau “đã tới điểm đón”: chờ vài–hơn mười phút; vòng thêm vài phút/vòng; thiếu tín hiệu khách còn ra hay không |
| Impact (nếu không giải thì sao) | Lỗ thời gian/xăng; hủy thì mất trip + phải xếp đơn mới; tài xế chịu rủi ro để giữ khách |
| Success metric (baseline → target) | Thời gian chết trung bình sau khi tới điểm (chờ+vòng) giảm (vd. ước 8–12 phút → &lt; 5 phút) trên mẫu cuốc khu Vin; hoặc giảm % cuốc hủy sau khi đã tới điểm |
| Phương án không dùng AI | Nút “khách còn X phút” bắt buộc phía khách; điểm chờ/đón quy định trong khu; đếm ngược chờ + phí chờ rõ trên app |
| Giả thuyết về AI (nếu có) | Gợi ý chờ/hủy dựa trên tín hiệu (phản hồi khách, lịch sử hủy khu, ETA) — tài xế quyết định; không tự hủy |
| Cảm nhận nhanh | Workflow (hoặc Rule nếu chỉ cần nút/phí chờ) |

Quy trình nháp hiện tại:

```text
HIỆN TẠI — mỗi cuốc khu Vin / tương tự

[1 Nhận cuốc] → [2 Chạy tới điểm đón] ⏱ ~10–20p
        │
        ▼
[3 Đã tới — chờ / vòng vòng] 🔴 BOTTLENECK ⏱ vài–15p+
        │
        ├─► [4a Đón được khách]
        └─► [4b Hủy theo hạn] → [5 Nhận đơn mới] ⚠ đã mất thời gian bước 2
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi app chỉ ghi điểm đón chung chung trong khu Vin/tòa nhà, tôi muốn biết khách đang ở cổng/sảnh nào, để khỏi chạy lòng vòng trong khu và nhắn qua lại nhiều lần. |
| Actor | Tài xế; khách |
| Thời điểm / bối cảnh | Gần tới / đã vào khu; pin điểm map không khớp lối vào thực tế |
| Quy trình hiện tại (3–7 bước) | Điều hướng tới pin → không thấy khách → gọi/nhắn → chạy thử các cổng → gặp khách hoặc hủy |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước tìm đúng cổng/sảnh trong khu: ~5–10 phút + 2–5 tin nhắn |
| Impact (nếu không giải thì sao) | Trễ đón, khách/tài xế ức chế, tăng hủy hoặc rating xấu |
| Success metric (baseline → target) | Thời gian từ “vào khu” → “gặp khách” giảm (vd. 8 phút → &lt; 3 phút); số tin nhắn điều phối trung bình giảm |
| Phương án không dùng AI | Khách bắt buộc chọn cổng/sảnh trong danh sách khu; ảnh landmark; share live location ngắn hạn |
| Giả thuyết về AI (nếu có) | Gợi ý cổng phổ biến theo lịch sử đón tại POI — không bắt buộc |
| Cảm nhận nhanh | Rule (ưu tiên) |

Quy trình nháp hiện tại:

```text
[1 Tới pin trên map] → [2 Không thấy khách]
        │
        ▼
[3 Gọi/nhắn + chạy các cổng] 🔴 BOTTLENECK ⏱ ~5–10p
        │
        ▼
[4 Gặp khách / hủy]
```

### Card muốn pitch nhất

- Card số: **#1** (sự cố/BH không rõ trên hệ thống trong khi **trừ thuê tự động**; hoàn sau mơ hồ)
- Vì sao: Lệch hai mạch (sự cố mờ vs billing chạy) là pain tiền thật; MVP = Rule nối ticket với tạm dừng/ghi nhận hoàn — không cần AI để “tạo ticket”.
- Câu hỏi muốn nhóm phản biện: *Nếu đã có mã sự cố trên hệ thống và rule gắn với tạm dừng/hoàn thuê (không AI), có đủ giải quyết việc bị trừ tự động lúc xe không dùng được không — AI còn cần ở bước nào?*

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Dễ bị hiểu nhầm là “cần AI tạo ticket” trong khi tạo mã là rule | Có | Nhấn mạnh MVP = Rule/No AI; AI chỉ phụ (checklist/draft), không phải lõi bài toán |
| “Ngày đầu hỏng” nghe như luôn xảy ra | Có (đã sửa từ CP1) | Card #1 ghi rõ ngày đầu chỉ là ví dụ case |
| Thiếu baseline % trả xe cứng | Có | Metric dùng % có mã &lt;5 phút + giảm trả xe so với baseline nội bộ (đo sau), không bịa % |
| Card #1 và checklist trả xe (#5 CP1) dễ trùng | Một phần | Top 3 lấy #3 điểm đón thay vì checklist; checklist giữ ở scan |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | | |
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
| CP1 Scan | Thought-partner làm rõ trọng tâm pain + gợi ý thêm 3 dòng cùng hệ tài xế | Giúp tách “xe hỏng” vs “thiếu theo dõi/tính giờ”; bổ sung điểm đón / hủy sát giờ / checklist trả xe | Hay đẩy sang chatbot/agent tự quyết | Chỉ giữ Job Story + dấu hiệu; bỏ solution-first |
| CP2 Problem Card | Điền 3 card; nhờ góc PM hoài nghi soi “AI có cần không” | Nhắc MVP Rule đủ cho ticket/billing SOP | Hay đẩy agent tự pause billing | Giữ Rank 1 + cảm nhận Rule/No AI; AI chỉ phụ |
| CP4 Research | | | | |
| CP5 Quy trình | | | | |
| CP5–6 Problem Statement | | | | |
| CP6 Mức can thiệp / quyết định | | | | |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật sau phần nhóm. **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

*(điền sau CP3)*

**6.2. Nhóm có lúc nào bị "solution-first" không? Lúc đó nhóm nhận ra và xử lý thế nào?**

*(điền sau)*

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

*(điền sau)*

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

*(điền sau CP4)*

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

*(điền sau CP5–6)*

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

*(điền sau)*

**6.7. Hiểu bài:** giải thích bằng 5–8 câu chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm.

*(điền cuối buổi)*

---

## 7. Tài liệu tham khảo

- [CHECKPOINTS.md](../../CHECKPOINTS.md)
- [docs/01-worksheet.md](../../docs/01-worksheet.md)
- Quan sát / nghe tài xế ô tô công nghệ và tài xế thuê xe (cần kiểm chứng thêm ở CP4 nếu nhóm chọn candidate này)
