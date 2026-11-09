# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm: BabyShark
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu): Khi xe thuê bị hỏng và đã báo lỗi, tài xế muốn sự cố được theo dõi rõ trên hệ thống và việc trừ tiền thuê được tạm dừng/ghi nhận hoàn có căn cứ, để không bị trừ tự động lúc xe không dùng được.
- Quyết định cuối: **Go, phạm vi nhỏ** — MVP = **Rule** (mã sự cố + gắn billing tạm dừng/ghi nợ hoàn); AI chỉ phụ sau này, không tự trừ/hoàn

---

## 2. Hội tụ nhóm (CP3)

### 2.1. Pitch

| # | Người đưa ra | Candidate (Job Story ngắn) | Actor | Bottleneck | Câu hỏi phản biện (ai hỏi/đặt) |
|---:|---|---|---|---|---|
| 1 | Cường | Xe thuê hỏng đã báo: sự cố mờ trên hệ thống trong khi trừ thuê vẫn chạy | Tài xế thuê xe; CSKH/kế toán | Hai mạch lệch: sự cố thủ công vs billing tự động (ngày–tuần) | Đức: Policy tạm dừng thuê khi BH có chưa? Baseline % trả xe lấy ở đâu? · Khánh: Bản thân Cường đã trực tiếp gặp cảnh xe thuê hỏng mà vẫn bị trừ tiền chưa hay chỉ quan sát qua nhóm chat, và nếu không tiếp cận được dữ liệu của hãng xe thì nhóm đo baseline bằng cách nào? |
| 2 | Cường | Tới điểm đón khu Vin mà khách chưa ra: chờ / vòng / hủy đều lỗ | Tài xế ô tô công nghệ | Sau “đã tới điểm”: chờ + vòng vài–15'+ | Khánh: Tín hiệu “khách còn ra” lấy từ đâu? |
| 3 | Cường | Điểm đón trong khu ghi chung chung → lòng vòng + nhắn nhiều | Tài xế; khách | Tìm đúng cổng/sảnh ~5–10' + 2–5 tin | Khánh: Có cùng pattern với chờ khách (#2) không? |
| 4 | Khánh | Ôn thi: tài liệu ở LMS + Drive + chat + ảnh → muốn gom đủ, không sót | Sinh viên cùng lớp | B3 sót lời dặn (~10'); B4 lọc ảnh (~15'/môn) | Cường: Metric chính là “không sót” hay “giảm phút”? · Đức: Nếu chỉ tạo album ảnh riêng cho từng môn và ghim tin nhắn của giảng viên, vấn đề có còn đủ nghiêm trọng để cần AI không? |
| 5 | Khánh | Cần lại file cũ trong nhiều nhóm chat | Người nhận file | Lướt ngược chat ~20'/lần | Đức: File quá hạn/Zalo có ngoài tầm tay không? |
| 6 | Khánh | Ảnh slide/bảng → muốn có chữ trong ghi chú, không gõ lại | Sinh viên chụp bài | Gõ lại từ ảnh ~15–20'/buổi | Cường: Live Text/Lens còn gap ở đâu? |
| 7 | Đức | So JD với kỹ năng hiện tại để biết còn thiếu gì trước nộp hồ sơ | SV năm cuối / fresher | Đối chiếu năng lực ~30'/lần; tổng ~90' | Khánh: Lần gần nhất Đức tự đối chiếu kỹ năng với JD là khi nào, lúc đó Đức có đánh giá sai kỹ năng nào của mình không và làm sao phát hiện ra là mình bị thiếu? |
| 8 | Đức | Học công nghệ mới: chọn tài liệu khớp trình độ/mục tiêu | SV IT tự học | Đọc–đánh giá tài liệu ~25'/lần | Cường: Checklist nguồn GV/cộng đồng đã đủ chưa? |
| 9 | Đức | Gặp lỗi project: muốn khoanh nguyên nhân nhanh | SV làm project | Tìm nguyên nhân ~30'/lỗi | Khánh: Debugger + log giải được bao nhiêu %? |


