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
| 6 | Cần đọc, tổng hợp nhiều thông tin | Khi đang treo sự cố/BH và phải đối chiếu chat CSKH, tin nhắn kế toán, ảnh xe và lịch trừ thuê, tôi muốn nắm được trạng thái sự cố và khoản nào đã/đang trừ trong một chỗ, để khỏi lướt nhiều luồng rồi vẫn không biết đang nợ hay được hoàn. | Tài xế thuê xe; CSKH / kế toán | Mỗi lần hỏi lại ~10–30 phút; phải đọc lại chuỗi chat + bill; treo ngày–tuần (quan sát/nghe kể, cùng hệ pain #1). |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- Tự nghĩ trước: (1) thuê xe hỏng / thiếu theo dõi BH + tính giờ (ngày đầu chỉ là một case cụ thể, không phải lúc nào cũng vậy), (2) chờ khách khu Vin phải vòng vòng / rủi ro hủy.
- Dùng AI/thought-partner để **mở rộng thêm góc** cùng hệ tài xế (điểm đón khó tìm, hủy sát giờ, checklist trả xe, và góc tổng hợp chat/bill khi treo sự cố) — giữ vì khớp vận hành thật, có thể đo thời gian.
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
| Pitch Problem Card | Pitch #1 thuê xe (billing vs sự cố mờ), #2 chờ khách Vin, #3 điểm đón | **#1 được chọn** làm candidate nhóm |
| Phản biện bài của bạn khác | Với Khánh: metric chính “không sót” hay “giảm phút”? Với Đức: checklist nguồn đã đủ chưa? | Giữ bài học tập/JD làm hướng tiếp theo, không trộn vào MVP thuê xe |
| Nhận phản biện | Đức/Khánh hỏi: policy pause đã có chưa? Kiểm chứng tài xế trong lab thế nào? | Thu hẹp MVP = mã sự cố + gắn billing; ghi Viability #6 + ngưỡng dừng; không hứa AI |
| Gom cluster / cây OST | Gom 9 card; OST outcome = không mất tiền oan / không trả xe khi đã báo lỗi | Gạch solution “chatbot/agent tự pause” |
| Chọn candidate problem | Tranh luận shortlist với bài gom tài liệu (lab-fit cao hơn) | Nhóm chọn thuê xe vì lệch quy trình + kết luận Rule sạch |
| Kiểm chứng / research | Structured quan sát/nghe kể + research Moiboo Pause Rental, Rently Incident | Đổi từ “có thể cần AI” → **Rule đủ cho MVP** |
| Quy trình nhóm | Vẽ hai mạch lệch → form→mã→rule billing→HITL | Mục 4 `group_report.md` |
| Problem Statement | Viết v0; v1 thêm “fleet có SOP pause” + AI point = không có ở MVP | PS không chứa chatbot |
| Mức can thiệp AI | So sánh 4 mức; loại Agent đụng tiền | **Chốt Rule** |
| Quyết định | Go nhỏ + ngưỡng dừng (% mã, pause nhầm, policy cấm pause) | **Go, phạm vi nhỏ** |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Thought-partner làm rõ pain + gợi ý thêm 3 dòng cùng hệ tài xế | Tách “xe hỏng” vs “thiếu theo dõi/tính giờ”; bổ sung điểm đón / hủy / checklist trả xe | Hay đẩy chatbot/agent tự quyết | Chỉ giữ Job Story + dấu hiệu |
| CP2 Problem Card | Điền 3 card; PM hoài nghi soi “AI có cần không” | Nhắc MVP Rule đủ cho ticket/billing SOP | Đẩy agent tự pause billing | Giữ Rank 1 = Rule/No AI; AI chỉ phụ |
| CP4 Research | Gợi ý tool fleetrental (pause/incident) | Nhanh ra hướng Pause Rental / incident status | Link marketing; gợi ý “build AI CSKH” | Tự mở Moiboo + Rently; bỏ nguồn mở không ổn; kết luận không tự xây agent |
| CP5 Quy trình | Nháp ASCII before/after + boundary | Làm rõ hai mạch lệch | Gộp tạo ticket với AI | Tách Rule tạo mã + HITL đổi tiền; AI optional draft sau |
| CP5–6 Problem Statement | Soi lỗ hổng metric/boundary | Nhắc đừng bịa % trả xe | Nhét giải pháp vào PS | Metric có mã + cờ billing; baseline trả xe đo sau |
| CP6 Mức can thiệp / quyết định | Hỏi khi nào cần Agent | Nhắc Agent = tự quyết bước / tiền | Thiên Workflow/AI dù Rule chưa thử | Ép “vì sao không mức đơn giản hơn” → Go Rule + ngưỡng dừng |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật sau phần nhóm.

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Khánh tách được hai bottleneck (sót vs phút). Mình áp dụng lại cho bài thuê xe: tách “thiếu mã/trạng thái sự cố” khỏi “billing vẫn chạy”, không gộp thành “CSKH kém”. Đức cho thấy bài JD dễ trượt vì metric tự đánh giá năng lực ảo; nhờ đó mình không bịa baseline % trả xe, mà để đo sau theo số nội bộ. Bài học tập của Khánh dễ poll trong lớp hơn, nên khi nhóm chọn thuê xe mình cũng nói thẳng: điểm yếu là kiểm chứng domain ngoài lớp, phải dựa quan sát/nghe kể + research tool và ghi hạn chế mẫu.

**6.2. Nhóm có lúc nào bị "solution-first" không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Có. Lúc đầu dễ nhảy sang “chatbot báo lỗi” hoặc “agent tự pause billing”. Khi vẽ OST và đọc research Pause Rental / incident status, nhóm thấy thị trường đã có rule gắn downtime với agreement. Cách xử lý: gạch chatbot/agent khỏi tầng opportunity; chốt MVP = form + mã sự cố + rule gắn billing + người duyệt.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Có. Card #1 từng dễ bị hiểu là “ngày đầu nhận xe luôn hỏng” hoặc “cần AI tạo ticket”. Sau phản biện của nhóm/AI đóng vai PM: mình sửa (1) ngày đầu chỉ là ví dụ case, (2) tạo mã là Rule không phải AI, (3) nếu fleet không cho pause theo policy thì không Go full. Sang Problem Statement v1, AI intervention point ghi rõ không có ở MVP; actor thu hẹp fleet có SOP pause.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

Bất ngờ nhất ở research: Pause Rental và incident gắn booking đã là tính năng sản phẩm fleetrental. Vậy phần đáng làm không phải xây AI, mà là nối hai mạch + SOP + đo % có mã và cờ billing. Phần quan sát/nghe kể xác nhận pain tiền và trả xe, nhưng cũng có tín hiệu phản bác (một số nơi đã có form báo hỏng; “ngày đầu hỏng” không phải luôn xảy ra) — nên nhóm thu hẹp scope thay vì phóng đại.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Khó nhất là Success Metric có baseline thật: chưa có % trả xe cứng nên phải viết so với baseline nội bộ đo sau, không bịa số. Khó thứ hai là Boundary vì bài đụng tiền: phải viết AI không được tạm dừng/hoàn, và HITL là bắt buộc, nếu không PS sẽ trượt sang giải pháp nguy hiểm.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Nếu làm lại, mình sẽ xin thêm 1–2 buổi hỏi ngắn với tài xế/CSKH trước CP3 để Feasibility chắc hơn. Với nhóm, mình sẽ phản biện mạnh hơn mỗi khi ai đề xuất Agent đụng billing: hỏi ngay ai audit, ai chịu nếu trừ/hoàn sai, và Rule đã cover chưa.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm.

Problem: tài xế đã báo xe thuê hỏng nhưng sự cố không rõ trên hệ thống trong khi tiền thuê vẫn trừ tự động. Quy trình hiện tại chạy hai mạch lệch — chat/BH một đường, billing một đường — dẫn tới tranh chấp hoặc trả xe. Metric: hầu hết case có mã+status trong &lt;5 phút, có cờ gắn billing trước cuối ngày sự cố, và theo dõi giảm trả xe so với baseline nội bộ. Boundary: AI không tự tạm dừng/hoàn/đóng case; mọi đổi tiền cần mã sự cố và người duyệt. Mức can thiệp: MVP là Rule (form→mã→pause/ghi nợ); AI chỉ có thể draft ticket sau này. Quyết định Go phạm vi nhỏ trên fleet có SOP, kèm ngưỡng dừng nếu không tạo được mã kịp, pause nhầm, hoặc policy cấm pause.

---

## 7. Tài liệu tham khảo

- [CHECKPOINTS.md](../../CHECKPOINTS.md)
- [docs/01-worksheet.md](../../docs/01-worksheet.md)
- [report/team/group_report.md](../team/group_report.md)
- Moiboo Pause Rental / daily rental billing; Rently Incident (mục 3.3 & 10 báo cáo nhóm)
- Quan sát / nghe tài xế thuê xe & ô tô công nghệ (CP1–CP2)