### 2.2. Cluster

| Cluster | Các candidate | Pattern chung |
|---|---|---|
| A — Thuê xe / sự cố–tiền | Xe hỏng + billing lệch sự cố (Cường #1) | Trạng thái sự cố không nối với tiền thuê |
| B — Điểm đón / chờ khách | Chờ khách Vin (Cường #2); điểm đón mơ hồ (Cường #3) | Thời gian chết sau khi đã tới điểm |
| C — Gom / tìm thông tin học | Gom tài liệu ôn thi; tìm file chat; chọn tài liệu công nghệ | Thông tin rải nhiều nơi → sót hoặc mất phút |
| D — Digitize ghi chú | Gõ lại ảnh bảng/slide | OCR / chuyển ảnh → chữ |
| E — Việc & debug | Gap JD; lỗi project | Đối chiếu / khoanh nguyên nhân |

### 2.3. Opportunity Solution Tree rút gọn

```text
OUTCOME: Tài xế thuê xe không bị mất tiền thuê oan và không bỏ cuộc (trả xe) khi xe không chạy được sau khi đã báo lỗi
├── Opportunity A: Sự cố/BH không có mã + trạng thái rõ trên hệ thống (chat rời)
├── Opportunity B: Billing vẫn trừ thuê tự động song song lúc xe treo/BH
└── Opportunity C: Hoàn/cấn trừ sau này mơ hồ → tranh chấp hoặc bỏ cuộc
     ✗ "Chatbot CSKH tự pause billing"     ← solution
     ✗ "Agent tự quyết trừ/hoàn tiền"      ← solution
     ✗ "App AI bảo hiểm toàn trình"       ← solution
```

Những ý đã gạch bỏ vì là solution đội lốt opportunity:

- “Làm chatbot báo lỗi”
- “Agent tự tạm dừng trừ tiền”
- “Dashboard AI cho tài xế”

### 2.4. Chấm điểm shortlist (1–5)

| Candidate | Actor rõ | Quy trình rõ | Pain có bằng chứng | Impact đo được | Vừa sức lab | So sánh được No AI/Rule/Workflow/Agent | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Xe thuê hỏng / billing lệch sự cố (Cường) | 5 | 5 | 3 | 5 | 3 | 5 | 4 | **30** |
| Gom tài liệu ôn thi (Khánh) | 5 | 5 | 4 | 4 | 5 | 5 | 5 | 33 |
| Gap kỹ năng vs JD (Đức) | 5 | 5 | 3 | 4 | 5 | 5 | 4 | 31 |

**Candidate được chọn:** Xe thuê hỏng đã báo lỗi — sự cố không rõ trên hệ thống trong khi **trừ thuê vẫn chạy tự động**; hoàn/cấn trừ sau mơ hồ.

**Vì sao chọn:** Bottleneck là **một lệch quy trình cụ thể** (hai mạch: sự cố thủ công vs billing tự động), impact tiền + trả xe, MVP so sánh 4 mức rất sạch (Rule nối ticket↔billing, không cần AI để “tạo mã”). Nhóm chấp nhận Feasibility kiểm chứng khó hơn bài học tập vì muốn làm bài có kết luận Rule rõ và research thị trường fleetrental đã có Pause Rental.

**Vì sao loại các candidate còn lại:** Các card còn lại chủ yếu dựa trên trải nghiệm cá nhân hoặc chưa có bằng chứng đủ mạnh về mức độ ảnh hưởng. Một số card có thể được giải quyết trước bằng thói quen, checklist hoặc quy tắc lưu trữ.

- **Gom tài liệu ôn thi:** Điểm tổng cao hơn, dễ poll trong lớp, nhưng nhóm thống nhất ưu tiên bài có lệch tiền/vận hành và kết luận “không tự xây AI”. Ghi làm hướng tiếp theo nếu mở rộng lab học tập.
- **Gap JD:** Quy trình đẹp nhưng metric tự đánh giá năng lực dễ ảo; giữ vòng sau.

**Xử lý bất đồng:** Khánh/Đức lo thiếu phỏng vấn tài xế formal trong 4 tiếng. Thỏa thuận: CP4 dùng quan sát/nghe kể có cấu trúc + research tool có sẵn; ghi rõ hạn chế mẫu nhỏ; ngưỡng dừng nếu pilot không xác nhận pain tiền thật.

---

## 3. Kiểm chứng + research giải pháp đã có (CP4)

### 3.1. Assumption Map

| # | Giả định | Loại (Value / Usability / Feasibility / Viability) | Quan trọng (1–5) | Đã có bằng chứng (1–5) | Kiểm chứng trước? |
|---:|---|---|---:|---:|---|
| 1 | Nhiều tài xế thuê xe gặp case “đã báo hỏng mà vẫn bị trừ thuê” | Value | 5 | 2 | ✅ |
| 2 | Bottleneck chính là **lệch billing vs sự cố**, không phải thiếu chatbot | Value | 5 | 3 | ✅ |
| 3 | Có thể tạo mã sự cố + trạng thái trên hệ thống trong &lt; 5 phút (ops chấp nhận) | Feasibility | 5 | 2 | ✅ (research + hỏi quy trình) |
| 4 | Rule tạm dừng/ghi nợ hoàn gắn ticket đủ cho MVP; chưa cần AI | Feasibility | 5 | 4 | ✅ research Pause Rental |
| 5 | Tài xế sẽ mở app xem trạng thái sự cố/billing nếu có | Usability | 4 | 2 | ✅ hỏi nhanh |
| 6 | Bên cho thuê cho phép pause billing theo policy (pháp lý/kế toán) | Viability | 5 | 1 | ⚠ chưa đủ — ghi Not Yet một phần |

Giả định nhóm kiểm chứng trong buổi này: #1, #2, #4, #5. Giả định #6 đánh dấu cần hỏi thêm trước khi pilot thật với một fleet.

### 3.2. Kiểm chứng

Cách đã dùng: **quan sát / nghe kể có cấu trúc** (theo khung Mom Test: chuyện đã xảy ra, workaround, thời gian) + đối chiếu báo cáo cá nhân Cường + **research giải pháp có sẵn**. Nhóm **không** dựng phỏng vấn formal giả; ưu tiên bằng chứng hành vi đã quan sát được và tín hiệu phản bác.

Evidence snapshot 1 — tài xế thuê xe (quan sát/nghe kể):

| Trường | Nội dung |
|---|---|
| Nguồn (vai trò, không ghi tên thật) | Tài xế thuê xe chạy app — quan sát/nghe kể lặp lại |
| Câu / mô tả đáng nhớ | Xe không chạy được (treo BH) mà tiền thuê vẫn bị trừ; hỏi CSKH thì bị bảo chờ |
| Chuyện cụ thể đã xảy ra | Báo hỏng qua chat/hotline; không thấy mã/trạng thái rõ trên hệ thống; billing vẫn theo chu kỳ |
| Workaround hiện tại | Nhắn lại nhiều lần; giữ ảnh/bill; một số case bỏ cuộc / trả xe |
| Mất bao lâu, bao lần? | Treo ngày–tuần; mỗi lần hỏi lại ước ~10–30 phút |
| Insight | Pain lõi = **minh bạch sự cố + nối với tiền**, không phải thiếu chatbot |

Evidence snapshot 2 — góc vận hành/CSKH (nghe kể / mô tả quy trình):

| Trường | Nội dung |
|---|---|
| Nguồn (vai trò, không ghi tên thật) | Mô tả từ phía gần CSKH/điều phối hoặc tài xế kể lại cách bên cho thuê xử lý |
| Câu / mô tả đáng nhớ | Sự cố đi một đường (chat), trừ tiền đi đường hệ thống khác |
| Chuyện cụ thể đã xảy ra | Case sự cố nằm chat/theo dõi thủ công; billing vẫn tự chạy; hoàn/cấn trừ xử lý sau |
| Workaround hiện tại | Hoàn tay; bảo tài xế chờ; không có SLA trạng thái rõ cho tài xế |
| Mất bao lâu, bao lần? | Hoàn có thể kéo dài; không đồng bộ với lúc xe chết |
| Insight | Cần **một mã/ticket nối hai mạch**; hoàn tay là workaround đắt |

Tổng hợp:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác |
|---|---:|---|---|
| Quan sát/nghe kể (structured) | ≥2 góc (tài xế + vận hành kể lại) | Lặp lại pattern “đã báo hỏng / treo BH mà vẫn bị trừ”; hỏi lại tốn phút; có case trả xe | “Ngày đầu hỏng” chỉ là ví dụ case, không phải pattern mặc định |
| Báo cáo cá nhân Cường (CP1–CP2) | 1 actor chính | Bottleneck hai mạch; metric % mã &lt;5' và cờ billing | Baseline % trả xe chưa có số cứng → phải đo sau |
| Research tool | 3 nguồn (Moiboo ×2, Rently) | Thị trường đã có Pause Rental + incident status gắn booking | Tool quốc tế ≠ mọi fleet VN đã dùng; policy pause chưa chắc |

**Nhóm đã sửa problem thế nào sau kiểm chứng:** Chưa có kiểm chứng chính thức nên chưa kết luận về tỷ lệ trả xe hoặc tỷ lệ bị tính tiền. Nhóm thu hẹp phạm vi về việc tạo mã và cập nhật trạng thái sau khi báo lỗi; các quyết định tiền thuê, đổi xe và hoàn tiền vẫn cần người có thẩm quyền.

- Thu hẹp: không giải “cả bảo hiểm”; chỉ **nối sự cố đã báo → trạng thái hệ thống → tạm dừng/ghi nhận billing**.
- Khẳng định MVP = **Rule**, không phải chatbot.
- Giữ giả định #6 (policy pháp lý/kế toán) là rủi ro Viability — pilot chỉ trên fleet đồng ý SOP pause.
- Ghi hạn chế: kiểm chứng chủ yếu quan sát/nghe kể + research; chưa có chuỗi Mom Test formal dài — ngưỡng dừng vẫn giữ nếu pilot không xác nhận pain tiền.

### 3.3. Research giải pháp đã có

| Công cụ / case / pattern | Link | Giải bước nào trong quy trình? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Moiboo — Pause / Resume rental khi breakdown, accident, service | https://www.moiboo.com/blog/workshop-software/vehicle-downtime-management-car-rental/ | Tạm dừng thỏa thuận thuê khi xe out of service; resume khi sẵn sàng | Đúng lệch billing vs downtime; cập nhật agreement | Là sản phẩm fleet; chưa chứng minh mọi bên thuê VN đang dùng | **Không tự xây agent pause billing** — pattern Rule đã có trên thị trường |
| Moiboo — Pause/Extend/Replace cập nhật agreement + billing | https://www.moiboo.com/blog/workshop-software/daily-car-rental-management/ | Mid-rental changes: pause, swap xe, invoice/credit note theo agreement | Single source of truth cho tiền + trạng thái thuê | Cần ops dùng đúng thao tác Pause | MVP = **rule gắn sự cố với agreement/billing** |
| Rently — Incident module (status Started / In Process / Finished, gắn booking) | https://www.rentlysoft.com/en/incident-module | Ghi nhận sự cố gắn booking; lifecycle trạng thái; invoice/payment trên incident | Minh bạch trạng thái sự cố — đúng Opportunity A | Tập trung claim/damage hơn “pause thuê ngày”; demo/sales page | Cần **mã + status** trên hệ thống, không để chat rời |

**Kết luận research:**

```text
Thị trường fleetrental đã có Pause Rental + incident status gắn booking.
Không có lý do tự xây agent.
Hướng hợp lý: Form/mã sự cố → trạng thái trên hệ thống → Rule tạm dừng hoặc ghi nợ hoàn gắn ticket → người duyệt hoàn → tài xế xem được trạng thái.
AI (nếu có) chỉ phụ: đọc mô tả chat để draft ticket / draft trả lời — không tự trừ/hoàn.
```

---

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

```text
HIỆN TẠI — hai mạch lệch nhau

[1 Phát hiện hỏng] → [2 Báo chat/hotline]
        │
        ▼
[3 Sự cố: không rõ lưu/quản lý trên hệ thống] 🔴
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
[5 Sau này hoàn / cấn trừ?] ⚠ mơ hồ → tranh chấp
   hoặc [6 Trả xe / bỏ cuộc]
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | Tài xế | Xe không dùng được | Báo cáo sự cố miệng/ảnh | Mỗi case sự cố | |
| 2 | Tài xế → CSKH | Chat/hotline | Tin nhắn rời | Vài phút | Không chắc có mã |
| 3 | CSKH / điều phối | Chat | “Đang xử lý” mơ hồ | Hỏi lại 10–30'/lần | Bottleneck minh bạch |
| 4 | Xưởng / BH | Xe | Chờ sửa | Ngày–tuần | |
| B | Hệ thống billing | Chu kỳ thuê | Trừ tiền tiếp | Tự động | Bottleneck tiền |
| 5–6 | Kế toán / tài xế | Khiếu nại | Hoàn tay hoặc trả xe | Không SLA | |

**Bottleneck chính:** Lệch hai mạch — sự cố không có trạng thái rõ trong khi billing vẫn chạy.

### 4.2. Quy trình tương lai

```text
TƯƠNG LAI — MVP Rule (không cần AI để chạy)

[1 Phát hiện hỏng] → [2 Form báo lỗi (ảnh + mô tả + xe/hợp đồng)]
→ [3 Hệ thống tạo MÃ SỰ CỐ + trạng thái (Mới/Đang BH/Tạm dừng thuê/…)]  ← RULE
→ [4 Rule: nếu đủ điều kiện SOP → TẠM DỪNG trừ thuê HOẶC gắn cờ “ghi nợ hoàn”]  ← RULE
→ [5 CSKH/kế toán duyệt pause hoặc duyệt hoàn (HITL)]  ← CON NGƯỜI
→ [6 Tài xế xem mã + trạng thái + trạng thái tiền trên app]
→ [7 BH xong → Resume thuê / chốt hoàn]

(Tuỳ chọn sau MVP)
[2b AI đọc chat cũ → draft điền form ticket]  ← AI phụ, người xác nhận

BOUNDARY:
- AI không tự tạm dừng billing, không tự hoàn tiền, không tự đóng case.
- Chỉ Rule + người duyệt (HITL) được đổi trạng thái tiền.
- Mọi thay đổi billing phải có mã sự cố gắn kèm.

PHƯƠNG ÁN QUAY VỀ:
- Rule/pause lỗi hoặc dispute → giữ ảnh/bill, CSKH hoàn tay theo SOP cũ; không “AI quyết”.
```

### 4.3. Before / after

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| Số bước lõi | 5–6 (+ billing song song) | 6–7 (có mã + duyệt) | Thêm bước nhưng giảm mơ hồ |
| Thời gian có mã/trạng thái sau báo lỗi | ~0% trong &lt;5' | ≥90% case &lt;5' | Metric chính |
| Case BH/treo có cờ gắn billing | Thấp / không rõ | Có trước cuối ngày sự cố | |
| Bước thủ công tranh chấp | Cao (hỏi lại nhiều lần) | Thấp hơn (xem status) | |
| Bottleneck chính | Billing chạy khi sự cố mờ | Duyệt HITL pause/hoàn | Chấp nhận — điểm kiểm soát tiền |
| Rủi ro mới | — | Pause nhầm / abuse báo ảo | SOP điều kiện + người duyệt |

---

## 5. Problem Statement v0 (CP5)

| Trường | Nội dung |
|---|---|
| **Actor** | Tài xế thuê xe chạy app; CSKH / điều phối / kế toán bên cho thuê |
| **Quy trình** | Phát hiện hỏng → báo chat/hotline → chờ BH → hệ thống vẫn trừ thuê → hoàn/cấn trừ sau (nếu có) hoặc trả xe |
| **Bottleneck** | Sự cố không có mã/trạng thái rõ trên hệ thống trong khi billing tự động vẫn chạy |
| **Impact** | Mất tiền thuê lúc xe không chạy; mất thu nhập; tăng trả xe; tốn thời gian CSKH/kế toán tranh chấp |
| **Success Metric** (baseline → target, cách đo) | (1) % case báo lỗi có mã + trạng thái trong &lt;5 phút: ~0% → ≥90% (log hệ thống). (2) % case BH/treo có cờ gắn billing (pause hoặc ghi nợ hoàn) trước cuối ngày sự cố. (3) Giảm trả xe trong 7 ngày sau báo lỗi so với baseline nội bộ fleet (đo sau khi có số). |
| **Boundary** | Không dùng AI để tự trừ/hoàn/tạm dừng tiền; mọi đổi billing cần mã sự cố + người duyệt (HITL) |

Phản biện nhận được và nhóm có đồng ý không:

- AI/PM hoài nghi: dễ hiểu nhầm là “cần AI tạo ticket” → **Đồng ý**; nhấn mạnh tạo mã = Rule.
- Nhóm: thiếu baseline % trả xe cứng → **Đồng ý**; metric (3) so với baseline nội bộ đo sau, không bịa %.
- Nhóm: Viability policy pause chưa chắc → **Đồng ý**; ghi rủi ro #6 và ngưỡng dừng.

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô: **độ mơ hồ thấp–trung bình** (trạng thái sự cố/billing có đúng–sai theo SOP) × **độ phức tạp trung bình** (vài hệ thống: chat, BH, billing).

Vì sao: Phần lõi là if/else theo điều kiện SOP (có báo lỗi hợp lệ → gắn trạng thái → pause/ghi nợ). Không phải bài “nhiều cách viết đều đúng” kiểu narrative. → **Rule** là mức mặc định đúng.

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** | SOP giấy: Excel mã sự cố + nhắc kế toán pause tay | Fleet nhỏ, ít case | Dễ sót, không real-time trên app tài xế | Dự phòng |
| **Rule** | Form → mã + status; rule gắn ticket↔tạm dừng/ghi nợ hoàn; app xem status | Lệch hai mạch là pain chính | Pause nhầm; abuse | **Chọn (MVP)** |
| **Workflow** | Rule trên + AI draft ticket từ chat / draft trả lời CSKH → người duyệt | Chat volume lớn, muốn giảm gõ form | Draft sai nội dung sự cố | Tuỳ chọn sau |
| **Agent** | AI tự đọc chat, tự pause billing, tự hoàn | Khi tin AI quyết tiền | Rất cao (tiền, pháp lý) | Không |

**Mức chọn:** **Rule**

**Vì sao không chọn mức đơn giản hơn:** No AI (Excel) vẫn để tài xế mù trạng thái và dễ sót pause. Vì sao không Workflow/Agent ngay: research Moiboo/Rently cho thấy Pause + incident status là rule/ops; kiểm chứng cũng chỉ ra pain là lệch hệ thống, không phải thiếu chatbot. Agent đụng tiền = Viability xấu.

### 6.3. AI Canvas rút gọn

*(MVP Rule thuần — theo đề bài, khi chọn No AI/Rule có thể giải thích thay Canvas. Nhóm ghi ngắn lý do + Canvas cho bước AI phụ sau này.)*

**Vì sao MVP không cần AI dự đoán:** Đầu ra cần đúng/sai theo SOP (có mã, có/không pause). Không cần model sinh nội dung để giải pain lõi.

| Thành phần | Nội dung (chỉ khi bật AI phụ) |
|---|---|
| **Prediction** | Bản nháp ticket từ đoạn chat / gợi ý phân loại loại sự cố |
| **Judgment** | CSKH xác nhận đúng xe, đúng điều kiện pause |
| **Action** | Người bấm tạo mã / duyệt pause (Rule thực thi) |
| **Outcome** | % case có mã &lt;5'; % có cờ billing; số tranh chấp hoàn |
| **Input** | Chat/ảnh báo lỗi, mã hợp đồng/xe — có sẵn nếu CSKH lưu |
| **Feedback** | Case bị từ chối pause; case hoàn tay sửa lại |

### 6.4. Hai câu hỏi của Google PAIR

- Augment hay automate? Tài xế/CSKH cần **minh bạch + rule tiền**, không muốn bot tự trừ/hoàn. → **Augment quy trình (thực ra là Rule)**, không automate quyết định tiền.
- Sai kiểu nào tệ hơn? **Pause nhầm / hoàn oan (báo nhầm có sự cố)** và **không pause khi xe thật sự chết (bỏ sót)** đều xấu; với tiền thuê, nhóm ưu tiên tránh **tự động sai** → không để AI quyết; HITL bắt buộc. Bỏ sót pause vẫn tệ với tài xế → metric bắt buộc có cờ billing trước cuối ngày sự cố.

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

| Trường | Nội dung |
|---|---|
| **Actor** | Tài xế thuê xe đã báo lỗi; CSKH/kế toán fleet có SOP pause/ghi nợ hoàn |
| **Quy trình** | Báo lỗi → mã sự cố + status → rule gắn billing → người duyệt → tài xế xem → resume/hoàn khi xong |
| **Bottleneck** | Hai mạch lệch: sự cố mờ vs trừ thuê tự động |
| **Impact** | Tiền thuê oan, trả xe, tải CSKH/kế toán |
| **Success Metric** | (1) ≥90% case có mã+status &lt;5'. (2) Có cờ billing trước cuối ngày sự cố. (3) Giảm trả xe 7 ngày sau báo lỗi vs baseline nội bộ. |
| **Boundary** | AI không tự pause/hoàn/đóng case; mọi đổi tiền cần mã + HITL |
| **AI intervention point** | Không có ở MVP. Sau này (optional): sau chat báo lỗi, trước khi tạo ticket — chỉ draft |
| **Mức chọn** | **Rule** |
| **Rủi ro & người kiểm tra** | Pause nhầm / báo ảo → CSKH/kế toán duyệt; audit log theo mã sự cố |

**Thay đổi so với v0 và lý do:**

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| AI intervention point | (ngầm “có thể AI”) | Không có ở MVP | Research + PAIR: Rule đủ |
| Actor | Tài xế + CSKH chung | Thêm: fleet có SOP pause | Viability #6 — chỉ pilot nơi policy cho phép |
| Mức chọn | (chưa ghi) | Rule | Chốt sau so sánh 4 mức |

**Tiêu chí đánh giá** (cho giải pháp Rule / SOP; không phải output AI):

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| 1 | Có mã sự cố kịp thời | ≥90% case có mã+status trong &lt;5' sau báo hợp lệ | Báo xong vẫn chỉ nằm chat |
| 2 | Billing gắn sự cố | Trước cuối ngày sự cố có pause hoặc cờ ghi nợ hoàn | Trừ thuê bình thường không ghi nhận |
| 3 | Tài xế xem được trạng thái | App/portal hiện mã + status tiền | Phải nhắn CSKH mới biết |
| 4 | HITL trước đổi tiền | Mọi pause/hoàn có người duyệt + log | Rule tự chạy không kiểm hoặc AI tự quyết |
| 5 | Phương án quay về | Dispute → hoàn tay theo SOP, giữ bằng chứng | Không có cách xử lý khi pause sai |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro

| Rủi ro | Câu hỏi | Mức độ rủi ro (Thấp = an toàn / TB / Cao = nguy hiểm) | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | Trung bình | Quan sát + Mom Test xác nhận lệch billing; mẫu còn nhỏ |
| **Usability** | Dùng được không? | Thấp | Form + xem status quen thuộc; không học model mới |
| **Feasibility** | Làm được không? | Thấp–TB | Pattern Pause Rental / incident đã có trên thị trường; phụ thuộc hệ thống fleet hiện tại |
| **Viability** | Policy/pháp lý/kế toán cho pause không? Ai vận hành? | Trung bình → theo dõi | Giả định #6 chưa chốt; cần SOP fleet trước pilot |

### 8.2. Kết luận

**Quyết định:** **Go, phạm vi nhỏ** (Rule trên một fleet/pilot SOP — không build AI)

**Lý do:** Không rủi ro Cao nếu không để AI đụng tiền. Value/Viability Trung bình kiểm được bằng pilot SOP + đo % có mã và có cờ billing.

**Nếu Go — pilot nhỏ nhất:** Thử với một nhóm xe hoặc một đối tác trong thời gian cố định; dùng form + mã ticket, đo baseline trước và so sánh sau về tỷ lệ cấp mã, số lần hỏi lại, thời gian chờ và lỗi billing.

1. Một fleet (hoặc giả lập ops): form báo lỗi → Google Sheet/DB đơn giản có mã + status.
2. SOP: đủ điều kiện thì đánh dấu “tạm dừng/ghi nợ”; kế toán duyệt trong ngày.
3. Đo 2 tuần: % có mã &lt;5'; % có cờ billing; số lần tài xế phải hỏi lại status.

**Ngưỡng dừng:**

- Nếu sau 2 tuần **&lt;70%** case có mã trong &lt;5' → quay về siết SOP chat (No AI thuần), chưa làm rule billing.
- Nếu có **1 case pause nhầm gây mất doanh thu** mà không có HITL log → dừng auto-rule, chỉ ghi nợ hoàn thủ công.
- Nếu fleet **không cho pause billing theo policy** → **No-Go Rule pause**; chỉ làm minh bạch status sự cố + quy trình hoàn tay rõ hạn.

---

## 9. Hạn chế và hướng tiếp theo

- Mẫu kiểm chứng còn mỏng — cần thêm phỏng vấn tài xế/CSKH thật trước khi scale.
- Chưa có baseline % trả xe nội bộ số cứng.
- Candidate học tập (Khánh) và JD (Đức) giữ cho vòng lab khác.
- Ứng viên liên quan: checklist trả xe / điểm đón Vin — không gộp vào MVP này.

## 10. Tài liệu tham khảo

- `report/individual/2A202603866_HuynhVanCuong.md` (card #1 — nguồn candidate)
- `report/individual/2A202603804_LeNgocKhanh.md`, `2A202603818_NguyenPhanTuanDuc.md`
- Moiboo downtime / Pause Rental: https://www.moiboo.com/blog/workshop-software/vehicle-downtime-management-car-rental/
- Moiboo daily rental changes + billing: https://www.moiboo.com/blog/workshop-software/daily-car-rental-management/
- Rently Incident module: https://www.rentlysoft.com/en/incident-module
- [docs/01-worksheet.md](../../docs/01-worksheet.md), [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md)
